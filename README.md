crawler
=======

Group Member:
Guodong Zhang gzhang47@wisc.edu
Yijing Bai ybai39@wisc.edu

#### A Simple Web/File crawler for cs537 P4a.  
* Start from the url/filename and crawl the pages.  
* parse with link:.  
* multi-threaded. 




usage
-------------
```shell
./file_tester pagea
./web_tester index.txt

```

implementation:
-------------
* wrapped all the functionality/data structure in the pool data structure.  
* Pool contains fixed sized link queue imlemented by array, unlimited sized page queue by linked list, each queue support push, pop, is empty, etc functionality
* Pool also contains a set for duplicate link loop up
* each data structure holds lock and holds condition variable. Page queue needs one lock one condition variable, link queue needs one lock two condition variables,
 set needs one lock one condition variable
* child threads will wake up parent thread given two queues are empty and no active threads working. 
