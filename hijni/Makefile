SRC_DIR = .
INCLUDES = -I$(SRC_DIR) -I${JAVA_HOME}/include -I${JAVA_HOME}/include/linux

all: headers shared class

headers:
	cd src;javah -d ../jni -jni hijni 

class:
	javac HelloWorld.java

shared: 
	gcc  $(INCLUDES) -fPIC -c -g -Wall jni/hijni.c 
	gcc -shared -o libhijni.so jni/hijni.o


clean:
	rm -f *.o *.so *.class *~
