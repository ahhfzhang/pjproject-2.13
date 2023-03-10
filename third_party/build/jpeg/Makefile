include ../../../build.mak
include ../../../build/common.mak

export LIBDIR := ../../lib

RULES_MAK := $(PJDIR)/build/rules.mak

export JPEG_LIB := libjpeg-$(TARGET_NAME)$(LIBEXT)

ifeq ($(PJ_SHARED_LIBRARIES),)
else
export JPEG_SONAME := libjpeg.$(SHLIB_SUFFIX)
export JPEG_SHLIB := $(JPEG_SONAME).$(PJ_VERSION_MAJOR)
endif

###############################################################################
# Gather all flags.
#
export _CFLAGS 	:= $(CC_CFLAGS) $(OS_CFLAGS) $(HOST_CFLAGS) $(M_CFLAGS) \
		   $(CFLAGS) $(CC_INC). $(CC_INC)../../jpeg \
		   $(CC_INC)../../../pjlib/include
export _CXXFLAGS:= $(CC_CXXFLAGS) $(OS_CXXFLAGS) $(M_CXXFLAGS) \
		   $(HOST_CXXFLAGS) $(CXXFLAGS) $(_CFLAGS)
export _LDFLAGS := $(CC_LDFLAGS) $(OS_LDFLAGS) $(M_LDFLAGS) $(HOST_LDFLAGS) \
		   $(LDFLAGS)

export JPEG_SRCDIR = ../../jpeg
export JPEG_OBJS = \
	jdinput.o \
	jccoefct.o \
	jsimd_none.o \
	jcinit.o \
	jdapimin.o \
	jcicc.o \
	jdmaster.o \
	jdatasrc.o \
	transupp.o \
	jutils.o \
	jchuff.o \
	wrppm.o \
	jdpostct.o \
	jidctfst.o \
	jpegtran.o \
	jdatasrc-tj.o \
	jidctred.o \
	cjpeg.o \
	jfdctint.o \
	jdmerge.o \
	jdcolor.o \
	jcomapi.o \
	jdapistd.o \
	jcprepct.o \
	jdarith.o \
	jdatadst-tj.o \
	jcarith.o \
	jfdctflt.o \
	jmemmgr.o \
	turbojpeg.o \
	jmemnobs.o \
	djpeg.o \
	tjexample.o \
	jdmarker.o \
	jerror.o \
	jdmainct.o \
	rdswitch.o \
	cdjpeg.o \
	jdtrans.o \
	jddctmgr.o \
	jcmarker.o \
	rdppm.o \
	wrgif.o \
	jcdctmgr.o \
	wrtarga.o \
	tjutil.o \
	jdicc.o \
	jcapistd.o \
	jdatadst.o \
	jcstest.o \
	rdjpgcom.o \
	rdtarga.o \
	jcapimin.o \
	rdcolmap.o \
	jfdctfst.o \
	jcmainct.o \
	jctrans.o \
	jdcoefct.o \
	jquant1.o \
	rdgif.o \
	jcsample.o \
	jquant2.o \
	jidctint.o \
	jcparam.o \
	rdbmp.o \
	jcphuff.o \
	jaricom.o \
	jcmaster.o \
	jdhuff.o \
	wrjpgcom.o \
	strtest.o \
	jccolor.o \
	tjbench.o \
	jdsample.o \
	jidctflt.o \
	jdphuff.o \
	wrbmp.o


export JPEG_CFLAGS = $(_CFLAGS)
export JPEG_CXXFLAGS = $(_CXXFLAGS)


export CC_OUT CC AR RANLIB HOST_MV HOST_RM HOST_RMDIR HOST_MKDIR OBJEXT LD LDOUT 
###############################################################################
# Main entry
#
# $(TARGET) is defined in os-$(OS_NAME).mak file in current directory.
#
TARGETS := $(JPEG_LIB) $(JPEG_SONAME)

all: $(TARGETS)

doc:
	cd .. && doxygen docs/doxygen.cfg

dep: depend
distclean: realclean

.PHONY: all dep depend clean realclean distclean
.PHONY: $(TARGETS)
.PHONY: $(JPEG_LIB) $(JPEG_SONAME)

libjpeg: $(JPEG_LIB)
$(JPEG_SONAME): $(JPEG_LIB)
$(JPEG_LIB) $(JPEG_SONAME):
	$(MAKE) -f $(RULES_MAK) APP=JPEG app=libjpeg $(subst /,$(HOST_PSEP),$(LIBDIR)/$@)

clean print_lib:
	$(MAKE) -f $(RULES_MAK) APP=JPEG app=libjpeg $@

realclean:
	$(subst @@,$(subst /,$(HOST_PSEP),.jpeg-$(TARGET_NAME).depend),$(HOST_RMR))
	
	$(MAKE) -f $(RULES_MAK) APP=JPEG app=libjpeg $@

depend:
	$(MAKE) -f $(RULES_MAK) APP=JPEG app=libjpeg $@


