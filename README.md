<h1>Multi Threaded Proxy Server with LRU_CACHE</h1>

This project is implemented using `C` and Parsing of HTTP referred from <a href = "https://github.com/vaibhavnaagar/proxy-server"> Proxy Server </a>

##### Basic Working Flow of the Proxy Server:
![diagram-export-6-14-2024-6_56_02-PM](https://github.com/MaheshPulivarthi18/multi_threaded_proxyserver_with_cache/assets/134507390/ad941088-7537-414f-97a3-b568382f7686)


##### How did we implement Multi-threading?
- Used Semaphore instead of Condition Variables and pthread_join() and pthread_exit() function. 
- pthread_join() requires us to pass the thread id of the the thread to wait for. 
- Semaphore’s sem_wait() and sem_post() doesn’t need any parameter. So it is a better option. 


##### Motivation/Need of Project
- To Understand → 
  - The working of requests from our local computer to the server.
  - The handling of multiple client requests from various clients.
  - Locking procedure for concurrency.
  - The concept of cache and its different functions that might be used by browsers.
- Proxy Server do → 
  - It speeds up the process and reduces the traffic on the server side.
  - It can be used to restrict user from accessing specific websites.
  - A good proxy will change the IP such that the server wouldn’t know about the client who sent the request.
  - Changes can be made in Proxy to encrypt the requests, to stop anyone accessing the request illegally from your client.
 
##### OS Component Used ​
- Threading
- Locks 
- Semaphore
- Cache (LRU algorithm is used in it)

##### Limitations ​
- If a URL opens multiple clients itself, then our cache will store each client’s response as a separate element in the linked list. So, during retrieval from the cache, only a chunk of response will be send and the website will not open
- Fixed size of cache element, so big websites may not be stored in cache. 

##### How this project can be extended? ​
- This code can be implemented using multiprocessing that can speed up the process with parallelism.
- We can decide which type of websites should be allowed by extending the code.
- We can implement requests like POST with this code.


# Note :-
- Code is well commented. For any doubt you can refer to the comments.


## How to Run

```bash
$ make all
$ ./proxy <port no.>
```
`Open http://localhost:port/https://www.cs.princeton.edu/`

# Note:
- This code can only be run in Linux Machine. Please disable your browser cache.
- To run the proxy without cache Change the name of the file (`proxy_server_with_cache.c to proxy_server_without_cache.c`) MakeFile.

## Demo
- When website is opened for the first time (`url not found`) then cache will be miss.
- ![Screenshot from 2024-06-14 19-25-04](https://github.com/MaheshPulivarthi18/multi_threaded_proxyserver_with_cache/assets/134507390/5aee4e2a-c07b-42a0-ab30-5745392277aa)

- Then if you again open that website again then `Data is retrieved from the cache` will be printed.
![Screenshot from 2024-06-14 20-58-58](https://github.com/MaheshPulivarthi18/multi_threaded_proxyserver_with_cache/assets/134507390/eb1fbe39-eae8-40d1-b0e0-95417025727f)

## Contributing

Feel free to add some useful. You can see `How this code can be extended`. Use ideas from there and feel free to fork and CHANGE. 

### Pull requests are highly appreciated.
#   m u l t i _ t h r e a d e d _ p r o x y s e r v e r _ w i t h _ c a c h e 
 
 #   m u l t i _ t h r e a d e d _ p r o x y s e r v e r _ w i t h _ c a c h e 
 
 
