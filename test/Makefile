
all : 
	find . -name "test.*" -exec make -C {} \;

verify : 
	find . -name "test.*" -exec make -C {} verify \;

clean : 
	find . -name "test.*" -exec make -C {} clean \;
	rm -f *~
