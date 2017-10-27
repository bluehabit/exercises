## Explanation

You can wrap everything on a div with hard coded width and height and absolute positioning. If so, your elements will never move, assuming the parent that contains all the content is actually out of the document flow and has always the same size.

Absolute elements are absolute positioned in relation to its parent, so if the parent has an absolute position and a fixed width and height, it prevents its content from being moved as the screen size changes.

Hard coding the size and absolute positioning it is an option: http://jsfiddle.net/gespinha/f6zPy/1/

HTML

Source:
https://stackoverflow.com/questions/18708772/page-elements-moving-with-different-screen-resolutions

![f](https://imgur.com/vZfC6yi.png)

## Center Position Absolute Elements

You can center the main wrapper if you would like. To center absolute positioned elements add the following markup

```
#wrapper {
    width:1024px;
    height:1024px;
    position:absolute;
    background:#00f;

    /*added code*/
    left: 0; 
    right: 0; 
    margin-left: auto; 
    margin-right: auto; 
}
```
