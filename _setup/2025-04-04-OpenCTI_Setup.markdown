---
layout: posts
title: "Deploy OpenCTI"
permalink: /Deploy OpenCTI/
hide_date: true
order: 2
---

How to deploy OpenCTI using Docker and get some initial feeds. 

See the <a href="/install tools/">installing useful tools</a> page if you haven't worked with docker before or search docker in the <a href="/resources/">resources.</a> 

## Key concepts to know

OpenCTI requires a .env file to be configured before it can run. Several of the required values are UUIDs, which can be easily generated using tools like jsonreader.com’s UUID generator. Simply generate, copy, and paste the UUIDs into the appropriate fields in your .env file.

OpenCTI uses connectors, which are services running as Docker containers, to ingest external data sources. Each connector requires specific configuration settings in the docker-compose.yml file. 

The configurations for connectors can be found <a href="https://github.com/OpenCTI-Platform/connectors/tree/master/external-import">here.</a> These can be run as individual containers or you can add the compose instructions to the OpenCTI Docker-compose.yml file as will be done below.

As you integrate more connectors into your OpenCTI instance, be aware that the resource load will increase accordingly. For production environments, it is better to deploy connectors in their own separate infrastructure.

Below are instructions to create an initial non production set up. For more information on installation and usage of OpenCTI see the <a href="https://docs.opencti.io/latest/deployment/installation/" target="_blank" style="color: #3399ff; font-weight: normal; font-size: 14px;">Official documentation.</a>

## Deploying OpenCTI

 <span style="font-size: 18px; font-weight: bold;">Clone the repository</span>

Create or navigate to a folder that will store the OpenCTI repository. Once inside, copy the contents of the repository from Github to your machine by running on the command line:

<p>
  <code style="...">git clone https://github.com/OpenCTI-Platform/docker.git</code>
</p>

The files will be downloaded contained in a folder called docker. Change directory into this folder and you will see the docker-compose.yml file and other files.

<p>
  <code style="...">cd docker</code>
</p>

 <span style="font-size: 18px; font-weight: bold;">Create and edit the .env file</span>

Create a file called .env and open it ready to paste the environment variables into it.

<span style="font-size: 15px; font-weight: bold;">macOS or Linux</span>
<p>
  <code style="...">nano .env</code>
</p>

<span style="font-size: 15px; font-weight: bold;">Windows CMD or Powershell</span>
<p>
  <code style="...">notepad .env</code>
</p>

You can paste the text below and it will work out of the box, but for your own security, you should replace the example values with your own. The <a href="https://www.jsonreader.com/uuid-generator">UUIDs </a>can be generated online



<div class="text-file-style">
OPENCTI_ADMIN_EMAIL=admin@opencti.io
OPENCTI_ADMIN_PASSWORD=YOURpasswordHERE
OPENCTI_ADMIN_TOKEN=7f3d8528-cd31-4a16-a28e-e01b16e708ce
OPENCTI_BASE_URL=http://localhost:8080
OPENCTI_HEALTHCHECK_ACCESS_KEY=6BE9676A-071E-4502-BC6E-59541B68A5D1
MINIO_ROOT_USER=92F11EEC-C1DB-4D52-8487-15F38B91D477
MINIO_ROOT_PASSWORD=2850f4b4-67a4-4a39-9875-cc719ac61ed7
RABBITMQ_DEFAULT_USER=guest
RABBITMQ_DEFAULT_PASS=guest
ELASTIC_MEMORY_SIZE=4G
CONNECTOR_HISTORY_ID=2464908F-04D9-45BD-856A-960C914DBD94
CONNECTOR_EXPORT_FILE_STIX_ID=B9220E67-1255-4821-B885-84475EB11AEC
CONNECTOR_EXPORT_FILE_CSV_ID=FA9B44C9-EFA2-42AB-BC6C-47B36D2ACBBD
CONNECTOR_IMPORT_FILE_STIX_ID=DAB8F60E-5994-41BB-A10B-73811B15FD1F
CONNECTOR_EXPORT_FILE_TXT_ID=0AF8F20F-60B6-4343-8525-494A8B5BA91B
CONNECTOR_IMPORT_DOCUMENT_ID=34B33DD8-C6C1-4E85-A603-15D9778391F6
CONNECTOR_ANALYSIS_ID=B4272FD6-877F-4DA6-97C3-0369EFDBA0EF
CONNECTOR_CISA_ID=7de23594-e5e1-4bd8-aa31-001c192f0236
SMTP_HOSTNAME=localhost
</div>
<br>
If using nano, save the file by holding <code style="...">control</code> and pressing <code style="...">x</code> and when asked to save the modified buffer, pressing <code style="...">y</code>

 <span style="font-size: 18px; font-weight: bold;">Adding connectors</span>

To add a connector to your docker-compose.yml file, start by locating the connector’s own docker-compose.yml from the <a href="https://github.com/OpenCTI-Platform/connectors/blob/master/external-import/cisa-known-exploited-vulnerabilities/docker-compose.yml">OpenCTI repository.</a> 

If adding the connector to the main docker-compose.yml file used by OpenCTI, paste the contents of the connector’s docker-compose.yml below the existing connectors in that file.

For example, to add the CISA KEV conenctor paste in the contents of the docker-compose.yml excluding

version: '3' <br>
services:

but with the following added below:

depends_on:<br>
&nbsp;&nbsp;&nbsp;&nbsp;opencti:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   condition: service_healthy

Then change the variables as shown to match the OpenCTI .env file created earlier.

Your OpenCTI docker-compose.yml file would include the following instructions, postioned below the other connectors and above volumes:

<div class="vscode-window-light">
  <div class="vscode-header-light">
    <span class="dot red"></span>
    <span class="dot yellow"></span>
    <span class="dot green"></span>
    <span class="filename">docker-compose.yml</span>
  </div>
  <div class="vscode-editor-light">
  connector-cisa-known-exploited-vulnerabilities:
    image: opencti/connector-cisa-known-exploited-vulnerabilities:6.6.3
    environment:
      - OPENCTI_URL=http://opencti:8080 #changed
      - OPENCTI_TOKEN=${OPENCTI_ADMIN_TOKEN} #changed
      - CONNECTOR_ID=${CONNECTOR_CISA_ID} #changed
      - "CONNECTOR_NAME=CISA Known Exploited Vulnerabilities"
      - CONNECTOR_SCOPE=cisa
      - CONNECTOR_RUN_AND_TERMINATE=false
      - CONNECTOR_LOG_LEVEL=error
      - CONNECTOR_DURATION_PERIOD=P2D
      - CISA_CATALOG_URL=https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
      - CISA_CREATE_INFRASTRUCTURES=false
      - CISA_TLP=TLP:CLEAR
    restart: always
    depends_on: #Added
      opencti: #Added
        condition: service_healthy #Added
  </div>
</div>

Note: Some connectors, such as NIST’s CVE connector, require an API key. This can be requested for free from NIST. Others may need additional configuration. For details, refer to each connector’s README file.

Repeat for each new connector

 <span style="font-size: 18px; font-weight: bold;">Launch OpenCTI</span>
 
Ensure you are in the docker folder for OpenCTI. After making any changes to your Docker-compose.yml file, to launch OpenCTI you should run

<p>
  <code style="..."> docker compose up -d --build</code>
</p>

After a few minutes, open a browser and go to http://localhost:8080/. Use the username and password set in the .env file to log in.

If you wish to stop OpenCTI then run the command
  <code style="..."> docker compose down</code>



