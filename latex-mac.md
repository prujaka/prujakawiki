#### Installation

Install mactex via homebrew:
`brew install mactex --cask`

Install texstudio via himebrew:
`brew install texstudio --cask`

#### Config migration

Go to texstudio config files:
`cd ~/.config/texstudio`

Copy `macros` folder to the `~/.config/texstudio/` of your new machine

Copy `texstudio.ini` to any location on the new machine, since you will only need to copy some lines from it to the new `texstudio.ini`

##### Macros migration

From your old `texstudio.ini` copy lines after the line `LogView\WarnIfFileSizeLargerMB=2` before the line `MainWindow\FullScreen=false`. They are all in alphabetical order so it's easy to search them and to not get lost. This will be all the lines starting with `Macros\` not including the line `Macros\RepositoryURL=https://api.github.com/repos/texstudio-org/texstudio-macro/contents/`, since it is the same in the new `texstudio.ini`. However, the `.ini` file of version 2.12.16 doesn't have the line `MacroEditor\LineWrap=false`, whereas the version 4.3.1 has, so paste all the copied lines right after it and before `Macros\RepositoryURL=https://api.github.com/repos/texstudio-org/texstudio-macro/contents/`.

Example of the old `.ini`:

```
LogView\WarnIfFileSizeLargerMB=2
Macros\0=Aligned, \\begin{aligned}\n    & %|\n\\end{aligned}, ,
Macros\1=\\left(\\right), \\left( %| \\right), ,
...
Macros\9=\\lambda, \\lambda, ,
Macros\RepositoryURL=https://api.github.com/repos/texstudio-org/texstudio-macro/contents/
```

Example of the new `.ini` before copying the macros lines:
```
LogView\WarnIfFileSizeLargerMB=2
MacroEditor\LineWrap=false
Macros\RepositoryURL=https://api.github.com/repos/texstudio-org/texstudio-macro/contents/
MainWindow\FullScreen=false
```

Example of the new `.ini` after copyting the macros lines:
```
LogView\WarnIfFileSizeLargerMB=2
MacroEditor\LineWrap=false
Macros\0=Aligned, \\begin{aligned}\n    & %|\n\\end{aligned}, ,
Macros\1=\\left(\\right), \\left( %| \\right), ,
...
Macros\9=\\lambda, \\lambda, ,
Macros\RepositoryURL=https://api.github.com/repos/texstudio-org/texstudio-macro/contents/
```

##### Keystroke migration

From your old `texstudio.ini` copy lines after the line `customIcons=@Variant(\0\0\0\b\0\0\0\0)` before the line `qttwp\address=`. This will be all the lines starting with `keysetting`. Then paste them to the new `texstudio.ini` between the `customIcons=@Variant(\0\0\0\b\0\0\0\0)` and the `qttwp\address=`.


Example of both old and new `.ini` keystroke lines:
```
customIcons=@Variant(\0\0\0\b\0\0\0\0)
keysetting\1\id=main/edit/lineoperations/moveLineUp~0
keysetting\1\key=Meta+Shift+Up
keysetting\10\id=main/latex/listenvironment/item~0
keysetting\10\key=
...
keysetting\9\id=main/latex/listenvironment/enumerate~0
keysetting\9\key=Ctrl+Shift+E
keysetting\size=27
qttwp\address=
```

##### Custom spell check words

Copy `en_US.ign` to `/Applications/texstudio.app/Contents/Resources`

Put `Spell\Language=en_US` to '.ini' file

##### Other preferences
As for other preferences, you can copy them from the old `.ini` to the new one in the same manner.
