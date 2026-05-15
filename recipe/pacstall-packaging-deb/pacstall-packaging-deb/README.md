

# pacstall




## Subject

* [Source](#source)
* [Howto](#howto)
* [Pacscript](#pacscript)
* [Reference](#reference)




## Source

* pacstall / [master](https://github.com/pacstall/pacstall/tree/master)




## Howto

### help

``` sh
make help
```




## Pacscript

| deb-coffee |
| ---------- |
| [deb-coffee](https://github.com/samwhelp/deb-coffee) |
| [deb-coffee-maccity](https://github.com/samwhelp/deb-coffee-maccity) |
| [deb-coffee-wincity](https://github.com/samwhelp/deb-coffee-wincity) |
| [deb-coffee-fancy](https://github.com/samwhelp/deb-coffee-fancy) |
| [deb-coffee-gruvbox](https://github.com/samwhelp/deb-coffee-gruvbox) |
| [deb-coffee-grub](https://github.com/samwhelp/deb-coffee-grub) |
| [deb-coffee-sddm](https://github.com/samwhelp/deb-coffee-sddm) |




## Notice

run

``` sh
make deb-install 
```

show

```
sudo dpkg -i ./build/deb/pacstall.deb
Selecting previously unselected package pacstall.
(Reading database ... 289807 files and directories currently installed.)
Preparing to unpack ./build/deb/pacstall.deb ...
Unpacking pacstall (0.1.1) ...
dpkg: dependency problems prevent configuration of pacstall:
 pacstall depends on aptitude; however:
  Package aptitude is not installed.
 pacstall depends on jq; however:
  Package jq is not installed.

dpkg: error processing package pacstall (--install):
 dependency problems - leaving unconfigured
Processing triggers for man-db (2.13.1-1) ...
Errors were encountered while processing:
 pacstall
make: *** [Makefile:94: deb-install] Error 1
```

run to finish install

``` sh
sudo apt-get install -f
```




## Reference

* [pacstall.pacscript](https://github.com/pacstall/pacstall-programs/blob/master/packages/pacstall/pacstall.pacscript)
