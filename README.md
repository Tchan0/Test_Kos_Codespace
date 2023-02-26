# To launch in your Web Browser a Visual Studio Code session that can compile for Dreamcast:
* Click on the green "Code" button
* Select the "Codespaces" Tab
* Click on !["Create codespace on main"](/img/create_codespace.png "Create codespace on main")
  * Github will create a codespace for you, this will take a couple of minutes the first time, but will be faster afterwards.

# This will launch Visual Studio Code in the browser, with:
* the sh-elf/arm compilers available in the terminal,
* the kos environ.sh sourced,
* dc-tool-ip installed

# Tips:
  * To add the Kos examples to your VSCode workspace:
    * code -a /opt/toolchains/dc/kos/examples
  * To go to the kos folder:
    * cd /opt/toolchains/dc
  * To compile an example & send the .elf to your broadband adapter: something like:
    * cd /opt/toolchains/dc/kos/examples/dreamcast/hello
    * make
    * dc-tool-ip -t 192.168.1.200 -x hello.elf
  * When you have finished working with your codespace, click on the green "Code" button again, and on the 3 dots next to your codespace to stop your container from running. This will save you some free execution minutes (default idle timeout is 30 minutes).

# Notes:
* This is just a simple test & could be improved a lot, eg by:
  * including (regular) gcc & dc-tool-ip in the docker image
  * trying to keep the docker image as small as possible, and/or use several separate images

# Thanks:
* To Kazade for [providing the Docker image](https://hub.docker.com/r/kazade/dreamcast-sdk/) !
* To Sizious for [adding a Dockerfile to Kos](https://github.com/KallistiOS/KallistiOS/blob/master/utils/dc-chain/docker/stable/Dockerfile)
