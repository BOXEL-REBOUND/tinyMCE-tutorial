# You chose React
The Official TinyMCE React component integrates TinyMCE into React projects. This procedure creates a basic React application containing a TinyMCE editor based on our Basic example.

For examples of the TinyMCE integration, visit the tinymce-react storybook.

Prerequisites
This procedure requires:

`Node.js` (and `npm`)
Access to `tinymce.min.js` on either:<br />
Tiny Cloud<br />
TinyMCE Self-hosted. See Advanced installation choices for details on self-hosting TinyMCE<br />
**Procedure**
1. On a command line or command prompt, install the Create React App package.

```shell
npm install -g create-react-app
```

2. Create a new React project named tinymce-react-demo.

```shell
create-react-app tinymce-react-demo
```

3. Change into the newly created directory.

```shell
cd tinymce-react-demo
```

4. Install the tinymce-react package and save it to your package.json.


#### NPM
```shell/npm
npm install --save @tinymce/tinymce-react
```

#### YARN

```shell/yarn
yarn add @tinymce/tinymce-react
```

5. Using a text editor, open `/path/to/tinymce-react-demo/src/App.js` and replace the contents with:

```js
import React from 'react';
import { Editor } from '@tinymce/tinymce-react'; 

class App extends React.Component {
  handleEditorChange = (e) => {
    console.log(
      'Content was updated:',
      e.target.getContent()
    );
  }

  render() {
    return (
      <Editor
        initialValue="<p>Initial content</p>"
        init={{
          height: 500,
          menubar: false,
          plugins: [
            'advlist autolink lists link image', 
            'charmap print preview anchor help',
            'searchreplace visualblocks code',
            'insertdatetime media table paste wordcount'
          ],
          toolbar:
            'undo redo | formatselect | bold italic | \
            alignleft aligncenter alignright | \
            bullist numlist outdent indent | help'
        }}
        onChange={this.handleEditorChange}
      />
    );
  }
}

export default App;
```

This JavaScript file will create the class App containing a TinyMCE editor configured to replicate the example on the Basic example page.

6. Provide access to TinyMCE using Tiny Cloud or by self-hosting TinyMCE.

**Tiny Cloud**

Include the apiKey option in the editor element and include your TinyMCE API key. Such as:

```js
<Editor 
 apiKey="afjr4b0jfzxrhryu2m26z97gl2h6acfw2739s51zhfed6nsk"
 init={{ /* your other settings */ }}
/>
```

**TinyMCE Self-hosted**

TinyMCE can be self-hosted by deploying TinyMCE independent of the React application, or bundling TinyMCE with the React application.

A. Deploy TinyMCE independent of the React application

To use an independent deployment of TinyMCE, add a script to either the `<head>` or at the end of the `<body>` of the HTML file, such as:

```html
<script src="/path/to/tinymce.min.js"></script>
```

COPY
To use an independent deployment of TinyMCE with the create a React application, add the script to `/path/to/tinymce-react-demo/public/index.html`.

For information on self-hosting TinyMCE, see Advanced installation choices.

B. Bundling TinyMCE with the React application using a module loader

To bundle TinyMCE using a module loader (such as Webpack and Browserify), see Usage with module loaders.

7. Test the application using the Node.js development server.

To start the development server, navigate to the tinymce-react-demo directory and run:

#### NPM
```shell/npm
npm run start
```

### YARN
```shell/yarn
yarn start
```
To stop the development server, select on the command line or command prompt and press `Ctrl+C`.

To see example and demo files, click [here](../react/).
