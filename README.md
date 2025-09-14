# 
# How to host C/C++ code with this Makefile-System
    1,Clone this repo : 
          git clone https://github.com/FoxInTango/Makefile.git ${Your project name}
    2,Modify the .make/config file :
          define the OUTPUT NAME : TARGET_NAME = ${YOUR Project Name}
          define the OUTPUT TYPE : 
              TARGET_TYPE_BIN = $(MK_TRUE | MK_FALSE)      build as executeable
              TARGET_TYPE_LIB = $(MK_TRUE | MK_FALSE)      build static  library
              TARGET_TYPE_DLL = $(MK_TRUE | MK_FALSE)      build dynamic library
          define the source file dir as below : 
              CONFIG_SOURCE_ROOT_DIRS    += ${source dir 1}
              CONFIG_SOURCE_ROOT_DIRS    += ${source drr 2} 
              ...
          IF it's the root project (Not a depended project of other Makefile-System project),uncomment contents shown below:

          # [ROOT only] Path Configurations
          #HEADER_INSTALL_PATH      = ${MAKE_FILE_DIR}inc
          #BINARY_INSTALL_PATH      = ${MAKE_FILE_DIR}bin
          #LIBRARY_INSTALL_PATH     = ${MAKE_FILE_DIR}lib
          #DEPENDS_MODULE_PATH      = ${MAKE_FILE_DIR}modules
          #DEPENDS_LIBRARY_PATH     = ${MAKE_FILE_DIR}libraries
          #DEPENDS_TEMPLATE_PATH    = ${MAKE_FILE_DIR}templates
          #DEPENDS_APPLICATION_PATH = ${MAKE_FILE_DIR}applications
          #DEPENDS_THIRD_PATH       = ${MAKE_FILE_DIR}thirds

          #CONFIG_HEADER_SEARCH_DIRS  += -I${HEADER_INSTALL_PATH}  # DO NOT touch
          #CONFIG_LIBRARY_SEARCH_DIRS += -L${LIBRARY_INSTALL_PATH} # DO NOT touch

          # [ROOT only] export PATHES FOR SUBPROJECTS
          # export ROOT_MAKE_DIR        = $(MAKE_FILE_DIR)
          # export ROOT_MAKE_CONFIG_DIR = $(MAKE_FILE_DIR).make
