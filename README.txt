unlock logging watcher
======================

THIS PROGRAM IS TOTALLY EXPERIMENTAL

search in logfile for lock/unlock attemps and send a notification after unlock.
Also take cam pictures when unlock attempt is detected.
Shutdown after 10 bad attempts.

Uses a patched version of slock wich logs failed login attempt.
Now monitor also failed login attempts on console

This program looks at the log an take a webcam picture at each failed log
attempt.
it requires fswebcam package to make the capture.

This module also requires the 'python-systemd' package

config is stored in /etc/unlock_watcher.cfg

content of config::

    [user]
    name = toto

Installation
------------

Installation is a manual process::

    sudo cp unlock_watcher /usr/local/bin/
    sudo chmod +x /usr/local/bin/unlock_watcher
    sudo cp unlock_watcher.service /etc/systemd/system/
    sudo systemctl enable unlock_watcher
    sudo systemctl start unlock_watcher
