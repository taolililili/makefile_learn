$(shell mkdir -p obj)

CC = gcc
ODIR = obj
IDIR = ../include
LDIR = ../lib
BIN = client server

_DEPS = error_functions.o become_daemon.o get_num.o inet_sockets.o
DEPS = $(patsubst %, $(ODIR)/%,$(_DEPS))


all : $(BIN)


$(ODIR)/error_functions.o : $(LDIR)/error_functions.c
	$(CC) -c -o $@ $<

$(ODIR)/become_daemon.o : $(LDIR)//become_daemon.c
	$(CC) -c -o $@ $< 

$(ODIR)/get_num.o :  $(LDIR)//get_num.c
	$(CC) -c -o $@ $<

$(ODIR)/inet_sockets.o : $(LDIR)/inet_sockets.c
	$(CC) -c -o $@ $<

$(ODIR)/client.o : client.c
	$(CC) -c -o $@ $<

$(ODIR)/server.o : server.c
	$(CC) -c -o $@ $<

client : $(ODIR)/client.o  $(DEPS)
	@echo $(DEPS)
	$(CC) -o $@ $^


server : $(ODIR)/server.o  $(DEPS)
	$(CC) -o $@ $^

.PHONY: clean
clean:
	rm obj/*.o $(BIN)