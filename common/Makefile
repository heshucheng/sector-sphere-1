include ../Makefile.common

CCFLAGS += -I../udt

OBJS = conf.o snode.o meta.o index.o index2.o memobj.o topology.o sysstat.o log.o sphere.o constant.o crypto.o transport.o datachn.o dhash.o routing.o ssltransport.o threadpool.o

all: libcommon.so libcommon.a

%.o: %.cpp
	$(C++) -fPIC $(CCFLAGS) $< -c

libcommon.so: $(OBJS)
	$(C++) $(DYNAMIC_FLAGS) -o $@ $^

libcommon.a: $(OBJS)
	ar -rcs $@ $^

clean:
	rm -f *.o *.so *.a

install:
	mkdir -p ../lib
	mv libcommon.so ../lib
	mv libcommon.a ../lib
