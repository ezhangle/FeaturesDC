#
#  There exist several targets which are by default empty and which can be 
#  used for execution of your targets. These targets are usually executed 
#  before and after some main targets. They are: 
#
#     .build-pre:              called before 'build' target
#     .build-post:             called after 'build' target
#     .clean-pre:              called before 'clean' target
#     .clean-post:             called after 'clean' target
#     .clobber-pre:            called before 'clobber' target
#     .clobber-post:           called after 'clobber' target
#     .all-pre:                called before 'all' target
#     .all-post:               called after 'all' target
#     .help-pre:               called before 'help' target
#     .help-post:              called after 'help' target
#
#  Targets beginning with '.' are not intended to be called on their own.
#
#  Main targets can be executed directly, and they are:
#  
#     build                    build a specific configuration
#     clean                    remove built files from a configuration
#     clobber                  remove all built files
#     all                      build all configurations
#     help                     print help mesage
#  
#  Targets .build-impl, .clean-impl, .clobber-impl, .all-impl, and
#  .help-impl are implemented in nbproject/makefile-impl.mk.
#
#  Available make variables:
#
#     CND_BASEDIR                base directory for relative paths
#     CND_DISTDIR                default top distribution directory (build artifacts)
#     CND_BUILDDIR               default top build directory (object files, ...)
#     CONF                       name of current configuration
#     CND_PLATFORM_${CONF}       platform name (current configuration)
#     CND_ARTIFACT_DIR_${CONF}   directory of build artifact (current configuration)
#     CND_ARTIFACT_NAME_${CONF}  name of build artifact (current configuration)
#     CND_ARTIFACT_PATH_${CONF}  path to build artifact (current configuration)
#     CND_PACKAGE_DIR_${CONF}    directory of package (current configuration)
#     CND_PACKAGE_NAME_${CONF}   name of package (current configuration)
#     CND_PACKAGE_PATH_${CONF}   path to package (current configuration)
#
# NOCDDL


# Environment 
MKDIR=mkdir
CP=cp
CCADMIN=CCadmin
PATH_TO_ROOT=../../../
PATH_TO_BUILD=../../../build

# bin
OUTPUT_FILE_NAME=DCPlusPlus
OUTPUT_FILE_NAME_STRIP=DCPlusPlus_stripped
OUTPUT_FILE_EXT_E=.exe
OUTPUT_FILE_EXT_S=.pdb

# dependencies 
PATH_DEP_CSHELP=../../../src/help/cshelp.h

# build
build: .build-post

.build-pre: .check-exist .gpch
	
.check-exist:
	@if [ ! -f $(PATH_DEP_CSHELP) ]; then \
	    echo "generate cshelp.h ..."; \
	    if [ $(shell echo $(CND_PLATFORM_${CONF}) | sed -r 's/(\S{5}).*/\L\1/') = 'mingw' ] ; then \
	        sh cshelp.sh; \
	    else \
	        cmd //c start "cshelp.bat"; \
	    fi; \
	fi;

.gpch:	
	@if [ $(shell echo ${CONF} | sed -r 's/(\S{5}).*/\L\1/') = 'pch__' ] ; then \
	    ${MAKE} -f nbproject/Makefile-${CONF}.mk "stdafx.h.gch"; \
	fi;

.build-post: .build-impl
	strip --only-keep-debug $(PATH_TO_BUILD)/_bin_/${CONF}/$(OUTPUT_FILE_NAME)$(OUTPUT_FILE_EXT_E) -o $(PATH_TO_BUILD)/_bin_/${CONF}/$(OUTPUT_FILE_NAME)$(OUTPUT_FILE_EXT_S)
	strip $(PATH_TO_BUILD)/_bin_/${CONF}/$(OUTPUT_FILE_NAME)$(OUTPUT_FILE_EXT_E) -o $(PATH_TO_BUILD)/_bin_/${CONF}/$(OUTPUT_FILE_NAME_STRIP)$(OUTPUT_FILE_EXT_E)


# clean
clean: .clean-post
	rm -f $(PATH_TO_BUILD)/_bin_/${CONF}/$(OUTPUT_FILE_NAME)$(OUTPUT_FILE_EXT_S)
	rm -f $(PATH_TO_BUILD)/_bin_/${CONF}/$(OUTPUT_FILE_NAME_STRIP)$(OUTPUT_FILE_EXT_E)

.clean-pre:
# Add your pre 'clean' code here...

.clean-post: .clean-impl
	rm -f $(PATH_DEP_CSHELP)	

# clobber
clobber: .clobber-post

.clobber-pre:
# Add your pre 'clobber' code here...

.clobber-post: .clobber-impl
# Add your post 'clobber' code here...


# all
all: .all-post

.all-pre:
# Add your pre 'all' code here...

.all-post: .all-impl
# Add your post 'all' code here...


# build tests
build-tests: .build-tests-post

.build-tests-pre:
# Add your pre 'build-tests' code here...

.build-tests-post: .build-tests-impl
# Add your post 'build-tests' code here...


# run tests
test: .test-post

.test-pre: build-tests
# Add your pre 'test' code here...

.test-post: .test-impl
# Add your post 'test' code here...


# help
help: .help-post

.help-pre:
# Add your pre 'help' code here...

.help-post: .help-impl
# Add your post 'help' code here...



# include project implementation makefile
include nbproject/Makefile-impl.mk

# include project make variables
include nbproject/Makefile-variables.mk

# output paths
CND_DISTDIR=$(PATH_TO_BUILD)/$(PROJECTNAME)/dist
CND_BUILDDIR=$(PATH_TO_BUILD)/$(PROJECTNAME)/obj