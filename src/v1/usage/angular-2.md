---
title: Angular 2+
type: usage
order: 102
published: true
---

## Setup

To use Anymod with [Angular 2+](https://angular.io/), add the Anymod script tag before (above) your Angular script tags in your HTML. Then make `Anymod` available in your `.ts` file:

```ts
declare var Anymod: any;
```

Now you can add your mod and call `Anymod.render()` to render the mod(s):

```ts
@Component({
  ...
  template: `<div id=anymod-mldrn></div>`,
})
class AnymodDemo {
  ...
  ngOnInit() {
    Anymod.render()
  }
}
```

You can use `Anymod.render()` by itself or with a callback or promise. See the section on [Anymod.render](/v1/api/index.html#Anymod-render-function-options-options) for more.

## Example

The following example shows a mod being rendered in typescript with `Anymod.render`:

<iframe width="100%" height="650" src="//jsfiddle.net/component/3nvx3kms/embedded/js,html,result/" allowpaymentrequest allowfullscreen="allowfullscreen" frameborder="0"></iframe>

## Rendering multiple mods

You can render multiple mods the same way as a single mod, and you only need to call `Anymod.render()` once:

```ts
@Component({
  ...
  template: `
    <div id=anymod-mldrn></div>
    <div id=anymod-eoako></div>
    <div id=anymod-klaln></div>
  `,
})
class AnymodDemo {
  ...
  ngOnInit() {
    Anymod.render()
  }
}
```

## Re-rendering

You can call `Anymod.render()` as often as you'd like in your Angular code (or elsewhere). This method will not lead to an API call every time; if a mod has already been fetched once, `Anymod.render()` will use that data instead of making another API call.

See the section on [Anymod.render](/v1/api/index.html#Anymod-render-function-options-options) for more.
