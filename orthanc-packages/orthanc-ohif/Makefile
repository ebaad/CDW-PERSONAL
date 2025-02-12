#
# Overmakefile for orthanc-ohif source
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
all:	.built_ohif .built_binary

.built_ohif:
	mkdir -p Build
	cd Build && ../Resources/CreateOHIFDist.sh
	touch $@

.built_binary:
	cd Build && cmake $(CMAKE_ARGS)
	cd Build && make
	touch $@

install:	all
	cd Build && make install

clean clobber:
	@rm -rf Build
