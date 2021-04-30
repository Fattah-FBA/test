MKDIR_COM = mkdir -p
RELDIR = release
SLINK = previous_release
SUBDIR = Reports Audits Logfiles
FULLDIR = $(addprefix $(RELDIR)/, $(SUBDIR))
SRC = 
NEWRELCMD := $(MKDIR_COM) $(FULLDIR)

#If source directory is provided then copy the contents to 'release' dir
ifdef SRC
NEWRELCMD := $(NEWRELCMD); \
						 cp -r $(addprefix $(patsubst %/, %, $(SRC))/, $(SUBDIR)) $(RELDIR)
endif

.PHONY : help new prev_rel new_rel

help : 
	@echo '#####Release Management System######'
	@echo 'To create new release dir and bakeup the previous release dir':
	@echo '	make new'
	@echo 'To create new release dir and copy the contents of a project dir:'
	@echo '	make SRC=<project_dir> new'

new : prev_rel new_rel

#Make a backup of previous release and create a soft link to it
prev_rel : 
	@if [ -d $(RELDIR) ]; then \
		tstamp=`date '+%Y%m%d_%H%M%S'`; \
		mv $(RELDIR) $(RELDIR)_$$tstamp; \
		ln -sf release_$$tstamp $(SLINK); \
	fi

#Create the new Release dir and optionally copy the contents of source dir if provided
new_rel : 
	@$(NEWRELCMD)
