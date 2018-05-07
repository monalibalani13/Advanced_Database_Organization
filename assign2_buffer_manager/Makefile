CC := gcc
SRC := dberror.c storage_mgr.c buffer_mgr_stat.c buffer_mgr.c test_assign2_1.c
OBJ := dberror.o storage_mgr.o buffer_mgr_stat.o buffer_mgr.o test_assign2_1.o

assignment2: $(OBJ)
	$(CC) -o test_assign2_1 $?

%.o: %.c
	$(CC) -w -g -c $<
run: assignment2
	./test_assign2_1

clean:
	rm -rf test_assign2_1 *.o	
