# The HFS Environment variable needs to be set before calling make
# Windows users should also define their MSVCDir environnment variable

include ../CustomGLTF.global

DSONAME = $(ROPLIB).$(EXT)

# Custom GLTF library
GHEADER = "../GLTF"
GLIB = "../GLTF"

SOURCES = \
	ROP_GLTF.C \
    ROP_GLTF_ExportRoot.C \
    ROP_GLTF_Image.C \
    ROP_GLTF_Refiner.C

INCDIRS = \
    -I$(GHEADER) \
    -I$(HFS)/toolkit/include

ifdef WINDOWS
LIBDIRS += -LIBPATH:$(GLIB)
LIBS += lib$(GLTFLIB).lib
else
LIBDIRS += -L$(GLIB)
LIBS += -l$(GLTFLIB)
endif

include $(HFS)/toolkit/makefiles/Makefile.gnu

HDEFINES += \
	-DGLTF_EXPORTS \
	-DGLTF_NAMESPACE=$(GLTFNAMESPACE) \
	-DCUSTOM_GLTF_TOKEN_PREFIX='$(TOKEN_PREFIX)' \
	-DCUSTOM_GLTF_LABEL_PREFIX='$(LABEL_PREFIX)'
