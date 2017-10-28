
### Read Me

On previous versions if you resized the window it would cause the puzzle pieces to move along with it. To fix this you have to give the main container position `relative` or `absolute` . This introduces a new error because when something has position `relative` or `absolute` its is in relation to its `parent` container. Whatever the `main` container is offset by, your mouse coordinates will be off by that much as well. 

To correct for this we can use 
```
	var pieceParent = piece.offsetParent.getBoundingClientRect();
	piece.style.left = evt.clientX - pieceParent.x - 55 + 'px';
	piece.style.top = evt.clientY - pieceParent.y - 55 + 'px';
 ```



### Z-index Issue

The original issue was when I placed a puzzle piece over its container it would fall behind that div, causing the puzzle piece to disapear. To fix this I added a default `z-index` value to all the puzzle pieces so they would be higher, and thus appear on top of, the div containers.

![f](https://imgur.com/EYRSOh6.gif)

When your selected piece mouses over another puzzle piece, by default, what determines wether the selected puzzle piece appears on top or below the other piece is what order it is in the html. 

![f](https://imgur.com/pLN4YrC.png)

To help correct for this I temporarily give the selected piece a z-index value of `999` with the class `.highZindexValue`. 

![f](https://imgur.com/AcusiIu.png)

On my initial attempt I used CSS selector attributes to target the puzzle pieces and add a `z-index` of `20`. The problem with this is how specific it is. This will override the toggle `z-index:999` which I gave to the selected piece. Causing the selected piece to still appear below another puzzle piece, if that piece is higher than the selected piece in the raw html.

You can see below that `.highZindexValue` has a strikethrough. 

![f](https://imgur.com/crEeXNo.gif)

To fix this I used a class instead of the specificity of CSS attribute selectors that override other values.

![f](https://imgur.com/G1EW3iz.png)

### Working


![f](https://imgur.com/KDGEyR4.png)
