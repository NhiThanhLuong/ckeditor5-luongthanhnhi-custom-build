###Installation:
Using npm:

```bash
$ npm install ckeditor5-luongthanhnhi-custom-build
```

Using yarn:

```bash
$ yarn add ckeditor5-luongthanhnhi-custom-build
```

###Rebuilding editor:

```bash
$ npm run build
```

```bash
$ yarn build
```

How to use, Ex:

```js
import ClassicEditor from "ckeditor5-luongthanhnhi-custom-build/build/ckeditor";
import { CKEditor } from "@ckeditor/ckeditor5-react";

const FormCkeditor = ({ name, label, rules, data, onFocus, ...props }) => {
  const config = {
    extraPlugins: [uploadPlugin],
    toolbar: [
      "undo",
      "redo",
      "|",
      "heading",
      "|",
      "fontfamily",
      "fontsize",
      "fontColor",
      "fontBackgroundColor",
      "|",
      "bold",
      "italic",
      "strikethrough",
      "subscript",
      "superscript",
      "code",
      "|",
      "link",
      "uploadImage",
      "blockQuote",
      "codeBlock",
      "|",
      "alignment",
      "|",
      "bulletedList",
      "numberedList",
      "todoList",
      "outdent",
      "indent",
    ],
  };

  function uploadAdapter(loader) {
    return {
      upload: async () => {
        //Handle upload
      },
    };
  }

  function uploadPlugin(editor) {
    editor.plugins.get("FileRepository").createUploadAdapter = (loader) => {
      return uploadAdapter(loader);
    };
  }

  return (
    <CKEditor
      editor={ClassicEditor}
      data={data}
      config={config}
      onFocus={onFocus}
      {...props}
    />
  );
};

export default FormCkeditor;
```
