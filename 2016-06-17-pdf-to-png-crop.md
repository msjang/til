
```
pdftoppm -f 4 -singlefile -png A.pdf > A-page-04.png
convert A-page-04.png -crop 1050x360+150+235 A-page-04-crop.png # [X]x[Y]+[Xoffset]+[Yoffset]
```

