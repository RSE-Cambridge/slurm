#
# Makefile for slurmd

AUTOMAKE_OPTIONS = foreign

sbin_PROGRAMS = slurmstepd

AM_CPPFLAGS = -I$(top_srcdir)

slurmstepd_LDADD = 				   \
	$(top_builddir)/src/common/libdaemonize.la \
	../common/libslurmd_common.o $(HWLOC_LDFLAGS) $(HWLOC_LIBS) \
	$(top_builddir)/src/api/libslurm.o $(DL_LIBS) \
	$(PAM_LIBS) $(UTIL_LIBS)

slurmstepd_SOURCES = 	        	\
	slurmstepd.c slurmstepd.h	\
	mgr.c mgr.h			\
	task.c task.h			\
	slurmstepd_job.c slurmstepd_job.h \
	io.c io.h			\
	fname.c fname.h			\
	ulimits.c ulimits.h     	\
	pdebug.c pdebug.h		\
	pam_ses.c pam_ses.h		\
	req.c req.h			\
	multi_prog.c multi_prog.h	\
	step_terminate_monitor.c step_terminate_monitor.h

slurmstepd_LDFLAGS = -export-dynamic $(CMD_LDFLAGS)

force:
$(slurmstepd_LDADD) : force
	@cd `dirname $@` && $(MAKE) `basename $@`
