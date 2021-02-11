Group 37 - Venkata Sai Naveena Bathula (A20451804)
                   Rishikesh Jangam (A20448930)
                   Hitha Venkatesh Prasanna (A20443457)


Steps to Run the project
1. Open the terminal and navigate to the Project directory.
2. run the 'make clean' command to clean all the object files that are currently present (if any).
3. run the 'make' command to compile and create the respective object files.
4. run the 'make run' command to execute the project and obtain the output.


Files contained
buffer_mgr.c - this contains all the function prototypes that are needed for the buffer manager functionality.
buffer_mgr.h - this header file consists of declarations for all the functions.
buffer_mgr_stat.h - This header file provides the required  functions to output a buffer or page content.
buffer_mgr_stat.c - Contains the respective implementation of the functions specified by the mentioned header file.
storage_mgr.c - Consists of the function definitions for the storage manager
storage_mgr.h - The header file that consists of all the prototypes for the functions that are required byb the storage manager.
dberror.h - It is a header file containing all the constants 
dberror.c - consists of the functions definition for error messages of the storage manager
test_assign1_1.c - is a Test case file which tests all the required functions


Buffer Manager


1. Buffer Manager Pool handling functions
initBufferPool() - A function that is meant to initialize a new buffer pool in memory, given number of pages and replacement strategy.


shutdownBufferPool() - A function that is used to shutdown/ destroy a bufferpool. This frees up all the allocated resources.


forcefFlushPool()- This is a function that is used to write all the dirty pages to the disk.


2. Page Management Functions
pinPage()- This function pins the pageNum  on to a file and reads the page from the page file present on disk, stores it in the buffer pool.


unpinPage()- It is used to unpin a specified page which is identified by the page's pageNum.


makeDirty() - Used to set the dirtyBit of the specified page frame to 1.


forcePage() - This page writes the content of the specified page frame to the page file present on disk.


3. Statistic Functions
getFrameContents() - This function returns an array of Page Numbers, in which the size of the array is equal to the buffer size. 


getDirtyFlags() - Return true if the page stored in the "n"th page frame is dirty.


getFixCounts()- This function returns the fixed count of value of the page frames present in the buffer pool.


getNumReadIO() - This function returns number of IO reads performed by the buffer pool.


getNumWriteIO() - Used to return the count of the total number of IO writes performed by the buffer pool 


4. Page Replacement Functions
FIFO()- First In First Out (FIFO) is a strategy which uses a queue where the page that comes in first to the buffer pool is the one that will be replaced first in case the buffer pool is full.


LFU()- Least Frequently Used (LFU) is a replacement strategy that removes the page frame which is used the least number of times.


LRU() - Least Recently Used (LRU) is a replacement strategy that removes the page frame which has not been used for a long time.


CLOCK() - The CLOCK algorithm keeps track of the last added page frame in the buffer pool




STORAGE MANAGER


1. File Manipulation Functions
initStorageManager()- This function initializes the Storage manager.


createPageFile() - This function is used to create a page file


openPageFile() - This function is used to open the created pageFile and store the information in file handler.


closePageFile() - This function is used to close the file


destoryPageFile() - This function is used to destroy (delete) a page file




2. File Read functions
readBlock() - This method reads the block from a file and stores the content in the memory.


getBlockPos() - Returns the current position of the cursor.


readFirstBlock()- This reads first page position of the file


readPreviousBlock() - This reads previous page's position


readCurrentBlock() - This reads current page's position


readNextBlock() - This reads next page position of the file


readLastBlock()- This reads last page position of the file


3. Writing Blocks from the disk
writeBlock() - This function writes a page which starts from the absolute position to the file on disk.


writeCurrentBlock() - This function write one page to the file from the current position


appendEmptyBlock()- This function performs the write of an empty page to the file by appending to the end.


ensureCapacity()- This function ensures the capacity and increases the size of the numberOfPages if the file has less than numberOfPages


Test cases
The test case files will be used to test all the functionalities of the buffer manager on the whole, additional test cases to check the clock and replacement strategies have also been added.