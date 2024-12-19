## [DevelopersGuide](https://xcb.freedesktop.org/DevelopersGuide/): moduleがどのように開発されているか知る

1. Downloadings
2. Build
	- shell script didn't work. Error: `aclocal: error: couldn't open directory 'm4': No such file or directory`
	- とりあえず深刻な問題ではないので、無視するのが賢明か
	- インストールする時にm4のエラーが出るmoduleは除外してダウンロードする
	-  The `-n` option allows the build script to continue the build with the next module
	- X libraries are in `$PREFIX/lib`
	- X client programs are in `$PREFIX/bin`