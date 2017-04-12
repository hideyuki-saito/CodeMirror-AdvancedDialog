# CodeMirror-AdvancedDialog
A more advanced dialog for CodeMirror allowing for multiple inputs and buttons.

To create a new dialog, use the following command:

`cm.openAdvancedDialog(template, opts);`

The first parameter is an html template or DOM node much like the vanilla dialog, and the second is an options object with the following properties:

- **shrinkEditor** (bool) - If set to true, the editor will shrink to make room for the dialog in order to prevent the dialog obscuring any text.
- **inputBehaviours** (object) - an object with behaviours for each input in the order that they appear in the template.
  * *closeOnEnter* (bool) - if true, the dialog will close if the user hits enter when this field has focus
  * *closeOnBlur* (bool) - if true, the dialog will close if this field loses focus
  * *callback* (function) - a callback function that will be executed if the user hits enter when this field has focus.  The function receives two parameters - the first is an array of the input fields in the dialog and the second is the DOM event.
- **buttonBehaviours** (object) - an object with behaviours for each button in the order that they appear in the template.
  * *callback* (function) - a callback function that will be executed if the user hits enter when this field has focus.  The function receives two parameters - the first is an array of the input fields in the dialog and the second is the DOM event.
  
## To install

You can install either manually or via npm.  The latter is very simple:

    npm install --save codemirror-advancedsearch

If you want to install manually, however, you will need to include both `advanced-dialog.js` and `dialog.css` in your page.

## Changes

### v1.1.0 - 2017-04-12

The `onInput`, `onKeyDown` and `onKeyUp` behaviours for input boxes now match the signature of the callback, in that they each are passed two parameters: an array of the inputs in the dialog, and the DOM event that triggered the function call.