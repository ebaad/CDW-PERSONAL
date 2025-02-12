#
#
#
ifeq ($(INSTALL_ROOT),)
$(error INSTALL_ROOT not set)
endif

#
# Order is probably not important
#
TOPTARGETS := all install
SUBDIRS := orthanc orthanc-dicomweb orthanc-gdcm orthanc-imagej orthanc-webviewer orthanc-ohif

$(TOPTARGETS): $(SUBDIRS)
$(SUBDIRS):
	@echo make arg is $(MAKECMDGOALS)
	$(MAKE) -C $@ $(MAKECMDGOALS)

.PHONY: $(TOPTARGETS) $(SUBDIRS)
