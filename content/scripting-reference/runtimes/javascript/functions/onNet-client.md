---
title: onNet - client
---

Use `onNet` function when you want to listen from client **AND** from server.\
This declares an event which gets triggered with [emit](/scripting-reference/runtimes/javascript/functions/emit-client) (from client) or [emitNet](/scripting-reference/runtimes/javascript/functions/emitNet-server) (from server).

## Signature

```ts
function onNet(eventName: string, fn: Function) => void
```

### Required arguments

- **eventName**: The event name you want to expose.
- **fn**: The function to execute when the event get triggered.

## Examples

```ts
let myNameIs = "Carl";

onNet("foo:serverCalledYou", (newName: string) => {
    myNameId = newName;
    console.warn(`Someone change your name to ${newName}`);

    if (newName.toLowerCase() === "idiot") {
        console.warn("Looks like he didn't like you.");
    }
});
```
