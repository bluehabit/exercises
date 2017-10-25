## Problem

Found something interesting today while getting a div to follow my mouse cursor using mousemove event listener. If you scroll down in your browser while the div is following it will only follow on the x axis, the y axis will still be where you were prior to scrolling. 

I guess this is intended https://developer.mozilla.org/en-US/docs/Mozilla/Performance/Scroll-linked_effects

![f](https://imgur.com/Rs9mTnO.gif)

## Solution

You cannot just disable the `scroll` event, according to this SO post. However one possible solution is to watch for, and disable, specific keys that are pressed such as page up / down, scroll etc.

![f](https://imgur.com/a61pu1D.png)

Another simple solution is to disable the scroll bar from popping up (which prevents scrolling) by using `overflow:hidden`

![f](https://imgur.com/AmN2FoR.png)
