This is a little tutorial on how to load CSV data from Python into Titan using
the Python library [Bulbs](http://bulbflow.com/). First we need to set up Xcode
and Homebrew, which is a nice package manager for OSX:

1. Install [Xcode](https://developer.apple.com/xcode)

2. Install Xcode command line tools by:

a. Open Xcode
b. Open Menu Xcode > Preferences
c. Open "Downloads" tab and install the Command Line Tools

3. Install [Homebrew](http://brew.sh/):

```
% ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
```

Note: there are some security risks here as you will be installing things
from the open internet. I've never heard of a security violation yet
though.

4. Open up a terminal and run:

```
% echo 'export PATH=/usr/local/bin:$PATH' >> .bashrc
% exec bash
```

5. Install Python:

```
% brew install git python
```

6. Install Bulbs:

```
% pip install bulbs
```

Second, if you want to start a local Titan instance:

7. Download the [Titan Server](https://github.com/thinkaurelius/titan/wiki/Downloads) package and unzip it

8. Start Titan with:

```
% unzip titan-server-0.4.1.zip
% cd titan-server-0.4.1
% ./bin/titan.sh start
```

Run the script:

```
% ./load-csv-into-titan data.csv
```

It should run without error. If you want to connect to an arbitrary server, run:

```
% ./load-csv-into-titan -u http://another.server:1234/graphs/graph data.csv
```

That script supports `-h` if you want to see the other options it supports.
