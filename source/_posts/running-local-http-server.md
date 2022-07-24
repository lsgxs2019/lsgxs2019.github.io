---
title: running local http server
date: 2022-07-24 08:47:21
tags:  
  - http
  - html
  - localhost 
categories: html
thumbnail: /images/local-http-server.png
---

## [Running a simple local HTTP server](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/set_up_a_local_testing_server#running_a_simple_local_http_server)

To get around the problem of async requests, we need to test such examples by running them through a local web server. One of the easiest ways to do this for our purposes is to use Python's `http.server` module.

**Note:** Older versions of Python (up to version 2.7) provided a similar module named `SimpleHTTPServer`. If you are using Python 2.x, you can follow this guide by replacing all uses of `http.server` with `SimpleHTTPServer`. However, we recommend you use the latest version of Python.

<!--more-->

To do this:

1. Install Python. If you are using Linux or macOS, it should be available on your system already. If you are a Windows user, you can get an installer from the Python homepage and follow the instructions to install it:

   - Go to [python.org](https://www.python.org/)
   - Under the Download section, click the link for Python "3.xxx".
   - At the bottom of the page, click the *Windows Installer* link to download the installer file.
   - When it has downloaded, run it.
   - On the first installer page, make sure you check the "Add Python 3.xxx to PATH" checkbox.
   - Click *Install*, then click *Close* when the installation has finished.

2. Open your command prompt (Windows) / terminal (macOS/ Linux). To check if Python is installed, enter the following command:

   ```
   python -V
   # If the above fails, try:
   python3 -V
   # Or, if the "py" command is available, try:
   py -V
   ```

   Copy to Clipboard

3. This should return a version number. If this is OK, navigate to the directory that your example is inside, using the

    

   ```
   cd
   ```

    

   command.

   ```
   # include the directory name to enter it, for example
   cd Desktop
   # use two dots to jump up one directory level if you need to
   cd ..
   ```

   Copy to Clipboard

4. Enter the command to start up the server in that directory:

   ```
   # If Python version returned above is 3.X
   # On Windows, try "python -m http.server" or "py -3 -m http.server"
   python3 -m http.server
   # If Python version returned above is 2.X
   python -m SimpleHTTPServer
   ```

   Copy to Clipboard

5. By default, this will run the contents of the directory on a local web server, on port 8000. You can go to this server by going to the URL `localhost:8000` in your web browser. Here you'll see the contents of the directory listed — click the HTML file you want to run.

**Note:** If you already have something running on port 8000, you can choose another port by running the server command followed by an alternative port number, e.g. `python3 -m http.server 7800` (Python 3.x) or `python -m SimpleHTTPServer 7800` (Python 2.x). You can then access your content at `localhost:7800`.
