# ServerClient-1
HTTP Denial-of-Service protection system

In this task, you need to write a simple HTTP Denial-of-Service protection system.

You need to create a solution with 2 projects (one for the client and one for the server).

 

1. Client

                a.            Console application.

                b.            The user enters the number of HTTP clients to simulate.

                c.             For each HTTP client you will run a separate simultaneous thread/task which will do the following in a loop:

                                i.              Send HTTP request to a server with simulated HTTP client identifier as a query parameter (e.g. http://localhost:8080/?clientId=3).

                                ii.             Wait some random time and then send another request.

                d. The client will run until key press after which it will gracefully drain all the threads/tasks (wait for all the of them to complete)  and will exit.

 

2. Server

                a.            Console application.

                b.            Starts listening for incoming HTTP requests using HttpListener.

                c.             For each incoming HTTP request you will do the following:

                                i.              Handle the request in a separate thread/task.

                                ii.             Check if this specific client reached the max number of requests per time frame threshold (no more than 5 requests per 5 secs).

                                iii.            If the client hasn't reached the threshold, it will get '200 OK' response otherwise '503 Service Unavailable'.

                                iv.           Note: The time frame starts on each client's first request and ends 5 seconds later.

                                                After the time frame has ended, the client's first request will open a new time frame and so forth.

                d.            The server will run until key press after which it will gracefully drain all the threads/tasks and will exit.


3. General notes

                a.            Pay attention to thread safeness.

                b.            The solution should be as simple as possible (avoid over design/engineering).

                c.             The solution should be clean piece of code so please write it as it was a production code (use your own standards/conventions).

                d.            Please confirm the reception and understanding of the coding interview
