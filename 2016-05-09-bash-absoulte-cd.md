# absolute cd

change working dir with real path

```
function CD {
	cd $(readlink -f $*)
}
```

```
$ cd ~/Dropbox
$ CD .
$ pwd
/hdd01/Dropbox
```
