Simple Draft-js
=====================

Minimal wysiwyg rich editor using draftjs (Rich editor framework for React).

### Install
```
npm i -S simple-draftjs
```

### How to use?
```javascript
import React from 'react';
import { render } from 'react-dom';
import Editor from 'simple-draftjs';

const controls = [
'bold',
'italic',
'underline',
'separator',
'unordered-list',
'separator',
'image',
'link',
'unlink',
'separator',
'code'
];

render(
  <Editor
    getContentAction={printHTML}
    hideButtonAction={closeEditor}
    placeholder={"do somenthing!"}
    controls={controls}
  />,
  document.getElementById('root')
);

function printHTML(content) {
  console.log("func ok");
}

function closeEditor() {
  console.log("close");
}
```
### Options
Options should be set via props

##### getContentActions (required)
[function] callback that return html or markdown content when "send" button is clicked or the state change
```javascript
function getContent(content) {
    console.log("html content", content); // <p>something</p>
}
<Editor getContentAction={getContent} />
```

##### placeholder (optional)
[string] placeholder.

##### controls (optional)
[array] list of elements to show as button options
Note: separator is the line for serparate items "|"
```javascript
const controls = [
'bold',
'italic',
'underline',
'separator',
'unordered-list',
];
<Editor controls={controls} />
```
##### export (optional)
[option: "html", "markdown"]
default: "html"

### How to Run?

```
npm install
npm start
open http://localhost:3002
```
#### Contribute: https://github.com/jhta/simple-draftjs

### Dependencies

* [React](https://facebook.github.io/react/)
* [Webpack](https://webpack.github.io/)
* [draft-js](https://facebook.github.io/draft-js)
* [webpack-dev-server](https://github.com/webpack/webpack-dev-server)
* [babel-loader](https://github.com/babel/babel-loader)
* [react-hot-loader](https://github.com/gaearon/react-hot-loader)
