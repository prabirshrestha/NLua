
EXTRA_DIST =  

# Warning: This is an automatically generated file, do not edit!

if ENABLE_DEBUG
ASSEMBLY_COMPILER_COMMAND = dmcs
ASSEMBLY_COMPILER_FLAGS =  -noconfig -codepage:utf8 -warn:4 -optimize- -debug "-define:DEBUG;TRACE"
ASSEMBLY = bin/Debug/ConsoleTest.exe
ASSEMBLY_MDB = $(ASSEMBLY).mdb
COMPILE_TARGET = exe
PROJECT_REFERENCES =  \
	../Run/Debug/NLua.dll
BUILD_DIR = bin/Debug/

CONSOLETEST_EXE_MDB_SOURCE=bin/Debug/ConsoleTest.exe.mdb
CONSOLETEST_EXE_MDB=$(BUILD_DIR)/ConsoleTest.exe.mdb
CONSOLETEST_EXE_CONFIG_SOURCE=App.config
NLUA_DLL_SOURCE=../Run/Debug/NLua.dll
NLUA_DLL_MDB_SOURCE=../Run/Debug/NLua.dll.mdb
NLUA_DLL_MDB=$(BUILD_DIR)/NLua.dll.mdb
KERALUA_DLL_SOURCE=../Core/KeraLua/src/bin/Debug/KeraLua.dll
KERALUA_DLL_MDB_SOURCE=../Core/KeraLua/src/bin/Debug/KeraLua.dll.mdb
KERALUA_DLL_MDB=$(BUILD_DIR)/KeraLua.dll.mdb
KOPILUA_DLL_SOURCE=../Core/KopiLua/Bin/Debug/KopiLua.dll
KOPILUA_DLL_MDB_SOURCE=../Core/KopiLua/Bin/Debug/KopiLua.dll.mdb
KOPILUA_DLL_MDB=$(BUILD_DIR)/KopiLua.dll.mdb

endif

if ENABLE_RELEASE
ASSEMBLY_COMPILER_COMMAND = dmcs
ASSEMBLY_COMPILER_FLAGS =  -noconfig -codepage:utf8 -warn:4 -optimize+ "-define:TRACE"
ASSEMBLY = bin/Release/ConsoleTest.exe
ASSEMBLY_MDB = 
COMPILE_TARGET = exe
PROJECT_REFERENCES =  \
	../Run/Release/NLua.dll
BUILD_DIR = bin/Release/

CONSOLETEST_EXE_MDB=
CONSOLETEST_EXE_CONFIG_SOURCE=App.config
NLUA_DLL_SOURCE=../Run/Release/NLua.dll
NLUA_DLL_MDB=
KERALUA_DLL_SOURCE=../Core/KeraLua/src/bin/Release/KeraLua.dll
KERALUA_DLL_MDB=
KOPILUA_DLL_SOURCE=../Core/KopiLua/Bin/Release/KopiLua.dll
KOPILUA_DLL_MDB=

endif

AL=al
SATELLITE_ASSEMBLY_NAME=$(notdir $(basename $(ASSEMBLY))).resources.dll

PROGRAMFILES = \
	$(CONSOLETEST_EXE_MDB) \
	$(CONSOLETEST_EXE_CONFIG) \
	$(NLUA_DLL) \
	$(NLUA_DLL_MDB) \
	$(KERALUA_DLL) \
	$(KERALUA_DLL_MDB) \
	$(KOPILUA_DLL) \
	$(KOPILUA_DLL_MDB)  

BINARIES = \
	$(CONSOLETEST)  


RESGEN=resgen2
	
all: $(ASSEMBLY) $(PROGRAMFILES) $(BINARIES) 

FILES = \
	../tests/Entity.cs \
	../tests/TestLua.cs \
	Program.cs \
	Properties/AssemblyInfo.cs 

DATA_FILES = 

RESOURCES = 

EXTRAS = \
	App.config \
	consoletest.in 

REFERENCES =  \
	System \
	System.Core \
	System.Xml.Linq \
	System.Data \
	System.Xml

DLL_REFERENCES = 

CLEANFILES = $(PROGRAMFILES) $(BINARIES) 

include $(top_srcdir)/Makefile.include

CONSOLETEST_EXE_CONFIG = $(BUILD_DIR)/ConsoleTest.exe.config
NLUA_DLL = $(BUILD_DIR)/NLua.dll
KERALUA_DLL = $(BUILD_DIR)/KeraLua.dll
KOPILUA_DLL = $(BUILD_DIR)/KopiLua.dll
CONSOLETEST = $(BUILD_DIR)/consoletest

$(eval $(call emit-deploy-target,CONSOLETEST_EXE_CONFIG))
$(eval $(call emit-deploy-target,NLUA_DLL))
$(eval $(call emit-deploy-target,NLUA_DLL_MDB))
$(eval $(call emit-deploy-target,KERALUA_DLL))
$(eval $(call emit-deploy-target,KERALUA_DLL_MDB))
$(eval $(call emit-deploy-target,KOPILUA_DLL))
$(eval $(call emit-deploy-target,KOPILUA_DLL_MDB))
$(eval $(call emit-deploy-wrapper,CONSOLETEST,consoletest,x))


$(eval $(call emit_resgen_targets))
$(build_xamlg_list): %.xaml.g.cs: %.xaml
	xamlg '$<'

$(ASSEMBLY_MDB): $(ASSEMBLY)

$(ASSEMBLY): $(build_sources) $(build_resources) $(build_datafiles) $(DLL_REFERENCES) $(PROJECT_REFERENCES) $(build_xamlg_list) $(build_satellite_assembly_list)
	mkdir -p $(shell dirname $(ASSEMBLY))
	$(ASSEMBLY_COMPILER_COMMAND) $(ASSEMBLY_COMPILER_FLAGS) -out:$(ASSEMBLY) -target:$(COMPILE_TARGET) $(build_sources_embed) $(build_resources_embed) $(build_references_ref)
