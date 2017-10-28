On previous versions if you resized the window it would cause the puzzle pieces to move along with it. To fix this you have to give the main container position `relative` or `absolute` . This introduces a new error because when something has position `relative` or `absolute` its is in relation to its `parent` container. Whatever the `main` container is offset by, your mouse coordinates will be off by that much as well. 

To correct for this we can use 
```
	var pieceParent = piece.offsetParent.getBoundingClientRect();
	piece.style.left = evt.clientX - pieceParent.x - 55 + 'px';
	piece.style.top = evt.clientY - pieceParent.y - 55 + 'px';
 ```
