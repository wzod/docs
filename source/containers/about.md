# Docker Images for Malware Analysis

The REMnux project provides [Docker](https://www.docker.com/) images of popular malware analysis tools, with the goal of allowing investigators to conveniently utilize difficult-to-install applications without having to install the REMnux distro. Such images could be compared to lightweight virtual machines; though they don't offer the same level of isolation as real VMs, they provide a container within which the application can be encapsulated along with its dependencies.

## How to Run Dockerized Applications?

To run REMnux-provided  application images, first you need to install Docker. This very easy to do on Linux (e.g. "`apt-get install docker.io`") and relatively painless on Windows and OS X. Just follow [Docker's installation instructions](https://docs.docker.com/installation/#installation) for your operating system.

Once Docker is installed, you can run a Dockerized application by specifying the name of the desired app image. For example, to run the REMnux-provided image of [Thug](https://github.com/buffer/thug), a low-interaction honeyclient, you would type something like "`docker run --rm -it remnux/thug bash`".

![Running Thug in Docker](containers/remnux-docker-thug-full.gif)

Docker maintains the [Docker Hub Registry](https://hub.docker.com/) of applications published as Docker images, within which the [REMnux repository](https://registry.hub.docker.com/repos/remnux/) of several malware analysis apps images is present. For a listing of the available applications and guidelines for running them, see below.

The first time you run a Dockerized application, Docker will automatically download it from the Registry; your system will need to be connected to the Internet at that time. Afterwards, Docker will use a local copy of the image without relying on the Internet. If the application's image has been updated and you are connected to the Internet, Docker will automatically update your image when you run the app.

## What is Docker?

Docker takes advantage of Linux kernels' ability to run applications in containers, which are sometimes described as "chroot on steroids." Containers provide each application an independent runtime environment, while avoiding the overhead of a full-fledged virtual machine.

Each container gets its own virtual file system, process listing and network stack; however, containers share the OS kernel with each other and the underlying host. In this respect, the isolation provided by containers is less robust than that of real virtual machines, which have independent kernels and run on top of a hypervisor. Yet, sharing the kernel allows containers to run faster and offers management features that are difficult to accomplish with traditional virtualization.

An application distributed as a Docker image incorporates all the dependencies and configuration necessary for it to run, eliminating the need for end-users to install packages and troubleshoot dependencies. This approach allows developers to be certain that if the application worked in dev, it will work in production. Docker provides the tools necessary to build, run and manage applications packaged as Docker images.

## Benefits of Applications as Containers

In many cases, it is convenient to launch malware analysis tools the traditional way by running them directly on the OS, for instance taking advantage of the packages preinstalled as part of the [REMnux distribution](https://remnux.org/#distro). Alternatively, you might want to run a tool without installing it directly onto your system, perhaps because you want to keep your system unclattered, or because it lacks the dependencies necessary to run the application.

When running the app as a Docker container, you're able to take advantage of the image developer's efforts to figure out how to properly set up the application. Also, you get to benefit from any updates that the application's developer and the image maintainer introduces without having to worry how to install them.

Because Docker images are mostly independent of each other, you can run applications in environments separate from each other and the underlying system; this is especially useful when applications rely on conflicting dependencies. Because Docker containers are more lightweight than virtual machines, it's more practical to dedicate a container to a single app than trying to set up a VM per application.

A Redhat article outlines [additional benefits that Docker offers](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/7.0_Release_Notes/sect-Red_Hat_Enterprise_Linux-7.0_Release_Notes-Linux_Containers_with_Docker_Format-Advantages_of_Using_Docker.html), which include:

- Rapid application deployment
- Portability across machines
- Version control and component reuse
- Simplified maintenance

Lastly, those who are trying to install applications directly on their system without Docker can examine the Dockerfile config for the desired application to see explicit, scriptable instructions for installing the app into their own environment.

Docker containers have their limitations and sometimes it's easier to run applications the traditional way. By providing Docker images several popular malware analysis tools, in addition to offering a full Linux distro, REMnux gives you the flexibility to investigate malicious software using several approaches.

## Available Application Images

The [REMnux repository on the Docker Hub Registry](https://registry.hub.docker.com/repos/remnux/) lists the images of malware analysis applications available as part of the project. These apps include:

- Google's JavaScript engine for JavaScript deobfuscation: [remnux/v8](https://registry.hub.docker.com/u/remnux/v8/)
- Thug low-interaction honeyclient: [remnux/thug](https://registry.hub.docker.com/u/remnux/thug/)
- Viper binry analysis and management framework:  [remnux/viper](https://registry.hub.docker.com/u/remnux/viper/)
- Rekall memory forensic framework:  [remnux/rekall](https://registry.hub.docker.com/u/remnux/rekall/)
- JSDetox malware analysis tool for JavaScript deobfuscation:  [remnux/jsdetox](https://registry.hub.docker.com/u/remnux/jsdetox/)

Help expand this collection. You can create Dockerfile configs or building Docker images of malware analysis applications that are not yet present in the repository. Once you have built and tested your Dockerfile, [share it with Lenny Zeltser](http://zeltser.com/about/contact.html), so he can review it and, if appropriate, incorporate your contribution into the REMnux repository.
