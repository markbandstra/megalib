#----------------------------------------------------------------
#
#  Makefile for MEGAlib 
#
#  Author: Andreas Zoglauer
#
#----------------------------------------------------------------



#----------------------------------------------------------------
# Definitions:
#

OBJS      = $(LB)/MGlobal.o \
						$(LB)/MAssert.o \
				 		$(LB)/MResponseMatrix.o \
						$(LB)/MResponseMatrixO1.o \
						$(LB)/MResponseMatrixO2.o \
						$(LB)/MResponseMatrixO3.o \
						$(LB)/MResponseMatrixO4.o \
						$(LB)/MResponseMatrixO5.o \
						$(LB)/MResponseMatrixO6.o \
						$(LB)/MResponseMatrixO7.o \
						$(LB)/MResponseMatrixO8.o \
						$(LB)/MResponseMatrixO9.o \
						$(LB)/MResponseMatrixO10.o \
						$(LB)/MResponseMatrixO11.o \
						$(LB)/MResponseMatrixO12.o \
						$(LB)/MResponseMatrixO13.o \
						$(LB)/MResponseMatrixO14.o \
						$(LB)/MResponseMatrixO15.o \
						$(LB)/MResponseMatrixO16.o \
						$(LB)/MResponseMatrixO17.o \
						$(LB)/MString.o \
						$(LB)/MStreamBuffer.o \
						$(LB)/MStreams.o \
						$(LB)/MFitFunctions.o \
						$(LB)/MInterface.o \
						$(LB)/MCSVFunctionLoader.o \
						$(LB)/MFile.o \
						$(LB)/MFileEvents.o \
						$(LB)/MFileEventsRawa.o \
						$(LB)/MFileEventsTra.o \
						$(LB)/MFileManager.o \
						$(LB)/MFileResponse.o \
						$(LB)/MFileInfo.o \
						$(LB)/MFileHistograms.o \
						$(LB)/MImage.o \
						$(LB)/MImage2D.o \
						$(LB)/MImage3D.o \
						$(LB)/MImageContainer.o \
						$(LB)/MMath.o \
						$(LB)/MPairEvent.o \
						$(LB)/MSystem.o \
						$(LB)/MJulianDay.o \
						$(LB)/MTokenizer.o \
						$(LB)/MConnection.o \
						$(LB)/MTransceiverTcpIp.o \
						$(LB)/MComptonEvent.o \
						$(LB)/MPhysicalEvent.o \
						$(LB)/MMuonEvent.o \
						$(LB)/MPhotoEvent.o \
						$(LB)/MUnidentifiableEvent.o \
						$(LB)/MParser.o \
						$(LB)/MFunction.o \
						$(LB)/MFunction2D.o \
						$(LB)/MFunction3D.o \
						$(LB)/MFunction3DSpherical.o \
						$(LB)/MVector.o \
						$(LB)/MPrelude.o \
						$(LB)/MTime.o \
						$(LB)/MTimer.o \
						$(LB)/MSettingsInterface.o \
						$(LB)/MSettings.o \
						$(LB)/MSettingsBasicFiles.o \
						$(LB)/MXmlData.o \
						$(LB)/MXmlNode.o \
						$(LB)/MXmlAttribute.o \
						$(LB)/MXmlDocument.o \


SOBJ = $(LB)/libCommonMisc.$(DLL)

#----------------------------------------------------------------
# Commands:
#

all: $(SOBJ)

link:
		@$(LINK) $(shell pwd)/inc/*.h $(IN)
		@rm -f $(IN)/LinkDef.h

clean:
		@rm -f src/*~
		@rm -f src/\#*
		@rm -f inc/*~
		@rm -f inc/\#*
		@rm -f *~
		@rm -f \#*
		@rm -f $(ROBJS) $(RCINT) $(OBJS) $(MOBJS)

#----------------------------------------------------------------
# Dependencies:
#

$(SOBJ): $(OBJS) 
	@echo "Linking $(subst $(LB)/,,$@) ..."
ifeq ($(ARCH),macosx)
	$(LD) $(SOFLAGS) $(OBJS) $(GLIBS) $(LIBS) -o $(SOBJ)
	$(LD) -bundle -undefined suppress -Wl,-x $(LDFLAGS) $^ $(GLIBS) $(LIBS) \
	   -o $(subst .$(DLL),.so,$@)
else
	@$(LD) $(LDFLAGS) $(SOFLAGS) $(OBJS) $(GLIBS) $(LIBS) -o $(SOBJ)
endif

$(OBJS): $(LB)/%.o: src/%.cxx inc/%.h
	@echo "Compiling $(subst src/,,$<) ..."
	@$(CXX) $(CXXFLAGS) -c $< -o $@

#
#----------------------------------------------------------------



