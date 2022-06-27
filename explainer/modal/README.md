# :modal psedo class

## Details

From the level 4 specs :
>The :modal pseudo-class represents an element which is in a state
>that excludes all interaction with elements outside it
>until it has been dismissed.
>Multiple elements can be :modal simultaneously,
>with only one of them active (able to receive input).

## Examples - dialog

Assume that we have dialog element as follows.
```html
<dialog id="dialog">this is dialog</dialog> 
```

We can get state as follows.
```javascript
const dialog = document.getElementById("dialog");

dialog.showModal();
dialog.matches(":modal"); // true

dialog.close();
dialog.matches(":modal"); // false
```

## Examples - fullscreen

Assume that we have fullscreen element as follows.
```html
<div id="container" onclick="handleClick()">
</div>
```

We can get state as follows.
```javascript
const container = document.getElementById("container");
const handleClick = () => {
  container.requestFullscreen();
  container.matches(":modal"); // true

  container.exitFullscreen();
  container.matches(":modal"); // false
}
```
