BUFFER MANAGER
______________


TEAM MEMBERS (GROUP 3)
______________________

1. Parva Udaykumar Bhayani (A20396637)
2. Shringa Bais (A20382937)
3. Monali Balani (A20410147)
4. Helly Modi (A20398173)


HOW TO EXECUTE THE SCRIPT
_________________________

1. Open Terminal

2. Go to the path where files are extracted

3. Run the below command: make run

5. To remove object files, run following command: make clean

6. An additional test file is created, 'test_assign2_2.c' to test LFU replacement strategy : Firstly, modify the make file and replace the text 'test_assign2_1' with 'test_assign2_2' everywhere in the file whether its a .c file , object file or any other. Then execute the command - make run


FUNCTIONS IMPLEMENTED
_____________________


Buffer Pool Functions

1. initBufferPool()

 - This function is used to initialize a new buffer pool using 'numPages' page frames and 'strategy' replacement strategy. 

2. shutdownBufferPool()

 - This function is used to destroy a Buffer Pool. All the resources i.e., memory allocation is freed. Dirty pages, if any, are written back to the disk before destroying the pool.

3. forceFlushPool()

 - This function is used to write the dirty pages back to the disk from the buffer pool if fix count=0.

Page Management Functions

4. markDirty()

 - This function is used to set the dirty bit of a given page frame to 1.

5. unpinPage()

 - This function is used to remove/unpin a page frame from the buffer pool.

6. forcePage()

 - This function is used to write the contents of the page frame to the particular page file on the disk.

7. pinPage()

 - This function is used to pin the page with the given pageNum. The data field points to the corresponding page frame in which the page is stored in memory.

Statistical Functions

8. getFrameContents()

 - This function is used to create an array of page numbers of 'pageNum' size.

9. getDirtyFlags()

 - This function is used to identify the pages which are dirty. An array of size numPages stores the value of the dirty bits which is TRUE if the bit is dirty and FALSE if it isn't dirty.

10. getFixCounts()

 - This function is used to get an array of fix counts of page stored in that particular pageFrame.

11. getNumReadIO()

 - This function is used to fetch the number of pages that have been read from the disk since the buffer pool was initialized.

12. getNumWriteIO()

 -  This function is used to fetch the number of pages that have been written to the disk since the buffer pool was initialized.

Additional Functions

13. FindEmpty()

 - This function is used to check for any empty space in the buffer pool. If there does not exist any empty frame, the replacement strategy decides which page to be replaced.

14. replacementStrategy()

 - This function is used to replace ther page from the buffer pool with the new page. Replacement strategies such as FIFO or LRU is used. If the page is dirty, it is written back to the disk, the dirty bit is updated and then removed.

15. pinPageLFU()

 - This function is used to implement Least Frequently Used page replacement strategy. The page which is used least is removed from the buffer pool.
If the page is dirty, it is written back to the disk, the dirty bit is updated and then removed.


ADDITIONAL ERROR CODES
______________________

For storage manager
#define RC_NUMBER_OF_PAGES_EXISTS 5
#define RC_FILE_READ_ERROR 6
#define RC_WRITE_OUT_OF_BOUND_INDEX 7
#define RC_FILE_ALREADY_PRESENT 8
#define RC_FILE_EXISTS 18

For buffer manager
#define RC_BUFFER_POOL_NOT_INIT 9
#define RC_BUFFER_POOL_ALREADY_INIT 10
#define RC_BUFFER_POOL_ERROR_IN_UNPINPAGE 11
#define RC_BUFFER_POOL_NULL 12
#define RC_BUFFER_POOL_ERROR_IN_FORCEPAGE 13
#define RC_BUFFER_POOL_ERROR_IN_MARKDIRTY 14
#define RC_BUFFER_POOL_ERROR_IN_PINPAGE 15
#define RC_BUFFER_POOL_PINPAGE_PRESENT 16
#define RC_BUFFER_POOL_PAGE_INUSE 17


EXTRA CREDIT
____________

1. Implemenation of Least Frequently Used(LFU) page replacement strategy.
2.All the functions of buffer manager are thread-safe. Multiple clients can access the buffer manager at the same time.

ADDITIONAL TEST FILES
_____________________

test_assign2_2.c

This file contains additional test cases. It is used to test the LFU page replacement strategy.

ABOUT MEMORY LEAKS
__________________

All the test cases have been tested with Valgrind tool and no memory leaks exist.


This folder contains an additional test file
