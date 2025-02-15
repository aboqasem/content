---
title: GlobalEventHandlers.ondrop
slug: Web/API/GlobalEventHandlers/ondrop
page-type: web-api-instance-property
tags:
  - API
  - HTML DOM
  - Reference
  - drag and drop
browser-compat: api.GlobalEventHandlers.ondrop
---
{{ApiRef("HTML DOM")}}

A {{domxref("GlobalEventHandlers","global event handler")}} for the {{domxref("HTMLElement/drop_event", "drop")}}
event.

## Syntax

```js
var dropHandler = targetElement.ondrop;
```

### Return value

- `dropHandler`
  - : The _drop_ event handler for element `targetElement`.

## Example

This example demonstrates the use of the
{{domxref("GlobalEventHandlers.ondrop","ondrop")}} attribute to define an element's
{{domxref("HTMLElement/drop_event", "drop")}} event handler.

```js
<!DOCTYPE html>
<html lang=en>
<title>Examples of using the ondrag Global Event Attribute</title>
<meta content="width=device-width">
<style>
  div {
    margin: 0em;
    padding: 2em;
  }
  #source {
    color: blue;
    border: 1px solid black;
  }
  #target {
    border: 1px solid black;
  }
</style>
</head>
<script>
function drag_handler(ev) {
 console.log("Drag");
}

function dragstart_handler(ev) {
 console.log("dragStart");
 ev.dataTransfer.setData("text", ev.target.id);
}

function drop_handler(ev) {
 console.log("Drop");
 ev.currentTarget.style.background = "lightyellow";

 ev.preventDefault();
 var data = ev.dataTransfer.getData("text");
 ev.target.appendChild(document.getElementById(data));
}

function dragover_handler(ev) {
 console.log("dragOver");
 ev.preventDefault();
}
</script>
<body>
<h1>Examples of <code>ondrag</code>, <code>ondrop</code>, <code>ondragstart</code>, <code>ondragover</code></h1>
 <div class="source">
   <p id="source" ondrag="drag_handler(event);" ondragstart="dragstart_handler(event);" draggable="true">
     Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
 </div>
 <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
</body>
</html>
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("HTMLElement/drop_event", "drop")}}
