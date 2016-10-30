```
$ echo $LANG
ko_KR.UTF-8

$ sudo apt-get update
무시 http://dl.google.com stable InRelease
기존 http://dl.google.com stable Release.gpg 
무시 http://packages.linuxmint.com rafaela InRelease
기존 http://dl.google.com stable Release 
...


$ LANG=en_US.UTF-8

$ sudo apt-get update
Ign http://dl.google.com stable InRelease
Ign http://pkg.jenkins-ci.org binary/ InRelease
Hit http://dl.google.com stable Release.gpg 
Ign http://packages.linuxmint.com rafaela InRelease
...
```
