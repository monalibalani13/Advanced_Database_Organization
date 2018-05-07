CC := gcc
SRC :=  record_mgr.c rm_serializer.c expr.c dberror.c storage_mgr.c buffer_mgr_stat.c buffer_mgr.c test_assign3_1.c
OBJ :=  record_mgr.o rm_serializer.o expr.o dberror.o storage_mgr.o buffer_mgr_stat.o buffer_mgr.o test_assign3_1.o

assignment3: $(OBJ)
	$(CC) -w -o test_assign3_1 $?
	$(CC) -w -o test_expr record_mgr.c rm_serializer.c expr.c dberror.c storage_mgr.c buffer_mgr_stat.c buffer_mgr.c test_expr.c
	

%.o: %.c
	$(CC) -w -g -c $<

clean:
	rm -rf test_assign3_1 test_expr *.o
