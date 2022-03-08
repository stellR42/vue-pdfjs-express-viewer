# Vue PDFJS Express Wrapper

Simple Vue wrapper for [@pdftron/pdfjs-express](https://www.npmjs.com/package/@pdftron/pdfjs-express). Supports Vue 3. 

## Usage

1. Install package

`npm i vue-pdfjs-express-viewer`

2. Copy assets in `pdfjs-express` folder to your public/static folder
3. Instantiate component

```vue
import { PdfApp } from "vue-pdfjs-express-viewer";

<pdf-app
  :src="file"
  :license-key="licenseKey"
  asset-path="/pdfjs-express"
></pdf-app>
```

### Props

- `src: File | Blob` - file source
- `licenseKey: string` - PDFJS Express license key. Can be generated [here](https://pdfjs.express/profile)
- `assetPath: string` - absolute path to PDFJS Express assets from your public/static folder
