# 19626_Pushover.hsl
Gira Homeserver to [Pushover](https://pushover.net) API Logic module

Ever wanted to receive notifications from your Gira Homeserver in [Pushover](https://pushover.net)? Look no further! This logic module does just that. 

The possibilities are endless. Get notified if your front door opens, or if an alarm is triggered, or if the temperature in your house is to low. You name it, you've got it!

Installation
------------
Just copy ```19626_Pushover_Vx.xx.hsl``` to the logic folder of your HomeServer and (re)start HomeServer Experte. You'll find the module in the folder Smarterliving. 

Usage
-----
Create (at least) two new HS Internal _14-Byte text_ Objects: 
  - Pushover Message 
  - Pushover Status 

Using the Graphic Logic Editor, create a new worksheet and add the Smarterliving\Pushover logic element to the worksheet. 

#### Input 1 - Pushover URL
__Required:__ Copy/Paste your Pushover API URL in this field. This URL currently defaults to: 
```https://api.pushover.net/1/messages.json ```

#### Input 2 - Message
__Required:__ Connect this input with the HS Internal Communication Object ```Pushover Message``` that you've created earlier.

#### Input 3 - Token
__Required:__ Pushover Application Token. You'll get one after you've created a Pushover Application. 

#### Input 4 - User 
__Required__: Pushover User ID. You'll find this in your dashboard. 

#### Input 5, 6, 7, 8, 10 and 11
_Optional:_ You can customize your message using these fields according to the Pushover documentation

#### Input 9 - Priority
_Optional:_ Pushover offers a few priorities for messages. All priorities, except ```2``` are supported. Priority ```2``` requires logic for accepting client/device acknowledgements. This functionality is currently not planned for 19626_Pushover.

#### Output 1 - Status
Currently 19626_Pushover does not output a status, but at least one output is required by the HomeServer. Connect this output to the HS Internal Communication Object ```Pushover Status``` that you've created earlier. 

You are now ready to start using 19626_Pushover! Using any of the supported means to set a value to a Communication Object will send your message to Pushover right away. 

Files Included
--------------
- 19626_Pushover_Vx.xx.hsl - HomeServer Logic file. Copy this to your logic folder. 
- 19626_Pushover.py - Source in Python
- log19626.html - Helpfile. Copy this to html\de or html\en 
- LICENSE - GNU v3 Public License 
- LogikGen.py - KNX-User-Forum Logik Tester, very useful tool if you want to debug logic modules. Used by test.sh
- test.sh - simple script that compiles the source and starts LogikGen for debugging. 
- README.md - this file 

Support
-------
Non whatsoever. Feel free to raise an issue on Github though and/or ask for help at [KNX-User-Forum](http://knx-user-forum.de). 

The module was tested and runs succesfully on a HomeServer 4 with Experte 4.4 (4.4.0.151203R). However, I'm not an active user of [Pushover](https://pushover.net) and created this Logic module just as a "proof of concept".

Credits
-------
Credits where credits are due! 

Out of the box a Gira HomeServer can do many things, however connecting to [Pushover](https://pushover.net), which requires the use of well established standards like HTTPS, POST and JSON is a step to far for a Gira HomeServer.

Luckily some fine folks at the German [KNX User Forum](http://knx-user-forum.de) have found a way to extend the HomeServer logic modules, which are written in a subset of the Python language, enabling developers to use almost all of the full power of the Python language and it's built-in modules like json, urllib2 etc. 

This logic module would not be possible without their efforts.

Roadmap
-------
I'm not an active user of [Pushover](https://pushover.net), so I have no further plans. 

However, as this is open source and this module is available on [Github](https://github.com/ottonet/19626_Pushover) feel free to issue a PR if you have the time and knowledge to add new features or fix bugs!  