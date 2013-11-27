This is a little tutorial on how to load CSV data from Python into Titan using the Python library [Bulbs](http://bulbflow.com/). First we need to set up Xcode and Homebrew, which is a nice package manager for OSX:

Setup for OS X
==============

Install XCode
-------------

* Install [Xcode](https://developer.apple.com/xcode) through the App Store.
* Install Xcode command line tools by:
    * Open Xcode
    * Open Menu Xcode > Preferences
    * Open "Downloads" tab and install the Command Line Tools

Install Python and Bulbs with Homebrew
--------------------------------------

[Homebrew](http://brew.sh) is a nice open source package manager for OS X. It's pretty simple to install. Be aware you'll be downloading things from the open web:

```
% ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
% echo 'export PATH=/usr/local/bin:$PATH' >> .bashrc
% exec bash
% brew install python
% pip install bulbs
```

Download Titan
--------------

Bulbs needs Titan running behind Rexster, so you need to download the [Titan Server](https://github.com/thinkaurelius/titan/wiki/Downloads) package. After downloaded, start it up with:

```
% unzip titan-server-0.4.1.zip
% cd titan-server-0.4.1
% ./bin/titan.sh start
```

Loading data into Titan
=======================

The script is pretty straightforward to use. It has two forms. The first accepts a single edge list `.csv` file. It will automatically create empty vertices to connect the edges: 

```
% ./load-csv-into-titan data.csv
```

Second is when you provide both a vertex and edge `.csv` file:

```
% ./load-csv-into-titan vertices.csv edges.csv
```

By default the script will connect to a locally hosted Titan, but if you want to connect to an arbitrary server, run:


```
% ./load-csv-into-titan -u http://another.server:1234/graphs/graph data.csv
```

Finally, the script supports a `-h` or `--help` if you want to see the other options it supports.
