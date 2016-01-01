Assignement implementation of a storage manager includes creating and opening a file, reading blocks from a file on disk into memory and writing blocks from memory to a file on disk. 

CreatePageFile:
	Creates a page in the file which is given page number as 1 and he bytes assigned to the page is 0B.

OpenPageFile:
	Opens the page that is already created and stores the details of file using the struct SM_FileHandle.

ClosePageFile:
	This is used to close the existing page in the file or gives an error message if the page does not exist.

DestroyPageFile:
	This is used to remove the page from the file or gives an error message if the page does not exist.

GetBlockPos:
	This is used to maintain the track of the current page position in the file.

ReadCurrentBlock, ReadPreviousBlock, ReadNextBLock:
	This reads the current, previous or next page depending on the curPagePos of the file.The curPagePos should be moved to the page that was read.

ReadFirstBlock, ReadLastBlock:
	This reads the first and the last pages in the file.

WriteBlock,WriteCurrentBlock:
  	This is used to write the page to the disk by either using the current position or an absolute position.

AppendEmptyBlock:
	This is used to increment the number of pages in the file by one. The page that is incremented is assigned zero bytes.

EnsureCapacity:
	this method checks if the file has pages less than numberofPages. If so, it increments the size to numberofPages.



