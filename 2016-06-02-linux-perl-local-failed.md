## perl: warning: Setting locale failed

http://ubuntuforums.org/showthread.php?t=1346581

```
$ crc32 a.sh 
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
	LANGUAGE = "en_US:en",
	LC_ALL = (unset),
	LC_PAPER = "ko_KR.UTF-8",
	LC_ADDRESS = "ko_KR.UTF-8",
	LC_MONETARY = "ko_KR.UTF-8",
	LC_NUMERIC = "ko_KR.UTF-8",
	LC_TELEPHONE = "ko_KR.UTF-8",
	LC_IDENTIFICATION = "ko_KR.UTF-8",
	LC_MEASUREMENT = "ko_KR.UTF-8",
	LC_TIME = "ko_KR.UTF-8",
	LC_NAME = "ko_KR.UTF-8",
	LANG = "en_US.UTF-8"
    are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").

ff21ac9a

$ locale-gen ko_KR.UTF-8 en_US.UTF-8
/usr/sbin/locale-gen: line 97: /var/lib/locales/supported.d/local: Permission denied

$ sudo locale-gen ko_KR.UTF-8 en_US.UTF-8
Generating locales...
  en_US.UTF-8... up-to-date
  ko_KR.UTF-8... done
Generation complete.

$ crc32 a.sh 
ff21ac9a
```