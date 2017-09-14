## Fast registration (does not use the phone number or e-mail, and directly register)

SDK supports that use mobile phone number and mailbox to verify registration and no verification registered
```
（1）Cell-phone number verify registration
（2）Mailbox verify registration
（3）No verification registered
```

## Does the latest SDK support IPv6？

Support

## What are the requirements for registering a username?

Username requires 4~15 characters, include Chinese, letters, numbers and "_"

## What is the format of alarm information?

Chinese：You have an alarm notice serialnumber: xxxxxx Time: 2016-06-24 10:00:00　

English: You have an alarm notice serialnumber: xxxxxx Time: 2016-06-24 10:00:00

## Libeznat: EventIOThread has been always reported such an error, what is the problem?

This is print.

## After switching resolution, it needs to restart the device. Does it need to call the funsdk interface or to re-charge the device?

If the IE modify the resolution, and need to manually start the device, then it will need to operate; otherwise it needs to call the interface to restart the device.

## Alarm pictures sometimes cannot show?

First reason: the device is not normally uploaded to the server so that download failed.

Second reason: FunSDK may download failed.

## What is the relationship between the device and the user?

A device can be bound to a number of users; a user can bind multiple devices. Theoretically the account is bound without limit. Recommend 100 devices within the best.

## How to judge that the coding and decoding of video use the hard decoding or soft decoding?

When opening the video, the type of View that needs to be uploaded. If it is GLSurfaceView20, it is soft decoding, or it is hard decoding.

## What is the way to download the alarm picture?

The first one: you can directly open it in the web page via the URL images in the returned result of querying history, or use the third party library or control download to display.The second one: use FunSDK interface to achieve picture download.

## Video type?

Configuration, closure and always. Configuration has ordinary, alarm and motion detection. The three is represented by mask.

## Resolution switching?

The value of Resolution：

    720p -> 720P
    960p ->1_3M

## Account distinction?

The registered user, who uses the app developed by open platform FunSDK, can only login the developed app and unable to login our company's other app. Account system has been separated.

## Cloud alarm

On APP, server alarm has frequency limit. Too fast will be filtered out in order to avoid excessive pressure on the server.

## App cannot receive the alarm push?

```
（1）App may not subscribed, solution: subscribe this device alarm on the App, calling interface is LinkDev.
（2）May be the device DNS is not set, solution: the domestic DNS is set to 114.114.114.114
（3）The reserved certificate on the server may not be correct (IOS), the solution is to provide a certificate.
```

## What does it mean when querying alarm history will return -222400?

This indicates that no query to the alarm history

## HD forwarding mode is not supported?

Need to use the DSS device to support HD (forwarding mode), the firmware of device needs to be upgraded to DSS.

## This interface which gets the device status, accept multiple devices to get online status, how do I distinguish between online and offline in callback?

Get device status can request multiple devices status at one time, device uuid uses ";" to be separated. Only return a device status at a time, and divide into many times to return. In callback, Param1 is greater than 0 is online. Equal to 0 is offline.







