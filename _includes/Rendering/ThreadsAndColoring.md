
{% include alertNoTitle.html  type="info" content="If you are color blind please see <a href=\"../../Roadmap/ColorBlindMode\">Color blind mode</a>." %}

Every thread rendered is assigned the most diferent color available, this is why the first 3 threads are Reg, Green and Blue (RGB)
Then it will start using the most different shades of RGB and so forward.


{% include alertNoTitle.html  type="warning" content="This also means that with allot of threads rendered colors can start look quite similar! always check the thread Id by hovering over it when making assumsions based on the render." %}

The Lines between the functions called by a thread applies this color, also you can specifiy in the [settings](#settings-window) wheter the background of a function also gets colored in by setting the scale on wich that should happen. 

We change the transparency of the applied color when a function is not active anymore. 
You can see an example of this in the screenshots above, for example on the first screenshot on the function that has the tooltip open, the red color got much darker as the background is dark.

The background will be colored in with this color for a time after it is not active anymore specified in the [settings](#settings-window), this is to make sure you see that a function has been called as we can profile allot of functions in a second.