# suckless
My suckless DWM setup and ricing

# Pre-requistes
    1. sudo apt update; sudo apt upgrade
    2. sudo apt install build-essential stterm suckless-tools libx11-dev libxinerama-dev libxft-dev sharutils dwm
    3. sudo apt install wget curl compton feh 
    4. sudo apt-get install xserver-xorg-input-synaptics (optional if your
       touchpad is not working like `tap to click` and `scroll`)

# Go to suckless directory and clone the below the repos 
NOTE: I kept my suckless inside <b>~/.config/suckless/</b> inside config directory
    1. git clone depth=1 https://git.suckless.org/dwm
    2. git clone depth=1 https://git.suckless.org/st 
    3. git clone depth=1 https://git.suckless.org/slstatus
    4. git clone depth=1 https://git.suckless.org/dmenu
    
    <br>
    <h2> Once you are done with cloning of all the repose,Please go inside all
    the directory use the below command to install it.</h2>
    </br>
    <br>
    <ul> <p> Command </p>
    <li> 1. rm config.h </li>
    <li> 2. sudo make clean install </li>
    </ul>
    </br>

    <p> we also apply some patches, To do that please follow steps </p>
    <ul> Step for patches:
    <li> 1. Create a directory called patches inside <b>dwm,st, slstatus or
    dmenu.</b></li>
    <li> 2. Go inside the patches and download the which ever you want from dwm
    site. </li>
    <li> 3. To apply the patches go the respesctive directory like dwm, st,
    slstatus or dmenu and use the command <b> patch -p1 < patches/your-patch-name.diff</b>
    <li> 4. If you success then enjoy if not the please check all .rej file and
    fix it by comparing with actual file.</li>

# Create .xinitrc
    1. cd ~
    2. echo "exec dwm" >> .xinitrc // Will modify this later

# Create dwm.desktop inside (/usr/share/xsessions/dwm.desktop)
    [Desktop Entry]
    Encoding=UTF-8
    Name=DWM
    Comment=Dynamic window manager
    Exec=/home/<User>/.config/suckless/dwm/dwm // replace the User with your username
    Icon=dwm
    Type=XSession

    [X-Window Manager]
    SessionManaged=true

# Scripts uses
    1. We will use the scripts to make status bar look little pritty, use below
       command to apply the changes
       - Go to scripts directory
       - chmod +x *
       - cp -ar dwm-iconbar wal /usr/local/bin/  // if you can put others scripts as well.

# Create autostart file
    1. cd ~
    2. mkdir .dwm
    3. cd .dwm
    4. vim autostart.sh 
    5. Paste below lines and save it
    
        # setting screen size
        xrandr -s 1920x1080 &

        # set wallpaper
        feh --bg-scale ~/Downloads/wallpaper-master/first-collection/ubuntu-1.png &

        # set transparency
        compton &

        # dwm-iconbar
        dwm-iconbar &

        # setting slstatus
        #~/.config/suckless/slstatus/slstatus &

        # setting st
        ~/.config/suckless/st/st &


    



