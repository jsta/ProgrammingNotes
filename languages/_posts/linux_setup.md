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
| **stop gedit backup file creation:** | `gsettings set org.gnome.gedit.preferences.editor create-backup-copy 'false'` |
| **Firefox extensions** | _noscript, privacy badger, https everywhere_, _dark reader_ |

3. Copy files from backup with `rsync`

4. install out-of-the-box basics

`sudo apt-get install git git-extras xclip vim okular evolution pandoc pandoc-citeproc gimp p7zip-full`

5. ssh keys + connect to github

   - [create new ssh key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
   - paste to clipboard with `xclip -sel clip < ~/.ssh/id_rsa.pub`
   - At github, settings -> ssh and gpg keys -> New SSH key

7. pull dotfiles repo

   https://github.com/jsta/dotfiles

11. install must-haves

    - zotero
    - conda
    - docker    
    - vscodium
    - chrome    
    - pdftk

9. make Okular the pdf default
    
      - Open folder and right click on a PDF
      - Select Properties and then the "Open With" tab
      - Choose okular and click "Set default"

5. install [keepassXC](https://keepassxc.org/download/)

    ```
    sudo apt install keepassxc
    ```
  
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
    
38. Install peek (screen recording)

    ```
    sudo add-apt-repository ppa:peek-developers/stable
    sudo apt update
    sudo apt install peek
    ```

46. Install [Corebird](https://corebird.baedert.org/), twitter client

    - Just used _Pop shop_ (the software installer for
      [Pop!_OS](http://pop.system76.com/docs)

</details>
