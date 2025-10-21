# Modifications
added more keys so you can use a keybord / Num Pad / Presentation Remote natively.
```
"key_next_page" : [ 57, 96, 109, 108, 106 ],
// 57 - Space, 96 - KPEnter, 109 - PageDown, 108 - Down, 106 - Right
"key_prev_page" : [ 104, 78, 103, 105 ],
// 104 - PageUp, 78 - KPPlus, 103 - Up, 105 - Left
```
(KP means Num Pad)

# KindleLazy 0.9 - cearp

Only tested on PW3, nothing else!

At the moment this only reads from event2 and event3 - this is what my device reads as.
This should be improved later.

There is no hotplugging, have the device inserted before starting. If the device is removed, this app may quit.

The page turn direction can be reversed (pass argument '-reverse'), so that your 'forward' button can still advance you to the next page.
For example, with books that are 'right to left', where the next page is on the left, you would reverse the direction.

The program will not work without a config file named 'config.json' in the same directory.
NOT menu.json and NOT config.xml, these are files for KUAL.

Here is a sample (and the default) config file:

{
   "key_brightness_down" : [ 115 ],
   "key_brightness_up" : [ 114 ],
   "key_next_page" : [ 104, 103, 106 ],
   "key_prev_page" : [ 109, 108, 105 ],
   "key_wake" : [ 15 ]
}

Errors in the config file are not handled, it will probably crash.
Beware of commas and other punctuation.

Enter the keycodes for the keys you want to trigger the actions.

For the config above, the key codes represent:

104 = KEY_PAGEUP            
109 = KEY_PAGEDOWN

103 = KEY_UP
108 = KEY_DOWN

105 = KEY_LEFT
106 = KEY_RIGHT

114 = VOLUME_DOWN
115 = VOLUME_UP

15 = TAB


I can see some keycodes here, I am not sure if some devices produce different ones.
https://android.googlesource.com/platform/frameworks/base/+/cd92588/data/keyboards/Generic.kl

It is best to run 'evtest /dev/input/mydevice', and press buttons and see what values are given.
