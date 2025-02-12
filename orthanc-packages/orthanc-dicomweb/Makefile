#
# Overmakefile for orthanc-dicomweb source
#
# Builds off of orthanc 1.12.5 source.
#
ifeq ($(INSTALL_ROOT),)
$(error INSTALL_ROOT not set)
endif
CMAKE_ARGS= .. -DCMAKE_INSTALL_PREFIX=$(INSTALL_ROOT) -DSTATIC_BUILD=ON -DCMAKE_BUILD_TYPE=Release

#
# Note that the submake usage explicitly uses make- not $(MAKE)
#
all:	Build/libOrthancDicomWeb.so.1.18

Build/libOrthancDicomWeb.so.1.18:
	mkdir -p Build
	cd Build && cmake $(CMAKE_ARGS)
	cd Build && make

install:	all
	cd Build && make install

clean clobber:
	@rm -rf Build
