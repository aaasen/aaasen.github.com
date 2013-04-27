## Simple Local File Sharing with Python's SimpleHTTPServer

I have a laptop and a desktop, and often need to share a file between them.
I don't need to keep them eternally synced or anything - just share a movie or an archive.

Fortunately, Python2 has SimpleHTTPServer to solve this problem.

```bash
$ cd movies/
$ python2 -m SimpleHTTPServer
Serving HTTP on 0.0.0.0 port 8000 ...
```

Then, just find your internal IP address using 
[ifconfig on Linux](https://www.google.com/?q=how+to+find+internal+ip+address+on+linux),
[ipconfig on Windows](https://www.google.com/?q=how+to+find+internal+ip+address+on+windows), or
[ifconfig on Mac](https://www.google.com/?q=how+to+find+internal+ip+address+on+mac).

```bash
$ ifconfig
...
inet 192.168.1.42
...
```

Connect to that address on port 8000 (`192.168.1.42:8000`)
and you'll see a listing of files in the folder that you ran the server in.

Enjoy!
