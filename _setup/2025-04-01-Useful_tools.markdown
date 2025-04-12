---
layout: posts
title: "Installing useful tools"
permalink: /install tools/
hide_date: true
order: 1
---
<!-- ---
layout: posts
title: "Set Up"
hide_date: true
order: 4
--- -->
Help installing Docker, Git and Visual Studio

I've found that many common tools assume a level of technical knowledge that can make it difficult for entry-level analysts to dive in and start using them effectively. 

But by installing a few basic programs, Git, Visual studio and Docker Desktop, much of the complexity is abstracted from the user and many great tools can be easilly used.

Git is a version control system that allows users to track changes in code. A common way people use Git is by hosting public repositories, such as on Github, that anyone can access and download, enabling easy sharing of code with the broader community.

Docker is a platform used to run containers. A container includes everything needed for an application to run such as libraries and system tools and allows the app to run consistently on any system where Docker is installed. It is not virtualisation but a restricted process in the host OS.

Containers are built from images. An image is a static, read-only package that contains all the components required to run the application inside a container. Once Docker is installed, you gain access to a vast ecosystem of public containers and images.  

There are several ways to obtain Docker images, and one method is by cloning a repository from GitHub, which requires Git to be installed. Public repositories on GitHub often contain Dockerfiles, which have instructions for Docker to assemble an image. From the image, Docker can then create a container, which is the live, running instance of that image.

It is often necessary to edit Docker related files to configure settings (e.g. passwords and startup parameters). Installing a code editor like Visual Studio Code simplifies this by providing helpful features like syntax highlighting and error correction.

Follow the below to get your machine set up.

## Install Docker Desktop

See Bret Fisher's Set up videos below which assume no previous knowledge of Docker. Note: He runs a paid Udemy course, which these free videos are  excerts from.

<span style="font-size: 18px; font-weight: bold;">Windows</span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/rATNU0Fr8zs?si=-F5Mh6kLtTlLKWtx" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe><br>

<span style="font-size: 18px; font-weight: bold;">macOS</span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/gcacQ29AjOo?si=g2WYMz3G7EHOZ-Lf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe><br>

<span style="font-size: 18px; font-weight: bold;">Linux</span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/AMcvwqvgU5U?si=mp5Huyb3woyYwBjd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe><br>


<span style="font-size: 18px; font-weight: bold;">Confirm installation</span>

Open a Terminal and run the command

<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>docker version</code>
</pre>

If using Linux:

<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>sudo docker version</code>
</pre>

If you experience problems installing Docker Desktop you can try the <a href="https://forums.docker.com/c/docker-desktop/48" target="_blank" style="color: #3399ff; font-weight: normal; font-size: 14px;">Docker Community Forum</a><br>


## Section 2: Install Git

See these short videos below

<span style="font-size: 18px; font-weight: bold;">Windows</span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/JNWXQskz4Uk?si=mfW6RVY6OL1OXTlO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe><br>


<span style="font-size: 18px; font-weight: bold;">macOS</span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/Mf3l8z6oxQ0?si=Ntz7a0BYwDNHW9Xg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe><br>

<span style="font-size: 18px; font-weight: bold;">Linux</span>

Open a Terminal and run the command

<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>sudo apt update</code>
</pre>
<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>sudo apt install git -y</code>
</pre>

<span style="font-size: 18px; font-weight: bold;">Confirm installation</span>

In a Terminal run the command

<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>git --version</code>
</pre>


## Section 3: Using git to clone a repository from github

To use the files stored in a GitHub repository, you need to copy (clone) them to your local machine. This is typically done using a terminal command via either the HTTPS or SSH protocol.

First locate the clone url from the repository page in github which can be found under the Code button and clone HTTPs.

<button class="github-code-button" type="button">
  <span class="icon">&lt;/&gt;</span> Code
</button>

In a Terminal move to or create the folder you want to store the files and run the command below, replacing clone-url with the HTTPS url you just copied. 

<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>git clone <em>clone-url</em></code>
</pre>


## Section 4: Building and running a docker container


<div style="background-color: #fff3cd; color: #856404; border: 1px solid #ffeeba; padding: 12px 16px; border-radius: 6px; font-size: 16px; font-weight: bold; margin-top: 12px;">
  ⚠️ Security Warning: Only run Docker images and containers from trusted sources. Unverified or malicious images can compromise your system, steal data, or install harmful software. Always review the source and avoid elevated permissions unless necessary.
</div><br>

<span style="font-size: 18px; font-weight: bold;">Important note about Docker commands</span>

Some time ago, Docker made a change to the way commands are run, adding a command and sub-command instead of just command. The modern approach is to run commands in the format as below but you may come across both: 

<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
docker &lt;command&gt; &lt;sub-command&gt;
</pre>

Example: 

Modern
<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>docker container run</code>
</pre>

Legacy (may still work)
<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>docker run</code>
</pre>

Additionaly you may see

Modern
<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>docker compose</code>
</pre>

Legacy
<pre style="background-color: #1e1e1e; color: #d4d4d4; padding: 12px; border-radius: 6px; font-family: monospace; font-size: 14px;">
<code>docker-compose</code>
</pre>

<span style="font-size: 18px; font-weight: bold;">Key concepts to know</span>

<p>
  <code style="...">docker compose</code> is used to launch multi-container applications, whereas 
  <code style="...">docker run</code> is for a single container. You will come across both depending on the app.
</p>
<code style="...">docker compose</code>  creates a Docker network connecting the containers defined in a .yml file. This network allows containers to communicate by service name, as each container is automatically named and Docker's built-in DNS handles name resolution within the network. External traffic can route through NAT via the host machine and restricts inbound access unless ports are explicitly published. If using <code style="...">docker run</code> you will have to add containers to a new Docker network for them to communicate since the default network does not have built-in DNS.

The docker-compose.yml file not only defines the containers and networks but also manages persistent storage through volumes. However, many applications running inside containers require configuration settings, such as passwords or startup parameters. Instead of hardcoding these values directly in the YAML file, it's common to store them in a separate .env file. Due to this, you will often have to fill in a .env file before being able to run <code style="...">docker compose.</code>



## Section 5: Visual Studio Code

Download <a href="https://code.visualstudio.com/">Visual Studio Code</a>

Follow the installation instructions.

Once in Visual Studio install the <a href="https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker"> docker</a> <a href=" https://code.visualstudio.com/docs/getstarted/extensions"> extension</a>

You now have a foundational setup to deploy and manage Docker based applications.



