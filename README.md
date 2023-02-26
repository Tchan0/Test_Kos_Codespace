# To launch in your Web Browser a Visual Studio Code session that can compile for Dreamcast:
* Click on the green "Code" button
* Select the "Codespaces" Tab
* click on "studious invention"

# This will launch Visual Studio Code in the browser, with:
* the sh-elf/arm compilers available in the terminal,
* the kos environ.sh sourced,
* dc-tool-ip installed

# Tips:
  * To add the Kos examples to your VSCode workspace:
    * code -a /opt/toolchains/dc/kos/examples
  * To go to the kos folder:
    * cd /opt/toolchains/dc
  * To send the .elf to your broadband adapter: something like:
    * dc-tool-ip -t 192.168.1.200 -x main.elf
  * When you have finished working with your codespace, click on the green "Code" button again, and on the 3 dots next to your codespace to stop your container from running. This will save you some free execution minutes (default idle timeout is 30 minutes).
  
# Thanks:
* To Kazade for [providing the Docker image](https://hub.docker.com/r/kazade/dreamcast-sdk/) !
* To Sizious for [adding a Dockerfile to Kos](https://github.com/KallistiOS/KallistiOS/blob/master/utils/dc-chain/docker/stable/Dockerfile)
