# TinyMCE Dropzone Plugin

<span class="badge-patreon"><a href="https://www.patreon.com/dimakorotkov" title="Donate to this project using Patreon"><img src="https://img.shields.io/badge/patreon-donate-yellow.svg" alt="Patreon donate button" /></a></span>
<span><a href="https://buymeacoff.ee/NXR1ZkP" title="Donate to this project using Buy Me A Coffee" rel="nofollow"><img src="https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg" alt="Buy Me A Coffee donate button"></a></span>

This plugin uses [Dropzone](https://www.dropzonejs.com) library for drag’n’drop file uploads with image previews.

This plugin is compatible with TinyMCE 5/6 and Dropzone 5.

## Install

### NPM:
```
npm i @dimakorotkov/tinymce-dropzone --save
```

You can install dropzone and tinymce from npm
```
npm i dropzone --save
```
```
npm i tinymce --save
```



### Download

* [Latest build](https://github.com/dimakorotkov/tinymce-dropzone/archive/master.zip)

## Usage

### TinyMCE editor

Configure your TinyMCE init settings by adding `external_plugins` and usage of `dropzone`: 

```
tinymce.init({
  ...
  external_plugins: {'dropzone': '/your-path-to-plugin/@dimakorotkov/tinymce-dropzone/plugin.min.js'},
  toolbar: 'dropzone',
  dropzone: {
    js: '/path-to-dropzone/dropzone.min.js', //required path to dropzone js
    css: '/path-to-dropzone/dropzone.min.css', //required path to dropzone css
    action: '/path-to-upload-action', //required path to upload action
    files: [], //optional existing files
    //title: 'Files', //optional button tooltip and dialog title
    //icon: 'upload', //optional button icon
    //okTitle: 'OK', //optional OK button text
    //removeTooltip: 'Remove', //optional tooltip for remove file button
    //downloadTooltip: 'Donwload', //optional tooltip for download file button
    //insertLinkTooltip: 'Insert link', //optional tooltip for insert link button
    //insertImageTooltip: 'Insert image', //optional tooltip for insert image button
    //removeConfirmation: 'Links to the file will be corrupted.', //optional text for remove confirmation dialog
    //config: {} //optional dropzone config
  }
});
```

## File format
Files array in config must contain objects with these properties:  
  name - filename,  
  url - url for downloading file,  
  thumbnail - url for downloading thumbnail,  
  type - mime type.  

Server side script ("action" in config) must return an object with these properties in json format.

## License - MIT
