## Linux setup

1. software update

   ```
   sudo apt update
   sudo apt list --upgradable
   sudo apt upgrade
   ```
   
2. configure base apps

|   |   |
| - | - |
| **Large text:** | _Settings -> Universal Access -> Large text_ |
| **[Large terminal font size](http://askubuntu.com/questions/157873/is-it-possible-to-change-the-terminal-font):** | _Edit -> Profile Preferences -> Font_ | 
| **stop terminal lock on ctrl-s:** | `echo "stty -ixon" >> ~/.bashrc` |
| **stop gedit backup file creation:** | `gsettings set org.gnome.gedit.preferences.editor create-backup-copy 'false'` |
| **Firefox extensions** | _noscript, privacy badger, https everywhere_, _dark reader_ |

3. install out-of-the-box basics

`sudo apt-get install git git-extras xclip vim okular evolution pandoc pandoc-citeproc gimp p7zip-full`

5. ssh keys + connect to github

   - [created new ssh key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
   - installed xclip with `sudo apt install xclip`
   - pasted to clipboard with `xclip -sel clip < ~/.ssh/id_rsa.pub`
   - At github, settings -> ssh and gpg keys -> New SSH key

6. install R

   - See [instructions at linuxconfig](https://linuxconfig.org/install-r-on-ubuntu-18-04-bionic-beaver-linux)

  - Install some packages: tidyverse, devtools
  - Needed `sudo apt install libcurl4-openssl-dev libssl-dev libxml2-dev libssh2-1-dev`

7. pull dotfiles repo

   https://github.com/jsta/dotfiles

8. Install RStudio

    - Download Ubuntu 16.04+ `.deb` file from
      <https://www.rstudio.com/products/rstudio/download>
    - `sudo dpkg -i rstudio*.deb`
    - error re `libjpeg62`
    - `sudo apt install libjpeg62`
    - Needed to zoom in to the greatest extent or all of the dialogs were tiny `Ctrl+`
   
11. install must-haves

    - zotero
    - python/conda
    - qgis 
    - grass

12. Copy files from backup with `rsync`

9. make Okular the pdf default
    
      - Open folder and right click on a PDF
      - Select Properties and then the "Open With" tab
      - Choose okular and click "Set default"

5. install [keepassXC](https://keepassxc.org/download/)

    ```
    sudo apt install keepassxc
    ```
13. install extras

    - chrome
    - vscodium
    - pdftk
  
---

<details/>
  <summary>kbroman extras</summary>

50. [autokey](https://github.com/autokey/autokey) is great, but after a day or so it seems to start
    using up 100% of a CPU. In short term, seems like I could just use
    a `cron` job to re-start it every evening.

    So I made a shell script with

    ```
    pkill autokey
    sleep 10
    autokey-gtk >& /dev/null &
    ```

    I then used `crontab -e` to add to my crontab file:

    ```
    0 2 * * * /bin/bash [path_to_shell_script]
    ```

30. Color picker, [gpick](http://www.gpick.org/)

    ```
    sudo apt install gpick
    ```

- Additional possible gnome extensions:
  - [Places status indicator](https://extensions.gnome.org/extension/8/places-status-indicator/)
  - [Pomodoro timer](http://gnomepomodoro.org/)

25. Additional packages

    - `gnome-tweak-tool`
    - `caffeine` (thought this didn't work initially, but there's no
      longer a little icon in the "panel"; rather it runs in the
      background and will turn off screen saver when there's an
      application in full screen mode)


26. Create a `start` script that acts like `open` on a Mac, as a
    little shell script that just calls `gnome-open` repeatedly for
    each command-line argument. Placed this in `~/.local/bin`

    ```
    #!/bin/bash

    for file in "$@"
    do
        gnome-open "$file"
    done
    ```


27. Get terminal to open at startup

    - Super key and type "Startup"
    - Click "Add"; for the command, use "`gnome-terminal`"
    - To start at a particular size and position, use like

      ```
      gnome-terminal --geometry 117x57+0+0
      ```
29. Download
    [moneydance](https://infinitekind.com/download-moneydance-personal-finance-software)

    - Available for linux as well as Mac :)
    - Downloaded `.deb` file; right click and "open" in chrome when it
      was done downloading, and it opened
      [Eddy](https://github.com/donadigo/eddy), a debian package
      installer.

34. Install a bunch more programms

    - `vlc` (video player)
    - `calibre` (organizes ebooks)
    - `autokey-gtk` (desktop automation)
    - `digikam` (organizing photos)
    
    35. Install npm and coffeescript

    - `sudo apt install npm`
    - `sudo npm install --global coffeescript`

    Also [`gistup`](https://github.com/mbostock/gistup):

    - `sudo npm install -g gistup`

38. Install peek (screen recording)

    ```
    sudo add-apt-repository ppa:peek-developers/stable
    sudo apt update
    sudo apt install peek
    ```

39. Install java 8 (there's a java 9, but Minecraft still needs 8)

    Followed the instructions at <http://www.webupd8.org/2012/09/install-oracle-java-8-in-ubuntu-via-ppa.html>

    ```
    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java8-installer
    sudo apt install oracle-java8-set-default
    ```

    Test that it's working:

    ```
    java -version
    javac -version
    ```

4. [Gnome extensions](https://extensions.gnome.org)

    - (Can install, uninstall, and configure extensions within browser)
    - [Clipboard indicator](https://extensions.gnome.org/extension/779/clipboard-indicator)
      (gives clipboard history)
    - [OpenWeather](https://extensions.gnome.org/extension/750/openweather/)
    - [Audio Switcher](https://extensions.gnome.org/extension/1092/audio-switcher/)
    - [system-monitor](https://extensions.gnome.org/extension/120/system-monitor/)
      (also needed `sudo apt install gir1.2-gtop-2.0`, and to log out
      and back in again)
    - [emoji selector](https://extensions.gnome.org/extension/1162/emoji-selector/_
      (also did `sudo apt install fonts-emojione`)
    - [gtile](https://extensions.gnome.org/extension/28/gtile/) (tile
      windows with a grid)
        - select window you want to resize
        - use Super-Enter (on number key pad) to open gtile
        - click one corner position and then the other on the grid
        - esc to exit
    - [hide activities button](https://extensions.gnome.org/extension/744/hide-activities-button/)
    - [Refresh wifi connections](https://extensions.gnome.org/extension/905/refresh-wifi-connections/)
      (adds a refresh button to the wifi connection dialog)
    - [Media player indicator](https://extensions.gnome.org/extension/55/media-player-indicator/)
    - [log out button](https://extensions.gnome.org/extension/1143/logout-button/)


46. Install [Corebird](https://corebird.baedert.org/), twitter client

    - Just used _Pop shop_ (the software installer for
      [Pop!_OS](http://pop.system76.com/docs)

51. VirtualBox and Windows + Office365
    See <https://www.extremetech.com/computing/198427-how-to-install-windows-10-in-a-virtual-machine>

    - Download Windows 10 from
      <https://www.microsoft.com/en-us/software-download/windows10ISO>
    - Download VirtualBox from
      <https://www.virtualbox.org/wiki/Downloads>
      - Add to `/etc/apt/sources.list`
      - Register Oracle public keys
      - `sudo apt install virtualbox-5.2`
      - `sudo apt install dkms`
    - Start `virtualbox`, create new Windows10 machine, adjust memory,
      disk size, connect to the windows ISO, and adjust display stuff
    - Then start the virtual machine to install windows10. I said I had
      no product key, chose Windows 10 Home edition, and said something
      like fresh install
    - The thing was deathly slow. Searched for solutions and found
      this: <http://blog.jdpfu.com/2012/09/14/solution-for-slow-ubuntu-in-virtualbox>

      - Followed these instructions, except for Network when I tried
        "Bridged" I didn't get a network connection so I switched back
        to the default "NAT" and that worked

      - Gave the machine 150 GB harddrive (dynamically sized) and 8192
        MB RAM. And went for 2 CPUs

      - Once windows was up and running, and changed the VM display to
        "scaled" and then within windows I changed the screen
        resolution to 1600x1200. Seems to work better.

    - Within Windows, installed Office365 (by going to office365.com
      and then logging in with my NetID from UW-Madison), R, Rtools,
      RStudio, and a bunch of R packages (devtools + tidyverse
      first)

    - Need to install "Guest additions". While the virtual box is
      running, you need the VirtualBox tool bar to be showing (it
      won't if you're using a "scaled" window, it seems). In the
      "Devices" menu there's an option to "insert guest additions
      CD". Then within windows, click on the CD and install the
      software.

    - Having installed the guest additions, you can share a linux
      folder with windows. First create a folder in your home
      directory that you will share. Then in VirtualBox settings, go
      to "Shared Folders" and right-click on "Machine Folders" and
      select "Add shared folder" and enter the path to the folder.

53. Install [gitg](http://gitx.frim.nl/), a git GUI similar to
    [gitx](http://gitx.frim.nl/) (which is Mac only)

    ```
    sudo apt install gitg
    ```

55. [Tunnelbear VPN](https://www.tunnelbear.com/blog/linux_support/)

    - `sudo apt install network-manager-openvpn-gnome`

    - `mkdir ~/.tunnelbear_config`

    - Grab [config
      files](https://s3.amazonaws.com/tunnelbear/linux/openvpn.zip)
      and unzip to the above `.tunnelbear_config` directory

    - Open Network settings; click plus sign by VPN and choose "Import
      from file"; find directory created above and select the file for
      the desired country. Add email address and tunnelbear password.
      Click "Add".

    - To start/stop: turn on/off VPN in network settings via status
      bar in top-right of display

    - To test:
        - [check your IP](https://bearsmyip.com/)
        - check for DNS leaks with "Extended test" at [dnsleaktest.com](https://www.dnsleaktest.com/)

</details>