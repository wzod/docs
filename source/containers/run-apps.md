If you'd like to run the tools below without installing the full REMnux Linux distro, you can use the REMnux collection of [Docker Images for Malware Analysis](malware-analysis.md). The following page explains which applications are available as images and how to run them, assuming you've installed Docker on your underlying host.

## Google's V8 JavaScript Engine: remnux/v8

[Google's V8 JavaScript Engine](https://code.google.com/p/v8) can be useful for obfuscating JavaScript embedded in malicious browser pages and PDF files. The REMnux image of this application is available in the the Docker Hub Registry as [remnux/v8](https://registry.hub.docker.com/u/remnux/v8/).

![Running remnux/v8](containers/remnux-docker-v8.gif)

The easiest way to use V8 is to invoke it by first running `bash` or another shell within its container, and then running the `d8` command:

    sudo docker run --rm -it remnux/v8 bash

However, since you'll probably want to provide some files for V8 to examine and get some files back, you will probably want to invoke Docker with the `-v` parameter to specify a shared directory that the container and the underlying host will be able to access:

    sudo docker run --rm -it -v ~/files:/home/nonroot/files remnux/v8 bash

In the example above, the ~/files directory will be shared between your host and the container. Before running the command above, make sure that ~/files exists and that its permissions are world-readable (i.e., `chmod a+xwr`).

The remnux/v8 image includes a file that defines several objects, methods and properties that malicious JavaScript scripts running in a standalone interpreter will require. This file is located within the container in the ~/def.js location. You might need to modify it to address the needs of your sample.

Once in the container, you might want to invoke the V8 application using a command like this:

    d8 -f ~/def.js ~/files/file.js

## Thug Low-Interaction Honeyclient: remnux/thug

[Thug](https://github.com/buffer/thug) low-interaction honeyclient can assist with the analysis of suspicious websites. The REMnux image of this application is available in the the Docker Hub Registry as [remnux/thug](https://registry.hub.docker.com/u/remnux/thug/).

![Running remnux/thug](containers/remnux-docker-thug.gif)

The easiest way to use Thug is to invoke it by first running `bash` or another shell within its container, and then running the `./thug.py` command:

    sudo docker run --rm -it remnux/thug bash

If you will want to save the log files that Thug creates when assessing the designated website, you will want to invoke Docker with the `-v` parameter to specify a shared directory that the container and the underlying host will be able to access:

    sudo docker run --rm -it -v ~/logs:/home/thug/logs remnux/thug bash

In the example above, the ~/logs directory will be shared between your host and the container. Before running the command above, make sure that ~/logs exists and that its permissions are world-readable (i.e., `chmod a+xwr`). If you'd like to share an additional directory (e.g., "files"), supply the mapping using another -v parameter such as `-v ~/files:/home/thug/files` and remember to make the directory on your host world-accessible.

Once in the container, you might want to invoke the Thug application using a command like this:

    ./thug.py http://example.com

If you want Thug to examine a single website and don't need an interactive shell, you could run its image like this:

    sudo docker run --rm -it -v ~/logs:/home/thug/logs remnux/thug ./thug.py http://example.com

In the example above, we launched the Thug image and specified that the command to run within it should be `./thug.py http://example.com`. We also directed Docker to share the underlying host's ~/log directory, which is where Thug saved the results of its analysis.

![Non-Interactive Thug Session](containers/remnux-docker-thug2.png)

## Viper Binary Analysis Framework: remnux/viper

[Viper](http://viper.li/) is "a binary management and analysis framework dedicated to malware and exploit researchers." It's useful to examine samples and maintain historical records about prior investigations. The REMnux image of this application is available in the the Docker Hub Registry as [remnux/viper](https://registry.hub.docker.com/u/remnux/viper/).

![Running remnux/viper](containers/remnux-docker-viper.gif)

One way to launch Viper is to simply run its container:

    sudo docker run --rm -it remnux/viper

This will automatically launch the tool. Alternatively, you could start the container by first running `bash` or another shell in it, and then running the `../viper/viper.py` command with the desired parameters:

    sudo docker run --rm -it remnux/viper bash

However, you'll probably want to share a directory between the container and your underlying host, so that Viper can read your samples and save its analysis. To do this, invoke Docker with the `-v` parameter to specify a shared directory that the container and the underlying host will be able to access:

    sudo docker run --rm -it -v ~/viper-workdir:/home/nonroot/workdir remnux/viper

In the example above, the ~/viper-workdir directory will be shared between your host and the container. Before running the command above, make sure that ~/viper-workdir exists and that its permissions are world-readable (i.e., `chmod a+xwr`).

## Rekall Memory Forensic Framework: remnux/rekall

[Rekall](http://www.rekall-forensic.com/) is a collection of tools for the extraction and analysis of artifacts from memory images. The REMnux image of this application is available in the the Docker Hub Registry as [remnux/rekall](https://registry.hub.docker.com/u/remnux/rekall/).

![Running remnux/rekall](containers/remnux-docker-rekall.gif)

One way to launch Rekall is to start the container by first running `bash` or another shell in it, and then running the `rekall` command with the desired parameters:

    sudo docker run --rm -it remnux/rekall bash

However, you'll probably want to share a directory between the container and your underlying host, so that Rekall can read your memory image files and save its output. To do this, invoke Docker with the `-v` parameter to specify a shared directory that the container and the underlying host will be able to access:

    sudo docker run --rm -it -v ~/files:/home/nonroot/files remnux/rekall bash

In the example above, the ~/files directory will be shared between your host and the container. Before running the command above, make sure that ~/files exists and that its permissions are world-readable (i.e., `chmod a+xwr`).

To use Rekall's web console, instead of its command-line interface, invoke the container with the -p parameter to give your host access to the container's TCP port 8000 like this:

    sudo docker run --rm -it -p 8000:8000 -v ~/files:/home/nonroot/files remnux/rekall

Then connect to http://localhost:8000 using a web browser from your underlying host. To stop the container running in this mode, press `Ctrl+C` in its terminal window.

## JSDetox JavaScript Analysis Tool: remnux/jsdetox

[JSDetox](http://www.relentless-coding.com/projects/jsdetox) is a web-based tool for analyzing and deobfuscating JavaScript. The REMnux image of this application is available in the the Docker Hub Registry as [remnux/jsdetox](https://registry.hub.docker.com/u/remnux/jsdetox/).

![Running remnux/jsdetox](containers/remnux-docker-jsdetox.gif)

One way to launch JSDetox, run its container like this:

    sudo docker run --rm -p 3000:3000 remnux/jsdetox

Then connect to http://localhost:3000 using a web browser from your underlying host.

To stop the JSDetox container, run `sudo docker ps -l` on your host to obtain the container ID, then use the `sudo docker stop `container-id` command and wait about a minute, where "container-id" is the ID of the JSDetox container.

Help expand this collection! You can put together Dockerfile configs for building Docker images of malware analysis applications that are not yet present in the repository. To do this, follow the guidelines in the article [Creating Docker Images for REMnux](create-docker-images.md).

## Radare2 Reverse Engineering Framework: remnux/radare2

[Radare2](http://radare.org/) is a reverse-engineering framework that includes a disassembler and other capabilities useful for analyzing malicious code. The REMnux image of this application is available in the the Docker Hub Registry as [remnux/radare2](https://registry.hub.docker.com/u/remnux/radare2/).

![Running remnux/radare2](containers/remnux-docker-radare2.gif)

To use Radare2, first running `bash` or another shell in its container and then specify the `rd2` command with the desired parameters:

    sudo docker run --rm -it remnux/radare2 bash

However, you'll probably want to share a directory between the container and your underlying host, so that Radare2 can read your samples and save its output. To do this, invoke Docker with the `-v` parameter to specify a shared directory that the container and the underlying host will be able to access:

    sudo docker run --rm -it -v ~/workdir:/home/nonroot/workdir remnux/radare2 bash

In the example above, the ~/workdir directory will be shared between your host and the container. Before running the command above, make sure that ~/workdir exists and that its permissions are world-readable (i.e., `chmod a+xwr`).