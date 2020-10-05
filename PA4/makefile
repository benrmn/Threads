# makefile

all: server client

common.o: common.h common.cpp
	g++ -g -w -std=c++11 -c common.cpp

Histogram.o: Histogram.h Histogram.cpp
	g++ -g -w -std=c++11 -c Histogram.cpp

FIFOreqchannel.o: FIFOreqchannel.h FIFOreqchannel.cpp
	g++ -g -w -std=c++11 -c FIFOreqchannel.cpp

client: client.cpp Histogram.o FIFOreqchannel.o common.o
	g++ -g -w -std=c++11 -o client client.cpp Histogram.o FIFOreqchannel.o common.o -lpthread -lrt

server: server.cpp  FIFOreqchannel.o common.o
	g++ -g -w -std=c++11 -o server server.cpp FIFOreqchannel.o common.o -lpthread -lrt

clean:
	rm -rf *.o fifo* server client 
