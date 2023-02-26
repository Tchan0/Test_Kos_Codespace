# To launch in your Web Browser a Visual Studio Code session that can compile for Dreamcast:
* Click on the green "Code" button
* Select the "Codespaces" Tab
* click on "studious invention"

This will launch Visual Studio Code in the browser, with:
* the sh-elf/arm compilers available in the terminal,
* the kos environ.sh sourced,
* and dc-tool-ip installed

* Tip:
  * to go to the kos folder: cd /opt/toolchains/dc
  * to send the .elf to your broadband adapter: something like:
    * dc-tool-ip -t 192.168.1.200 -x main.elf
  
  
Thanks to Kazade for providing the Docker image !
