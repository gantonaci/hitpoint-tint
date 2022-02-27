# Hitpoint-Tint

A basic FoundryVTT module for tinting tokens based on their current HP.

Intended to make it easier for players to see approximate health of creatures without showing them the health bars.

## Demo
![Demo Animation](demo/HP-Tint-Example.gif)

## Ignore tokens
The following macro will mark the selected tokens to be ignored by the module:
```js
canvas.tokens.controlled.map( token => {
	token.document._actor.setFlag('hitpoint-tint', 'ignore_token', true);
	token.document.update({tint: '#ffffff'});
});
```

Use the following macro for the tint to work again:
```js
canvas.tokens.controlled.map( token => {
	token.document._actor.unsetFlag('hitpoint-tint', 'ignore_token');
});
```

## Requirements / Limitations:
- https://github.com/ardittristan/VTTColorSettings is used for settings / color picking.
- Currently only the 5e module for FoundryVTT is tested / supported. (Enable on other systems at your own risk)
- Token tints will only be updated on the current active scene
- Token tints will only be updated if the current HP changes (i.e. increase in Max HP will not be reflected)
