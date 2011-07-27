
IPM_ROOT = ../

LIB_MXML=-lmxml -lpthread
#LIB_CUBE=-L./cubew/lib -lcubew3
LIB_CUBE=cubew/lib/libcubew3.a 

CFLAGS = -I./cubew/lib -I$(IPM_ROOT)/include

#include $(IPM_ROOT)/make_config

ipm_parse : ipm_parse.o getopts.o read_ipm.o write_cube.o util.o report_banner.o $(LIB_CUBE)
	$(CXX) -o $@ $+ $(LIB_MXML) $(LIB_CUBE)

%.o : %.cc 
	$(CXX) $(CFLAGS) -c $+ -o $@

report_banner.o : $(IPM_ROOT)/src/report_banner.c
	$(CXX) $(CFLAGS) -c $+ -o $@

$(LIB_CUBE) : 
	make -C ./cubew/lib

clean : 
	rm -f ipm_parse
	rm -rf *.o *~