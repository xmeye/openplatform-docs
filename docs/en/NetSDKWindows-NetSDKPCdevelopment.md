# SDK demon description

## ClientDemo

Basic description：

SDK integrates a lot of playing parts that is decoded locally. Just need to call the network SDK, it can complete the network transmission and video play. This usage makes it easy to use in secondary development. Commonly used functions all can be completed as long as calling the NETSDK.

Main points:

The key is that incming the window handle in the parameters of start playing;


## Basic process of application

```
1.After entering, the device list on the right is empty (as shown in Figure one below).
2.Right-click in the list --> click to add, pop up device add window (as shown in Figure two below)
3.At this time, you can input the appropriate parameters to add device, or click to search and get to the device that can be connected in the local area network, or log in via DDNS serial number.
4.At this time, there is a corresponding device in the device list. You can also add multiple devices (as shown in Figure three below)
5.Double click the channel in the device list, and select the playing window so that you can play. Click the right box below: PTZ control, image color, video playback, device configuration, network keyboard, and network alarm functions demonstration.
6.(Figure four) is playback dialog box, local play and file conversion; (Figure five is capture image and record); right-click the device list, it has talk-back.
```


## ClientDemo2

Network and decoding the two sets of SDK completely separate. Cooperate with the two sets of SDK to complete the final function implementation. 

The feature of this usage is using flexibly. It is a good choice for the application which wants to do secondary processing or forwarding for network data. In addition, do some special effects processing in the display; it can be able to apply flexibly if playing SDK.


## ConfigDemo

The processing of configured data processing is various. This demon clearly demonstrates the acquisition and setting of almost all configurations.


## Transparent

Simple calling presentation for transparent 485 application

## AlarmCenter

Application of alarm center
