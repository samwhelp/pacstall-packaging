

REF_MAKEFILE_FILE_PATH := $(abspath $(lastword $(MAKEFILE_LIST)))
REF_BASE_DIR_PATH := $(abspath $(dir $(REF_MAKEFILE_FILE_PATH)))
REF_PLAN_DIR_PATH := $(REF_BASE_DIR_PATH)
REF_BUILD_DIR_PATH := $(REF_PLAN_DIR_PATH)/build
REF_DEBIAN_DIR_PATH := $(REF_PLAN_DIR_PATH)/debian
REF_MAIN_BIN_DIR_PATH := $(REF_PLAN_DIR_PATH)/bin


#PATH := $(REF_MAIN_BIN_DIR_PATH):$(PATH)




REF_SUBJECT_NAME="pacstall"
DESTDIR := $(REF_BUILD_DIR_PATH)/deb/$(REF_SUBJECT_NAME)




default: help
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
	@echo '	$$ make deb-build'
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
## ## deb packaging
##

deb-build-essential:
	sudo apt-get install -y git devscripts equivs
.PHONY: deb-build-essential


deb-build:
	./deb-build.sh
.PHONY: deb-build


deb-install:
	sudo dpkg -i ./build/deb/pacstall.deb
.PHONY: deb-install
