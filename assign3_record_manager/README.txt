RECORD MANAGER
______________


TEAM MEMBERS (GROUP 3)
______________________

1. Parva Udaykumar Bhayani (A20396637)
2. Shringa Bais (A20382937)
3. Monali Balani (A20410147)
4. Helly Modi (A20398173)


NOTE
____

With the consent of TA, we have changed "line 21" in the file "rm_serializer.c ". We have changed "calloc(100,0)" to "malloc(100)".


HOW TO EXECUTE THE SCRIPT
_________________________

1. Open Terminal

2. Go to the path where files are extracted

3. Run the below command: 1) make 
			  2)./test_assign3_1

4. To remove object files, run following command: make clean


FUNCTIONS IMPLEMENTED
_____________________

Table and Manager Functions

1. initRecordManager()

 - This function is used to initialise the record manager.

2. shutdownRecordManager()

 - This function is used to shut down the record manager.

3 . createTable()

 - This function is used to create a table or a page file. After opening the page file, the schema is serialized and data is written to the file handler.

4. openTable()

 - This function is used to open the table and initialize buffer and record management structure. Then the schema is deserialized.

5. closeTable() 

 - This function is used to close the open buffer pool and the table.

6. deleteTable()

 - This function is used to delete the page or table which is open. It does so by calling destroyPageFile() function of Storage Manager.

7. getNumTuples()

 - This function is used to get the number of records or tuples in the table or relation.

Record Functions

8. insertRecord()

 - This function is used to insert records in the table / relation.

9. deleteRecord()

 - This function is used to delete record from the table/relation.

10. updateRecord()

 - This function is used to update the data in a record in the table/relation.

11. getRecord()

 - This function is used to get the desired record from the table/relation

Scan Functions

12. startScan()

 - This function is used to fetch the data from the table that matches any condition.

13. next()

 - This function is used to get the tuple that satisfies any condition.

14.closeScan()

 - This function is used to close the scan.

Schema Functions

15. getRecordSize()

 - This function is used to get the size of the record.

16. *createSchema()

 - This function is used to create a schema and set the attributes to given values.

17. freeSchema()

 - This function is used to free attributes from the schema.

Record and attribute functions

18. createRecord()

 - This function is used to create new records.

19.freeRecord()
 
 - This function is used to delete the record and free the memory occupied by the record.

20. getAttr()

 - This function is used to get the attributes of the record.

21. setAttr()

 - This function is used to set the attributes for any particular record.


EXTRA STRUCTURES IMPLEMENTED
____________________________

RM_RecordPoolInfo
This structure is created to store the data of all records.

RecordM_PoolScan
This structure is created for carrying out scan operations.

PrimaryKey_Record
This hashing structure is created to check the primary key 

ADDITIONAL ERROR CODES
______________________

For storage manage.
#define RC_NUMBER_OF_PAGES_EXISTS 5
#define RC_FILE_READ_ERROR 6
#define RC_WRITE_OUT_OF_BOUND_INDEX 7
#define RC_FILE_ALREADY_PRESENT 8

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

For record manager
#define RC_EMPTY_TABLE 17
#define RC_INVALID_CONDITION 18
#define RC_RM_ERROR_CREATING_TABLE 19
#define RC_RM_NO_RECORD_FOUND 20
#define RC_RM_NO_TABLE_INIT 21
#define RC_RM_PRIMARY_KEY_ALREADY_PRESENT_ERROR 22
#define RC_RM_PRIMARY_KEY_DELETE_ERROR 23
#define RC_RM_UPDATE_ON_DELETE_RECORD_ERROR 24


EXTRA CREDIT
____________

1.TID and Tombstone

 - Tombstone is used to indicate a deleted value. An array is used to store whether a particular space is occupied or the tombstone value is set to '0' indicating the space is empty.

2. Check primary key constraints

 - A structure is used to check primary key of the records while inserting a new record. We have cross checked primary key in every function, wherever required, before inserting the record.

** 
Due to time constraints, we have not implemented the test cases for both of the above mentioned cases.
**

ABOUT MEMORY LEAKS
__________________

All the test cases have been tested with Valgrind tool and no memory leaks exist.
