# Robotgo

完整的README文件請參考[此處](README.md)

## [給初心者](https://stackoverflow.com/a/72424179/9935654)

> ⚠ 此段說明是專為**Windows**作業系統所寫

----

本套件需要安裝`MinGW`才可以用，不然可能會出現類似以下的錯誤

> #include "bitmap/goBitmap.h" ... fatal error: zlib.h: No such file or directory

若您不打算使用bitmap相關的功能，可以直接取消掉，不要編譯[bitmap.go](https://github.com/go-vgo/robotgo/blob/c466829/bitmap.go)這個檔案，在該文件的頭加上以下敘述即可

```
//go:build ignore
```

### [安裝MinGW](https://stackoverflow.com/a/72424179/9935654) [^MinGW]

主要就是要有`gcc`, `g++`，但不是所有版本的gcc, g++都可以，建議裝以下的版本

[前往sourceforge](https://sourceforge.net/projects/mingw-w64/files/)

選擇您想要的

- version:{..., `8.1.0`, `7.3.0`, `6.4.0`, `5.4.0`, ...}
- arch. : `x86_64`, [i686](https://en.wikipedia.org/wiki/P6_(microarchitecture))<sup>similarly `x86`</sup>
- [threads](https://stackoverflow.com/q/17242516/9935654): `posix`, `win32`
- [exception](https://stackoverflow.com/q/15670169/9935654): `sjlj`, `dwarf`, `seh`

[![download MinGW-W64][1]][1]

以下以[x86_64-win32-seh](https://nchc.dl.sourceforge.net/project/mingw-w64/Toolchains%20targetting%20Win64/Personal%20Builds/mingw-builds/8.1.0/threads-win32/seh/x86_64-8.1.0-release-win32-seh-rt_v6-rev0.7z)<sup>8.1.0</sup>為例子
<sub>👉 [其他下載連結](https://github.com/CarsonSlovoka/robotgo/releases/download/assets/x86_64-8.1.0-release-win32-seh-rt_v6-rev0.7z)</sub>

您下載完之後

1. 解壓文件.
2. 複製路徑 `C:\downloads\x86_64-8.1.0-release-win32-seh-rt_v6-rev0\mingw64\bin` (which contains: `gcc.exe`, `g++.exe`)
3. set go env: `CC`, `CXX`

- `go env -w CC=C:\downloads\x86_64-8.1.0-release-win32-seh-rt_v6-rev0\mingw64\bin\gcc`  (最後的gcc其實就代表gcc.exe, .exe可以不用寫)
- `go env -w CXX=C:\downloads\x86_64-8.1.0-release-win32-seh-rt_v6-rev0\mingw64\bin\g++`

  再次使用`go env`可以發現`CC`和`CXX`已經被修改了

  或者直接`go env CC, CXX`列出我們所關心的這兩個項目就好

  預設的CC和CXX應該是

    ```
    CC=gcc
    CXX=g++
    ```

最後，再次嘗試`go build`應該就可以成功編譯了

#### 參考資料

- [robotgo/issues/100](https://github.com/go-vgo/robotgo/issues/100)


## robotgo學習

請參考examples的資料夾，會推薦參考tag的examples資料夾，因為您得到的版本應該也是以tag的為主，所以看該tag的資料夾才是比較準確的

- https://github.com/CarsonSlovoka/robotgo/tree/v0.100.10/examples
- https://github.com/go-vgo/robotgo/blob/master/examples



[^MinGW]: MinGW全稱: Minimalist GNU on Windows



[robotgo]: https://github.com/go-vgo/robotgo
[1]: https://i.stack.imgur.com/j1441.png
