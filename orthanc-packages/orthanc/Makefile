#
# Overmakefile for orthanc source for 1.12.6 branch.
#
ifeq ($(INSTALL_ROOT),)
$(error INSTALL_ROOT not set)
endif
CMAKE_ARGS= -DCMAKE_INSTALL_PREFIX=$(INSTALL_ROOT) -DALLOW_DOWNLOADS=ON -DUSE_GOOGLE_TEST_DEBIAN_PACKAGE=ON -DUSE_SYSTEM_CIVETWEB=OFF -DDCMTK_LIBRARIES=dcmjpls -DCMAKE_BUILD_TYPE=Release ../OrthancServer/

#
# Note that the submake usage explicitly uses make- not $(MAKE)
#
all:	Build/Orthanc

Build/Orthanc:
	mkdir -p Build
	cd Build && cmake $(CMAKE_ARGS)
	cd Build && make

install:	all
	cd Build && make install

clean clobber:
	@rm -rf Build
