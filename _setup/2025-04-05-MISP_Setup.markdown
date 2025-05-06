---
layout: posts
title: "Deploy MISP"
permalink: /Deploy MISP/
hide_date: true
order: 2
---

How to deploy MISP using Docker. 

See the <a href="/install tools/">installing useful tools</a> page if you haven't worked with docker before or search docker in the <a href="/resources/">resources.</a> 

## Key concepts to know


Below are instructions to create an initial non production set up. For more information on installation and usage of OpenCTI see the <a href="https://www.circl.lu/doc/misp/" target="_blank" style="color: #3399ff; font-weight: normal; font-size: 14px;">Official documentation.</a>

## Deploying MISP

 <span style="font-size: 18px; font-weight: bold;">Clone the repository</span>

Create or navigate to a folder that will store the MISP repository. Once inside, copy the contents of the repository from Github to your machine by running on the command line:

<p>
  <code style="...">git clone https://github.com/MISP/misp-docker.git</code>
</p>

The files will be downloaded contained in a folder called misp-docker. Change directory into this folder and you will see the docker-compose.yml file and other files.

<p>
  <code style="...">cd misp-docker</code>
</p>

 <span style="font-size: 18px; font-weight: bold;">Create the .env file</span>

Copy the file called template.env to a new file called .env.

<span style="font-size: 15px; font-weight: bold;">macOS or Linux</span>
<p>
  <code style="...">cp template.env .env</code>
</p>

<span style="font-size: 15px; font-weight: bold;">Windows CMD</span>
<p>
  <code style="...">copy template.env .env</code>
</p>

Note: It is recommended to change the username and password in .env file for your own security, but it will work without changes if you just want to get running.

 <span style="font-size: 18px; font-weight: bold;">Launch MISP</span>
 
Ensure you are in the misp-docker folder. Run

<p>
  <code style="..."> docker compose pull</code>
</p>

After the images have downloaded, run

<p>
  <code style="..."> docker compose up -d</code>
</p>

After a minute or so, open a browser and go to http://localhost. Use the default username and password or if you change it, the one set in the .env file to log in.

User: admin@admin.test
Password: admin

If you wish to stop MISP then run the command
  <code style="..."> docker compose stop</code>

Then if you wish to start MISP again, run the command
  <code style="..."> docker compose start</code>

