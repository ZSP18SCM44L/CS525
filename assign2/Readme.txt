Assignement implementation of a Buffer manager includes creating and initializing a BufferPool, shutting down the Bufferpool along with few helper functions to emulate the functionality of Buffer Manager. 

All the functionality are implemented as expected. 
Implementation details are provided below where subjective design decisions are made.

Design Decisions:

	In the PinPage function, when it’s asked to pin a page that’s not present in the file, Page is created in the BufferPool and flushed to the file when asked or appropriate. During flushing the non-existent page into the file, it is ensured PageNum number of pages are present in the file and later data is flushed.

	For FIFO strategy implementation, FIFO Nodes are explicitly maintained and are managed during the whole life of the BufferPool. These nodes are updated whenever a new page that’s not currently in the Buffer are asked to be pinned.

	For LRU strategy implementation, LRU Nodes are explicitly maintained and are managed during the whole life of the BufferPool. These nodes are updated whenever pinPage function is called.

	pthread_mutex_lock and pthread_mutex_unlock are used to implement thread safety.