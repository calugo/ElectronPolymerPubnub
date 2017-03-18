# Quickstart for Electron and Arduino and Polymer components.

![](https://github.com/calugo/ElectronPolymerPubnub/blob/master/poster2.png)

This repo contains code for a little electron desktop application to plot, log, and stream data via PubNub from an Arduino board, the GUI is built using Polymer (1.x) components. It is always work in progress.

This project is heavily inspired in the great repos of [leoweigand](https://github.com/leoweigand/electron-arduino-quickstart) and [sofroniewn](https://github.com/sofroniewn/electron-johnny-five-examples), the former is actually based in a  [tutorial](http://meow.noopkat.com/using-johnny-five-within-an-electron-app/) by @noopkat.

## OS notes

It works oaut of the box in Linux and OSX, I have not try in Windows, I really hope to be able to provide installers at some point.

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
cd electron-arduino-quickstart
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

# ENJOY!
