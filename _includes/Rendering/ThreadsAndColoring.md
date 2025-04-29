
Every thread rendered is assigned the most different color available, this is why the first 3 threads are Red, Green and Blue (RGB)
Then it will start using the most different shades of RGB and so forward.


{% include alertNoTitle.html  type="warning" content="This also means that with allot of threads rendered colors can start look quite similar! Always check the thread id by hovering over it when making assumptions based on the render." %}

The lines between the functions called by a thread applies this color, also you can specify in the [settings](#settings-window) whether the background of a function also gets colored in by setting the scale on which that should happen. 

We change the transparency of the applied color when a function is not active anymore. 
You can see an example of this in the screenshots above. For example, the functions on the bottom right have a darker red color.

The background will be colored in with this color for a time after it is not active anymore specified in the [settings](#settings-window), this is to make sure you see that a function has been called as we can profile allot of functions in a second.