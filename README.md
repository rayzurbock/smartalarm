## Smart Alarm

Smart Alarm is a home security application for the
[SmartThings](http://fbuy.me/bb9pe) home automation system.


### Features

* Two arming modes - Away and Stay.
* Unlimited number of sensors (contact, motion, moisture or smoke).
* Each sensor represents a security zone that be designated as Exterior (armed
in both Away and Stay modes), Interior (armed in Away mode only), Alert
(always armed) and Entrance (same as Exterior, but uses entry and exit
delays).
* Optional entry and exit delays for the Entrance zones.
* Zone bypass allows quickly exclude selected zones.
* When alarm is set off, Smart Alarm can execute selected 'Hello, Home'
action, turn on sirens and light switches, send push notifications and text
messages.
* Silent mode disables sirens and switches, but leaves push notifications and
text messages on.


### Arming and Disarming

Smart Alarm can be armed and disarmed in several different ways:

1. By assigning home 'Modes'. For example, you can configure Smart Alarm to
arm in Away mode when the home Mode is set to 'Away', to arm in Stay mode when
the home Mode is set to 'Night' and disarm when the home Mode is set to 'Home'.
Using home Mode to arm and disarm Smart Alarm is a very flexible and powerful
technique because home modes can be changed by other Smart Apps and 'Hello,
Home' actions. For example, 'Good Night!' action activates the 'Night' mode,
thus automatically arming Smart Alarm in Stay mode.
2. Using a remote control, such as
[Aeon Labs Minimote](http://www.amazon.com/Aeon-Labs-DSA03202-v1-Minimote/dp/B00KU7ERAW)
3. Using REST API endpoints. Smart Alarm provides REST endpoints to allow any
web client to arm, disarm and trigger panic alarm using HTTP GET request. This
feature can be used to integrate Smart Alarm into variety of Web dashboards
and remote control web apps.


### Screenshots

Coming soon....


### Using REST API

Smart Alarm provides REST API endpoints to allow any web client to arm, disarm
and trigger panic alarm using HTTP GET request. This feature can be used to
integrate Smart Alarm into variety of Web dashboards and remote control web
apps.

    BASE_URL/armaway  - Arms Smart Alarm in Away node
    BASE_URL/armstay  - Arms Smart Alarm in Stay mode
    BASE_URL/disarm   - Disarms SmartAlarm
    BASE_URL/panic    - Triggers panic alarm
    BASE_URL/status   - Returns current status

The BASE_URL is https://graph.api.smartthings.com/api/smartapps/installations/APP_ID,
where APP_ID is the installed Smart App ID.

The REST API requires Access Token. You can obtain the access token using
SmartThings OAuth2 work flow, however as a convenience, Smart Alarm creates
the token for you. You can find your app's base URL and access token in the
SmartThings IDE.

Go to [My Locations](https://graph.api.smartthings.com/location/list) and
click on the "smartapps" link for your Location. Then find "Smart Alarm" in
the list of Installed SmartApps. Right-click on the "Smart Alarm" and select
"Open Link in New Window". Scroll down to the "Application State" section.
There you'll see "accessToken" and "restEndpoint". Save those values and
plug them in into your web app. 

 
### Installation

Smart Alarm app is available in the "Safety & Security" section of the Shared
Smart Apps in [SmartThings IDE](https://graph.api.smartthings.com).

1. Go to "My SmartApps" section and click on the "+ New SmartApp" button on the
right.
2. On the "New SmartApp" page, fill out mandatory "Name" and "Description"
fields (it does not matter what you put there).
3. Make sure to enable OAuth in the application settings.
4. Click the "Create" button at the bottom.
5. When a new app template opens in the IDE, click on the "Browse SmartApps"
drop-down list in the upper right corner and select "Browse Shared SmartApps".
A list of shared SmartApps will appear on the left side of the editor window.
6. Scroll down to "Safety & Security" section and click on it.
7. Select "Smart Alarm" app from the list and click the red "Overwrite" button
in the bottom right corner.
8. Click the blue "Save" button above the editor window.
9. Click the "Publish" button next to it and select "For Me". You have now
self-published your SmartApp.
10. Open SmartThings mobile app on iPhone or Android and go to the Dashboard.
11. Tap on the round "+" button and navigate to "My Apps" section by swiping
the menu ribbon all the way to the left.
12. "Smart Alarm" app should be available in the list of SmartApps that
appears below the menu ribbon. Tap it and follow setup instructions.


### Revision History

**Version 2.2.1. Released 2014-12-06**
* Added option to disable entry delay in Stay mode.
* Fixed an issue related to scheduling delayed actions.

**Version 2.2.0. Released 2014-11-05**
* Exit delay is back. Note that the exit delay applies only to the Entrance
zones and only when arming in Away mode.
* Added voice notifications for the state changes (armed/disarmed).
* If the notification phrase is not entered then a default phrase will be
used.
* Moved voice configuration to "Notification Options" page

**Version 2.1.0. Released 2014-11-04**
* Added voice notifications using devices with 'Speech Synthesis' capability.
Currently, implemented only in the
[VLC Thing](https://github.com/statusbits/smartthings-vlc), as far as I know.
* New notification options. You can now select notification options for alarm
notifications and status change separately.
* Increased the number for telephone numbers used for SMS notifications from
two to four.
* Fixed broken push notifications.

**Version 2.0.0. Released 2014-11-02**
* Simplified zone management. Each sensor is now treated as a separate
zone. The number of zones (sensors) is unlimited.
* New 'Entrance' zone type. Entry delay now only affects Entrance zones.
* Exit delay is eliminated.
* Removed buttons (Arm, Disarm, Panic) from the control panel pending
UI button implementation on Android platform.
* Refactored arming/disarming logic to work around event unsubscribtion
errors that started after SmartThings backend upgrade.

**Version 1.2.1. Released 2014-09-22**
* Fixed Issue #11 - Entry/Exit delays configuration changes are not applied.

**Version 1.2.0. Released 2014-09-18**
* Implemented REST endpoints to arm, disarm and trigger panic alarm with HTTP
GET requests.
* Added configuration setting to select home 'Mode' for disarming alarm.
* Exit and entry delays can now be configured for 15, 30, 45 or 60 seconds.
* Fixed an issue with broken SmartThings runIn() API.

**Version 1.1.3. Released 2014-09-14**
* You can now use remote control, such as Aeon Labs Minimote, to arm and
disarm Smart Alarm, as well as trigger panic alarm. 
* When alarm is set off, Smart Alarm can now execute 'Hello, Home' action in
addition to turning on sirens and light switches
* Added 'Arm Away', 'Arm Stay and 'Disarm' control panel buttons (iOS only).
* Modified Setup Menu work flow and some help text.

**Version 1.1.0. Released 2014-09-12**
* Released under GPLv3 License.
* Added 'About' page in the setup menu.
* Merged changes from Barry Burke (SANdood) branch
(https://github.com/SANdood/smartthings/tree/master/SmartAlarm). Thanks!

**Version 1.0.1. Released 2014-08-28**
* Fixed spelling mistakes, formatting, etc.

**Version 1.0.0. Released 2014-07-04**
* First public release.


License
-------

Copyright (C) 2014 Statusbits.com

This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the Free
Software Foundation, either version 3 of the License, or (at your option)
any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License
for more details.

You should have received a copy of the GNU General Public License along
with this program.  If not, see <http://www.gnu.org/licenses/>.
