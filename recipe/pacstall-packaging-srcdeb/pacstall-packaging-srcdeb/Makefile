

REF_MAKEFILE_FILE_PATH := $(abspath $(lastword $(MAKEFILE_LIST)))
REF_BASE_DIR_PATH := $(abspath $(dir $(REF_MAKEFILE_FILE_PATH)))
REF_PLAN_DIR_PATH := $(REF_BASE_DIR_PATH)
REF_BUILD_DIR_PATH := $(REF_PLAN_DIR_PATH)/build
REF_DEBIAN_DIR_PATH := $(REF_PLAN_DIR_PATH)/debian
REF_MAIN_BIN_DIR_PATH := $(REF_PLAN_DIR_PATH)/bin


#PATH := $(REF_MAIN_BIN_DIR_PATH):$(PATH)




REF_SUBJECT_NAME="pacstall"
DESTDIR := $(REF_DEBIAN_DIR_PATH)/$(REF_SUBJECT_NAME)




default: build
.PHONY: default





help:
	@echo 'Usage:'
	@echo '	$$ make [action]'
	@echo
	@echo 'Ex:'
	@echo '	$$ make'
	@echo
	@echo '	$$ make help'
	@echo
	@echo '	$$ make deb-build-essential'
	@echo
	@echo '	$$ make deb-build-dep'
	@echo
	@echo '	$$ make deb-build'
	@echo
	@echo '	$$ make srcdeb-build'
	@echo
.PHONY: help




dump:
	@echo "REF_MAKEFILE_FILE_PATH=$(REF_MAKEFILE_FILE_PATH)"
	@echo "REF_BASE_DIR_PATH=$(REF_BASE_DIR_PATH)"
	@echo "REF_PLAN_DIR_PATH=$(REF_PLAN_DIR_PATH)"
	@echo "REF_BUILD_DIR_PATH=$(REF_BUILD_DIR_PATH)"
	@echo "REF_DEBIAN_DIR_PATH=$(REF_BUILD_DIR_PATH)"
	@echo "DESTDIR=$(DESTDIR)"
.PHONY: dump




build:
	REF_BUILD_DIR_PATH=$(REF_BUILD_DIR_PATH) ./build.sh
.PHONY: build


install:
	@echo "Make: DESTDIR=$(DESTDIR)"
	DESTDIR=$(DESTDIR) ./install.sh
.PHONY: install


clean:
	./clean.sh
.PHONY: clean




##
## ## changelog
##
## * [man 5 deb-changelog](https://manpages.debian.org/stable/dpkg-dev/deb-changelog.5.en.html)
## * [man 1 debchange](https://manpages.debian.org/stable/devscripts/debchange.1.en.html)
##

changelog-edit:
	debchange
.PHONY: changelog-edit


changelog-date:
	date -R
.PHONY: changelog-date


##
## `date -R`
##
## `date -d '2025-06-09 07:45:46' -R`
##




##
## ## deb packaging
##

deb-build-essential:
	sudo apt-get install -y git devscripts equivs
.PHONY: deb-build-essential


deb-build-dep:
	sudo mk-build-deps -i -t "apt-get -y" -r
.PHONY: deb-build-dep


deb-build:
	dpkg-buildpackage -b -uc -us -tc
.PHONY: deb-build


srcdeb-build:
	dpkg-buildpackage -uc -us -tc
.PHONY: srcdeb-build
