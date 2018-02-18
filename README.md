# Termux-tools
PDF handling tools and other tools to be used with Termux
## Those simple scripts allow you to 2-up PDF files from any app on your device

### Install
Big thanks to [@tomty89](https://github.com/termux/termux-packages/issues/2150) for letting me know how to compile `psutils` in termux. 

#### Installing necessary packages

`pkg install python poppler ghostscript`

##### To compile psutils
`pkg install clang make perl` 

```
$ tar -xf /sdcard/Download/psutils.tar.gz                                          
$ cd psutils/
$ mkdir -p $PREFIX/local/share/man                                                 
$ make PERL=$PREFIX/bin/perl BINDIR=$PREFIX/local/bin INCLUDEDIR=$PREFIX/local/include MANDIR=$PREFIX/local/share/man/man1 -f Makefile.unix install
```
##### To get youtube-dl and ytdl working
```
pip3 install --upgrade youtube-dl 
pip3 install --upgrade mps-youtube 
```
#### Configure Termux's access to storage

run `termux-setup-storage`

#### Copy the files 

Save `termux-url-opener` and `termux-file-editor` to `~/bin` and run `chmod u+x ~/bin/termux-*`.  
Run `echo "export PATH=$PATH:/data/data/com.termux/files/usr/local/bin" >> ~/.bashrc` 

### Usage
Note: If asked to enter a filename by hand, don't forget to add the `.pdf` extension. The script will not work without it.
