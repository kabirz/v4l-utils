if WITH_DYN_LIBV4L
lib_LTLIBRARIES = libv4lconvert.la
if HAVE_LIBV4LCONVERT_HELPERS
libv4lconvertpriv_PROGRAMS = ov511-decomp ov518-decomp
endif
include_HEADERS = ../include/libv4lconvert.h
pkgconfig_DATA = libv4lconvert.pc
LIBV4LCONVERT_VERSION = -version-info 0
else
noinst_LTLIBRARIES = libv4lconvert.la
endif

libv4lconvert_la_SOURCES = \
  libv4lconvert.c tinyjpeg.c sn9c10x.c sn9c20x.c pac207.c  mr97310a.c \
  flip.c crop.c jidctflt.c spca561-decompress.c \
  rgbyuv.c sn9c2028-decomp.c spca501.c sq905c.c bayer.c nv12_16l16.c \
  stv0680.c cpia1.c se401.c jpgl.c jpeg.c jl2005bcd.c \
  control/libv4lcontrol.c control/libv4lcontrol.h control/libv4lcontrol-priv.h \
  processing/libv4lprocessing.c processing/whitebalance.c processing/autogain.c \
  processing/gamma.c processing/libv4lprocessing.h processing/libv4lprocessing-priv.h \
  helper-funcs.h libv4lconvert-priv.h libv4lsyscall-priv.h \
  tinyjpeg.h tinyjpeg-internal.h
if HAVE_JPEG
libv4lconvert_la_SOURCES += jpeg_memsrcdest.c jpeg_memsrcdest.h
endif
if HAVE_LIBV4LCONVERT_HELPERS
libv4lconvert_la_SOURCES += helper.c
endif
libv4lconvert_la_CPPFLAGS = $(CFLAG_VISIBILITY) $(ENFORCE_LIBV4L_STATIC)
libv4lconvert_la_LDFLAGS = $(LIBV4LCONVERT_VERSION) -lrt -lm $(JPEG_LIBS) $(ENFORCE_LIBV4L_STATIC)

ov511_decomp_SOURCES = ov511-decomp.c

ov518_decomp_SOURCES = ov518-decomp.c

EXTRA_DIST = Android.mk
