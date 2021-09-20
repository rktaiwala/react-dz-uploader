# React Dz Uploader


[![NPM](https://img.shields.io/npm/v/react-dz-uploader.svg)](https://www.npmjs.com/package/react-dz-uploader)
[![npm bundle size (minified + gzip)](https://img.shields.io/bundlephobia/minzip/react-dz-uploader.svg)](https://www.npmjs.com/package/react-dz-uploader)

React Dz Uploader is a customizable file dropzone and uploader for React. It is same as the original react-dropzone-uploader except that it features for preview of PDF files while uploading.


## Features
- Preview for PDF files
- Detailed file metadata and previews, especially for image, video and audio files
- Upload status and progress, upload cancellation and restart
- Easily set auth headers and additional upload fields ([see S3 examples](https://react-dropzone-uploader.js.org/docs/s3))
- Customize styles using CSS or JS
- Take full control of rendering with component injection props
- Take control of upload lifecycle
- Modular design; use as standalone dropzone, file input, or file uploader
- Cross-browser support, mobile friendly, including direct uploads from camera
- Lightweight and fast
- Excellent TypeScript definitions

![](https://raw.githubusercontent.com/fortana-co/react-dropzone-uploader/master/rdu.gif)


## Documentation
<https://react-dropzone-uploader.js.org>


## Installation
`npm i react-dz-uploader`

Import default styles in your app.

~~~js
import 'react-dz-uploader/dist/styles.css'
~~~


## Quick Start
RDU handles common use cases with almost no config. The following code gives you a dropzone and clickable file input that accepts image, audio and video files. It uploads files to `https://httpbin.org/post`, and renders a button to submit files that are done uploading. [Check out a live demo](https://react-dropzone-uploader.js.org/docs/quick-start).

~~~js
import 'react-dz-uploader/dist/styles.css'
import Dropzone from 'react-dz-uploader'

const MyUploader = () => {
  // specify upload params and url for your files
  const getUploadParams = ({ meta }) => { return { url: 'https://httpbin.org/post' } }
  
  // called every time a file's `status` changes
  const handleChangeStatus = ({ meta, file }, status) => { console.log(status, meta, file) }
  
  // receives array of files that are done uploading when submit button is clicked
  const handleSubmit = (files) => { console.log(files.map(f => f.meta)) }

  return (
    <Dropzone
      getUploadParams={getUploadParams}
      onChangeStatus={handleChangeStatus}
      onSubmit={handleSubmit}
      accept="image/*,audio/*,video/*"
    />
  )
}
~~~


## Examples
See more live examples here: <https://react-dropzone-uploader.js.org/docs/examples>.


## Props
Check out [the full table of RDU's props](https://react-dropzone-uploader.js.org/docs/props).


## Browser Support
| Chrome | Firefox | Edge | Safari | IE | iOS Safari | Chrome for Android |
| --- | --- | --- | --- | --- | --- | --- |
| ✔ | ✔ | ✔ | 10+, 9\* | 11\* | ✔ | ✔ |

\* requires `Promise` polyfill, e.g. [@babel/polyfill](https://babeljs.io/docs/en/babel-polyfill)



## Contributing
There are a number of places RDU could be improved; [see here](https://github.com/fortana-co/react-dropzone-uploader/labels/help%20wanted).

For example, RDU has solid core functionality, but has a minimalist look and feel. It would be more beginner-friendly with a larger variety of built-in components.


### Shout Outs
Thanks to @nchen63 for helping with [TypeScript defs](https://github.com/fortana-co/react-dropzone-uploader/blob/master/src/Dropzone.d.ts)!


### Running Dev
Clone the project, install dependencies, and run the dev server.

~~~sh
git clone git://github.com/rktaiwala/react-dz-uploader.git
cd react-dz-uploader
yarn
npm run dev
~~~

This runs code in `examples/src/index.js`, which has many examples that use `Dropzone`. The library source code is in the `/src` directory.


## Thanks
Thanks to `react-dropzone-uploader` ,`react-dropzone`, `react-select`, and `redux-form` for inspiration.

This is just a fork of the original repo and all credit goes to the original author. 
