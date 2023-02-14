[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org) ![visitors](https://visitor-badge.glitch.me/badge?page_id=AlanTanner.pdfjs-hugo-module)
# pdfjs-hugo-module 
This is a fork of [hugo-embed-pdf-shortcode](https://github.com/anvithks/hugo-embed-pdf-shortcode) created by [Anvinth KS](https://github.com/anvithks) with pdf.js v3.3.122 and optimized for use as a Hugo Module.
---  
# Table of Contents  

* [Online Demo](https://hugo-embed-pdf.netlify.app/)
* [Introduction](#introduction)
* [Setup](#setup)  
* [Usage](#usage)  
* [FAQ](#faq)  
* [Support](#support)  
* [Who uses embed-pdf](#who-uses-hugo-embed-pdf-shortcode)
* [License](#license)  

---

## Introduction  
[\[Back to Top\]](#table-of-contents)

This is a [Hugo Shortcode](https://gohugo.io/extras/shortcodes/) developed for use in [Hugo](https://gohugo.io/) based websites. This shortcode allows you to embed a PDF file in a page on your Hugo website. It is developed using the [PDF.js](https://mozilla.github.io/pdf.js/) library by Mozilla.

![hugo-embed-pdf-shortcode cover](https://github.com/anvithks/hugo-embed-pdf-shortcode/blob/master/hugo-embed-pdf-cover.png)

## Setup  
[\[Back to Top\]](#table-of-contents)

**Note:**  This shortcode is for use in Hugo based websites. It will not work anywhere else. 

Init your project as a hugo module if not already.

```
hugo mod init <your_repo_url>
```

Add this module to site config. The following is an example of yaml, and the same is true for toml and json.

```
module:
  imports:
  - path: github.com/AlanTanner/pdfjs-hugo-module
```

<br />

## Usage  
[\[Back to Top\]](#table-of-contents)

In your Hugo website place the following shortcode in any of the markdown pages. 
```
{{< embed-pdf url="./path/to/pdf/file/example.pdf" >}}

```

To hide pagination
```
{{< embed-pdf url="<path>/example.pdf" hidePaginator="true" >}}
```


To render a selected page number
```
{{< embed-pdf url="<path>/example.pdf" renderPageNum="5" >}}
```

To hide loading spinner
```
{{< embed-pdf url="./path/to/pdf/file/example.pdf" hideLoader="true" >}}
```

### Parameters
- **url (required)** : The relative location of the file.  
- **hidePaginator (optional)**: Boolean which expects `true` or `false`. Hides the paginator for single page documents. 
- **renderPageNum (optional)**: Integer which expects any number from `1` up to the last page number in the document. Will render that specific page on initial load.
- **hideLoader (optional)**: Boolean which expects `true` or `false`. Hides the loading spinner while your document loads. 

<br />

**Note:** Currently supports local file embed. If absolute URL from the remote server is provided, configure the CORS header on that server.


## FAQ  
[\[Back to Top\]](#table-of-contents)

## Support  
[\[Back to Top\]](#table-of-contents)
You an reach me at:
- Twitter : [@anvith3](https://twitter.com/anvith3)

For any bugs, enhancement requests, feature requests please raise issues [here](https://github.com/anvithks/hugo-embed-pdf-shortcode/issues)

## Who uses Hugo Embed Pdf Shortcode
[\[Back to Top\]](#table-of-contents)

[Dirk's Changelog](https://changelog.deimeke.ruhr/2019/08/11/workshop-20190811/)

## License  
[\[Back to Top\]](#table-of-contents)

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
