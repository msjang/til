## 날짜 변경 및 확인

날짜 변경 (ubuntu)
```
sudo date --set "17 Feb 2016 19:23:47"
sudo date --set "18 Feb 2016 00:39:59"
```

날짜 확인 (ubuntu)
```
date --rfc-2822
Thu, 18 Feb 2016 08:49:36 +0900
```

날짜 확인 (osx)
```
date -u +"%Y-%m-%d %H:%M:%S"
2016-02-18 08:12:09
```

파일 날짜 확인 (osx)
```
ls -lT
total 96
-rw-r--r--@ 1 shuggie  staff    135  2 18 08:50:10 2016 2016-02-18-date.md
```