[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=3MJE3M4FMJYGN&lc=BR&item_name=Shin%2dNiL%27s%20Github&item_number=Github&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donate_SM%2egif%3aNonHosted)

Simple *App invite on Facebook* module for [Godot Game Engine](http://godotengine.org/) (Android only). 

To use it, make sure you're able to compile the Godot android template, you can find the instructions [here](http://docs.godotengine.org/en/latest/reference/compiling_for_android.html). 

For Godot 3.1.0 or higher, remove the line:

	 implementation "com.android.support:support-core-utils:28.0.0"
    
from the file _platform/android/build.gradle.template_ before compiling to avoid conflicts between the support libs.


**Module name (engine.cfg):**
```
[android]
modules="org/godotengine/godot/GodotFacebook"
```

**Functions:**
* init(app_id)
* appInvite(app_link_url, preview_image_url)

**Example:**
```python
func _ready():
    if(Globals.has_singleton("GodotFacebook")):
        fb = Globals.get_singleton("GodotFacebook")
        fb.init(‘YOUR_APP_ID’)

(...)

func _on_share_button_pressed():
    if fb != null:
        fb.appInvite(“YOUR_APP_URL”, ‘YOUR_APP_IMG_URL’)
```        

Any questions? Leave a comment on my blog [http://shinnil.blogspot.com.br](http://shinnil.blogspot.com.br)
