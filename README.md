# kc-react-pdf-to-text-01

Light-weight memory-safe client library for extracting plain text from pdf files.

## Installing

Using npm:

```js
npm install kc-react-pdf-to-text-01
```

## Example

**Local File Input**

Now add a input tag with type="file" to take file input.

```html
<input type="file" accept="application/pdf" onChange={extractText} />
```

Import the pdf2text function from package

```js
import pdfToText from "kc-react-pdf-to-text-01";

function extractText(event) {
  const file = event.target.files[0];
  pdfToText(file)
    .then((text) => console.log(text))
    .catch((error) => console.error("Failed to extract text from pdf"));
}
```

**Remote PDF File Input**

For Pdf files stored at remote locations

```js
import pdfToText from 'kc-react-pdf-to-text-01'

const pdf_url = "REMOTE_PDF_URL"

function extractText() {
    const file = await fetch(pdf_url)
        .then(res => res.blob())
        .catch(error => console.error(error))

    pdfToText(file)
        .then(text => console.log(text))
        .catch(error => console.error("Failed to extract text from pdf"))
}
```

## Contributing

This project welcomes contributions and suggestions.
# pdf-to-text
