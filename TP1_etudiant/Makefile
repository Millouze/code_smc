all : simulator.x 

fast : fast_simulator.x

fifo_gcd_master.o :
	g++ -Wno-deprecated -fpermissive -std=gnu++0x -I. -I/users/outil/dsx/cctools/include -m32 -c  fifo_gcd_master.cpp	

fifo_gcd_coprocessor.o :
	g++ -Wno-deprecated -fpermissive -std=gnu++0x -I. -I/users/outil/dsx/cctools/include -m32 -c  fifo_gcd_coprocessor.cpp	

top_tp1.o :
	g++ -Wno-deprecated -fpermissive -std=gnu++0x -I. -I/users/outil/dsx/cctools/include -m32 -c  tp1_top.cpp

simulator.x : fifo_gcd_master.o fifo_gcd_coprocessor.o top_tp1.o
	g++ -Wno-deprecated -fpermissive -m32 -L. -L/users/outil/dsx/cctools/lib-linux -o simulator.x fifo_gcd_master.o fifo_gcd_coprocessor.o tp1_top.o -lsystemc 2>&1 

fast_fifo_gcd_master.o :
	g++ -Wno-deprecated -fpermissive -std=gnu++0x -I. -I/users/outil/dsx/systemcass/include -m32 -c fifo_gcd_master.cpp	

fast_fifo_gcd_coprocessor.o :
	g++ -Wno-deprecated -fpermissive -std=gnu++0x -I. -I/users/outil/dsx/systemcass/include -m32 -c  fifo_gcd_coprocessor.cpp	

fast_top_tp1.o :
	g++ -Wno-deprecated -fpermissive -std=gnu++0x -I. -I/users/outil/dsx/systemcass/include -m32 -c  tp1_top.cpp

fast_simulator.x : fast_fifo_gcd_master.o fast_fifo_gcd_coprocessor.o fast_top_tp1.o
	g++ -Wno-deprecated -fpermissive -m32 -L. -L/users/outil/dsx/systemcass/lib -o  fast_simulator.x fifo_gcd_master.o fifo_gcd_coprocessor.o tp1_top.o -lsystemc -ldl 2>&1

clean : 
	rm fifo_gcd_master.o fifo_gcd_coprocessor.o tp1_top.o
