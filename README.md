# To launch in your Web Browser a Visual Studio Code session that can compile for Dreamcast:
* Click on the green "Code" button
* Select the "Codespaces" Tab
* Click on "Create codespace on main"
  * <img src="/img/create_codespace.png" alt="Create codespace on main" width="25%" height="25%" title="Create codespace on main">
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
  * To compile an example & send the .elf to your broadband adapter (BBA): something like:
    * cd /opt/toolchains/dc/kos/examples/dreamcast/hello
    * make
    * dc-tool-ip -t 192.168.1.200 -x hello.elf
      * (with 192.168.1.200 being the ip address of the BBA)
      * Notes:
        * By default, Codespaces can only access the BBA if it is reachable via the internet (ie, addresses like 192.168.0.xxx, 192.168.1.xxx or 10.0.0.xxx, ... are not reachable)
        * If you want Codespaces to be able to access the BBA when it is only reachable via your internal network, [check this link](https://docs.github.com/en/codespaces/developing-in-codespaces/connecting-to-a-private-network)
  * When you have finished working with your codespace, click on the green "Code" button again, and on the 3 dots next to your codespace to stop your container from running. This will save you some free execution minutes (default idle timeout is 30 minutes).

# Notes:
* This is just a simple test & could be improved a lot, eg by:
  * including (regular) gcc, dc-tool-ip, gdb, ... in the docker image
  * trying to keep the docker image as small as possible, and/or use several separate images
  * automate the building of the toolchain / kos on a regular base, and put that in docker image(s), to benefit from the latest changes
  * adding extra VSCode configuration
* If you want to use Codespaces in your own github repository, just
  * add a ".devcontainer" folder, with
    * at least a "devcontainer.json" file,
    * (optionally, a Dockerfile if you want to specify your commands to build a container, instead of using a pre-built Docker image)

# Thanks:
* To Kazade for [providing the Docker image](https://hub.docker.com/r/kazade/dreamcast-sdk/) !
* To Sizious for [adding a Dockerfile to Kos](https://github.com/KallistiOS/KallistiOS/blob/master/utils/dc-chain/docker/stable/Dockerfile)
