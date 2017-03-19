# Quickstart for Electron and Arduino and Polymer components.

![](https://github.com/calugo/ElectronPolymerPubnub/blob/master/poster2.png)

This repo contains code for a little electron desktop application to plot, log, and stream data via PubNub from an Arduino board, the GUI is built using Polymer (1.x) components. It is always work in progress.

This project is heavily inspired in the great repos of [leoweigand](https://github.com/leoweigand/electron-arduino-quickstart) and [sofroniewn](https://github.com/sofroniewn/electron-johnny-five-examples), the former is actually based in a  [tutorial](http://meow.noopkat.com/using-johnny-five-within-an-electron-app/) by @noopkat.

The layout so far includes a set of buttons and a plot area, all of these are polymer webcomponents, the buttons are standard 
paper-button components and the plot is a [highcharts](https://github.com/avdaredevil/highcharts-chart) courtesy of avdaredevil. The components API can be reached [here](https://github.com/avdaredevil/highcharts-chart).

The toggle buttons have the following functionality:

_**start**_ the data stream plot from A0 in the arduino
_**record**_ record's the data stream and stores it the folder "Logs/" as log0.dat, log1.dat, etc. where the numeric index represents the event of recording since the application started, this should soon will be refined to a date-time format i guess, if you have a log stored, close and restart the application the indexing of the logs will be restarted and any previous log with the same index will be overwritten.
_**load**_ Loads and plot a log file.
_**IOT**_ streams the data to a PubNub channel, if you have a set ok keys and a page somewhere, you should change these in the source code or otherwise it will be streamed and plotted to my settings.
_**LED**_ Hello world to turn on and off the on-board led.

There are a lot of things I inted to do to turn this into something more useful but at the moment this is it, if you have and idea or a contribution please share!


## OS notes

The app works out of the box in Linux and OSX, I have not tried out in Windows. I really hope to be able to provide installers at some point.

Below there are instructions I ripped off from [leoweigand's](https://github.com/leoweigand/electron-arduino-quickstart) README.

## Prerequisites
First, you have to install Firmata on your Arduino, which is a protocol for communicating with microcontrollers. In the Arduino IDE, select the `Firmata Plus` sketch from the examples folder and upload it to your board.
Be sure to have [node.js](https://nodejs.org/en/) installed, as well Electron:
```bash
npm install -g electron
```

## How to use
First, hook up your Arduino with Firmata loaded on to it.
Next, clone this repository and install the dependencies:
```bash
git clone https://github.com/calugo/ElectronPolymerPubnub.git
cd ElectronPolymerPubnub
npm install
bower install
```
Use `npm start` to run your app and you are ready to go!
  
If you get an error because of missing **xcode-commandline-tools**, install the command-line-tools and execute `npm run postinstall`. After that, you should be able to use npm start as shown before.

## What’s next?
I recommend looking into the documentation of both Johnny-Five and Electron for more information on the topic. If something is not working, feel free to [open a new issue](https://github.com/calugo/ElectronPolymerPubnub/issues/new).

## Why is this useful?
If you want to program an Arduino using JavaScript, Johnny-Five and node.js are a great way to start. But even for the most basic UI, you have to incorporate some sort of communication between your webpage and node.js. You could use websockets, for example using socket.io but this is really to much boilerplate code for rapid prototyping. Using Electron on the other hand, we are able to i.e. use jQuery and other libraries and directly speak to Arduinos when actions occur in the browser window.
  
Unfortunately, there are some difficulties to overcome using Electron and the `serialport` library required by Johnny-Five which take time and might be confusing for beginners. As outlined in the tutorial by @noopkat, this repo fixes these problems and provides the boilerplate code for getting started with hardware prototyping in Electron.

# If you succed you should see something like this:

![](https://github.com/calugo/ElectronPolymerPubnub/blob/master/GUI.png)
