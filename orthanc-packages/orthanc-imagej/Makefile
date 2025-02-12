#
# Overmakefile for orthanc-imagej source
#
ifeq ($(INSTALL_ROOT),)
$(error INSTALL_ROOT not set)
endif

#
# Note that the submake usage explicitly uses make- not $(MAKE)
#
all:
	@true

install:	all
	install -D -m 644  Orthanc_Import.jar ${INSTALL_ROOT}/usr/share/imagej/plugins/Orthanc_Import.jar
	cd $(INSTALL_ROOT)/usr/share/imagej/plugins && rm -f Orthanc_Import_json-simple.jar && ln -s ../../java/json-simple.jar Orthanc_Import_json-simple.jar

clean clobber:
	@true
