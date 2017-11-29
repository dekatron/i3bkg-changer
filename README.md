# i3bkg-changer

This script is intended for use with i3wm and feh

i3bkg-changer is a simple bash script intended to be used with cron or a simmlar job scheduler to periodically rotate your wallpaper in i3.

## Usage

Download or git clone the i3bkg-changer script.

Edit the script and set the location of the folder containing your background images in the BGFOLDERPATH variable

Place the script somewhere in your path (for example /bin/)

Finally add an entry to your job scheduler of choice to run the script at the desired interval.

## Systemd Service & Timer (Optional)

As an alternative to cron I have included a i3bkg-changer.service file that can be used to run i3bkg-changer as a systemd oneshot service.
There is also an i3bkg-changer.timer file that should be used to control the service.

The following instruction are for Arch linux and detials may vary for other operating systems.

Move or copy the 3bkg-changer.service and i3bkg-changer.timer files into the /etc/systemd/ directory
cd into the directory and execute the following:
```
sudo chmod 655 i3bkg-changer.*
sudo systemctl daemon-reload
sudo systemctl enable --now i3bkg-changer.timer
```

If you want to check that the timer is working correctly you can run the following:
```
watch systemctl list-timers --all
```
You should see the new timer listed and counting down the time until the next wallpaper rotation.
