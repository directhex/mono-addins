
KEY_FILE=$(top_srcdir)/mono-addins.snk
ASSEMBLY_COMPILER_COMMAND = gmcs
ASSEMBLY_COMPILER_FLAGS = -keyfile:$(KEY_FILE) -noconfig -codepage:utf8 -warn:4 -debug -d:DEBUG
ASSEMBLY = ../bin/Mono.Addins.Setup.dll
ASSEMBLY_NAME=Mono.Addins.Setup
COMPILE_TARGET = library
PC_FILES_IN = mono-addins-setup.pc.in
PROJECT_REFERENCES = ../bin/Mono.Addins.dll
BUILD_DIR = ../bin

	
all: $(ASSEMBLY)

FILES =  \
	AssemblyInfo.cs \
	Mono.Addins.Setup.ProgressMonitoring/ConsoleProgressMonitor.cs \
	Mono.Addins.Setup.ProgressMonitoring/LogTextWriter.cs \
	Mono.Addins.Setup.ProgressMonitoring/NullProgressMonitor.cs \
	Mono.Addins.Setup.ProgressMonitoring/ProgressStatusMonitor.cs \
	Mono.Addins.Setup.ProgressMonitoring/ProgressTracker.cs \
	Mono.Addins.Setup/AddinInfo.cs \
	Mono.Addins.Setup/AddinInfoCollection.cs \
	Mono.Addins.Setup/AddinPackage.cs \
	Mono.Addins.Setup/AddinPropertyCollection.cs \
	Mono.Addins.Setup/AddinRepositoryEntry.cs \
	Mono.Addins.Setup/AddinStore.cs \
	Mono.Addins.Setup/AddinSystemConfiguration.cs \
	Mono.Addins.Setup/AddinSystemConfigurationReaderWriter.cs \
	Mono.Addins.Setup/AddinSystemConfigurationSerializer.cs \
	Mono.Addins.Setup/ConsoleAddinInstaller.cs \
	Mono.Addins.Setup/InstallException.cs \
	Mono.Addins.Setup/IProgressMonitor.cs \
	Mono.Addins.Setup/Package.cs \
	Mono.Addins.Setup/PackageCollection.cs \
	Mono.Addins.Setup/PcFileCache.cs \
	Mono.Addins.Setup/ReferenceRepositoryEntry.cs \
	Mono.Addins.Setup/Repository.cs \
	Mono.Addins.Setup/RepositoryEntry.cs \
	Mono.Addins.Setup/RepositoryEntryCollection.cs \
	Mono.Addins.Setup/RepositoryReaderWriter.cs \
	Mono.Addins.Setup/RepositoryRecord.cs \
	Mono.Addins.Setup/RepositoryRegistry.cs \
	Mono.Addins.Setup/RepositorySerializer.cs \
	Mono.Addins.Setup/SetupService.cs \
	Mono.Addins.Setup/SetupTool.cs \
	Mono.Addins.Setup/TextFormatter.cs

DATA_FILES = 

RESOURCES = 

EXTRAS = \
	./Makefile.am 

REFERENCES =  \
	-r:ICSharpCode.SharpZipLib \
	-r:System \
	-r:System.Core \
	-r:System.Xml

DLL_REFERENCES = 

$(ASSEMBLY).mdb: $(ASSEMBLY)

$(ASSEMBLY): $(build_sources) $(build_resources) $(build_datafiles) $(POLICY_ASSEMBLIES)
	mkdir -p $(dir $(ASSEMBLY))		
	$(ASSEMBLY_COMPILER_COMMAND) $(ASSEMBLY_COMPILER_FLAGS) -out:$@ -target:$(COMPILE_TARGET) $(build_sources) $(build_resources_embed) $(build_references_ref)

install-data-local: gac-install

uninstall-local: gac-uninstall

include $(top_srcdir)/Makefile.include

CLEANFILES += $(POLICY_ASSEMBLIES) $(POLICY_CONFIGS)
