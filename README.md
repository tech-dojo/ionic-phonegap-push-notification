# Ionic-phonegap-push-notification

This is an example Ionic application where you can easily test push notifications in android with the help of [GCM ALERT Website](http://gcm-alert.appspot.com/) acting as a server.

This application uses Google's Cloud Messaging (gcm) to send push notifications from a demo gcm service to our mobile app.

There are three variations of notifications that are showcased here:

 [Notifications with an Image](#notifications-with-an-image)
 
 [Notifications with an Icon](#notifications-with-an-icon)
 
 [Notifications with an Image and Icon](#notifications-with-an-image-and-icon)

# Installation

 * git clone https://github.com/tech-dojo/ionic-phonegap-push-notification.git

 * cd ionic-phonegap-push-notification

 * npm install -g ionic cordova
 
## For running in browser
 
 * ionic serve
 
## For running in device
 
 * ionic state restore

 * ionic platform add android

 * ionic run android
 
# Setting up a new project

 * Head over to [Google Developer Console](https://console.developers.google.com) and create a new project.
 * Find the project number, select the project and click the menu item and then click 'Project Information' to display the   project number.
 * Replace the SENDER_ID value in **package.json** and **app.js** with the project number.
 * Then go to credentials in your project in Google Developer Console and create an api key, choose **server key** to create   the server key.
 * Also enable Google Cloud Messaging from the Google Api library.
 
# Demo GCM Alert

[GCM ALERT](http://gcm-alert.appspot.com/) is a demo google notification service where you can input the data to be sent from the demo gcm alert service to your mobile app as a notification. You can also send additional data other than the given data types. In the gcm alert page, you input the **server key** that was created before in the API Key field. Also in the Reg.Id  field input the value that you will get from the **push.on('registration)** function in app.js. The details of the notification is sent via the message field.

Example message field: title:Event title,message:This is a new Event,EventId=32432432,image=https://dl.dropboxusercontent.com/u/887989/antshot.png

Note: There must not be any spaces between each field or after any comma.

Data types:

 * data.message	*string*	The text of the push message sent from the 3rd party service.
 * data.title	*string*	The optional title of the push message sent from the 3rd party service.
 * data.count	*string*	The number of messages to be displayed in the badge in iOS/Android or message count in the notification shade in Android. For windows, it represents the value in the badge notification which could be a number or a status glyph.
 * data.sound	*string*	The name of the sound file to be played upon receipt of the notification.
 * data.image	*string*	The path of the image file to be displayed in the notification.
 * data.launchArgs	*string*	The args to be passed to the application on launch from push notification. This works when notification is received in background. (Windows Only)
 * data.additionalData	*Object*	An optional collection of data sent by the 3rd party push service that does not fit in the     above properties.
 * data.additionalData.foreground	*boolean*	Whether the notification was received while the app was in the foreground
 * data.additionalData.coldstart	*boolean*	Will be true if the application is started by clicking on the push notification,     false if the app is already started.
 
above data types and their explanation taken from the [phonegap-plugin-push documentation](https://github.com/phonegap/phonegap-plugin-push/blob/master/docs/API.md)

# Types of Notifications

As mentioned before there are three variations of push notifications , Procedure to achieve those are written below,

## Notifications with an Image

* In app.js, when initializing push notification remove the icon and icon color field.

 var push = PushNotification.init({
          android: {
                            senderID: "XXXXXXXXXXX",
                            icon: 'icon',
                            iconColor: "#FF4000"
                        }
        });
  

* In the GCM alert page, send the image with the image field along with title and message.


![Notifications with an Image](/../screenshots/1.png?raw=true "Notifications with an Image")

**FIG: Notifications with an Image**

## Notifications with an Icon

* In app.js, when initializing push notification add the icon and icon color field.

            var push = PushNotification.init({
          android: {
                            senderID: "XXXXXXXXXXX",
                            icon: 'icon',
                            iconColor: "#FF4000"
                        }
        });

* In the GCM alert page, do not send any image with the image field, just pass along the title and message.


![Notifications with an Icon](/../screenshots/2.png?raw=true "Notifications with an Icon")

**FIG: Notifications with an Icon**

## Notifications with an Image and Icon

* In app.js, when initializing push notification add the icon and icon color field.

            var push = PushNotification.init({
          android: {
                            senderID: "XXXXXXXXXXX",
                            icon: 'icon',
                            iconColor: "#FF4000"
                        }
        });

* In the GCM alert page, send image with the image field along with the title and message.


![Notifications with an Image and Icon](/../screenshots/3.png?raw=true "Notifications with an Image and Icon")

**FIG: Notifications with an Image and Icon**

# More Information

For more details, give this a read [ionic-phonegap-push-notification]()

# References

 * [phonegap-plugin-push documentation](https://github.com/phonegap/phonegap-plugin-push/tree/master/docs)
 

## License

MIT License is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.


 

