{{- if not ($.Page.Scratch.Get "embed-pdf-count") -}}

<script type="text/javascript" src= '/js/pdf-js/build/pdf.js'></script>

<style>
  #embed-pdf-container {
    position: relative;
    width: 100%;
    height: auto;
    min-height: 20vh;
    /* overflow-y:scroll; */
  }
  
  .pdf-canvas {
    border: 1px solid black;
    direction: ltr;
    width: 100%;
    height: auto;
    display: none;
  }
  
  #the-canvas {
    border: 1px solid black;
    direction: ltr;
    width: 100%;
    height: auto;
    display: none;
  }
  
  
  .pdf-loadingWrapper {
    display: none;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 350px;
  }
  
  .pdf-loading {
    display: inline-block;
    width: 50px;
    height: 50px;
    border: 3px solid #d2d0d0;;
    border-radius: 50%;
    border-top-color: #383838;
    animation: spin 1s ease-in-out infinite;
    -webkit-animation: spin 1s ease-in-out infinite;
  }
  
  {{/*  Download link  */}}
  
  
  
  #overlayText {
    word-wrap: break-word;
    display: grid;
    justify-content: end;
  }
  
  #overlayText a {
    position: relative;
    top: 10px;
    right: 4px;
    color: #000;
    margin: auto;
    background-color: #eeeeee;
    padding: 0.3em 1em;
    border: solid 2px;
    border-radius: 12px;
    border-color: #00000030;
    text-decoration: none;
  }
  
  #overlayText svg {
    height: clamp(1em, 2vw, 1.4em);
    width:  clamp(1em, 2vw, 1.4em);
  }
  
  
  
  @keyframes spin {
    to { -webkit-transform: rotate(360deg); }
  }
  @-webkit-keyframes spin {
    to { -webkit-transform: rotate(360deg); }
  }
  </style>
{{- end -}}

{{- $.Page.Scratch.Add "embed-pdf-count" 1 -}}
<div class="embed-pdf-container" id="embed-pdf-container-{{ substr (.Get "url" | md5) 0 8 }}">
    <div class="pdf-loadingWrapper" id="pdf-loadingWrapper-{{ substr (.Get "url" | md5) 0 8 }}">
        <div class="pdf-loading" id="pdf-loading-{{ substr (.Get "url" | md5) 0 8 }}"></div>
    </div>
    <div id="overlayText">
      <a href="{{ .Get "url" }}" aria-label="Download" download>
        <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 18 18">
            <path d="M9 13c.3 0 .5-.1.7-.3L15.4 7 14 5.6l-4 4V1H8v8.6l-4-4L2.6 7l5.7 5.7c.2.2.4.3.7.3zm-7 2h14v2H2z" />
        </svg>
      </a>
    </div>
    <canvas class="pdf-canvas" id="pdf-canvas-{{ substr (.Get "url" | md5) 0 8 }}"></canvas>
</div>

<div class="pdf-paginator" id="pdf-paginator-{{ substr (.Get "url" | md5) 0 8 }}">
    <button id="pdf-prev-{{ substr (.Get "url" | md5) 0 8 }}">Previous</button>
    <button id="pdf-next-{{ substr (.Get "url" | md5) 0 8 }}">Next</button> &nbsp; &nbsp;
    <span>
      <span class="pdf-pagenum" id="pdf-pagenum-{{ substr (.Get "url" | md5) 0 8 }}"></span> / <span class="pdf-pagecount" id="pdf-pagecount-{{ substr (.Get "url" | md5) 0 8 }}"></span>
    </span>
    <a class="pdf-source" id="pdf-source-{{ substr (.Get "url" | md5) 0 8 }}" href="{{ .Get "url" }}">[pdf]</a>
</div>

<noscript>
View the PDF file <a class="pdf-source" id="pdf-source-noscript-{{ substr (.Get "url" | md5) 0 8 }}" href="{{ .Get "url" }}">here</a>.
</noscript>

<script type="text/javascript">
    (function(){
    var url = '{{ .Get "url" }}';

    var hidePaginator = "{{ .Get "hidePaginator" }}" === "true";
    var hideLoader = "{{ .Get "hideLoader" }}" === "true";
    var selectedPageNum = parseInt("{{ .Get "renderPageNum" }}") || 1;

    // Loaded via <script> tag, create shortcut to access PDF.js exports.
    var pdfjsLib = window['pdfjs-dist/build/pdf'];

    // The workerSrc property shall be specified.
    if (pdfjsLib.GlobalWorkerOptions.workerSrc == '')
      pdfjsLib.GlobalWorkerOptions.workerSrc = "{{.Site.BaseURL}}" + 'js/pdf-js/build/pdf.worker.js';

    // Change the Scale value for lower or higher resolution.
    var pdfDoc = null,
        pageNum = selectedPageNum,
        pageRendering = false,
        pageNumPending = null,
        scale = 3,
        canvas = document.getElementById('pdf-canvas-{{ substr (.Get "url" | md5) 0 8 }}'),
        ctx = canvas.getContext('2d'),
        paginator = document.getElementById("pdf-paginator-{{ substr (.Get "url" | md5) 0 8 }}"),
        loadingWrapper = document.getElementById('pdf-loadingWrapper-{{ substr (.Get "url" | md5) 0 8 }}');


    // Attempt to show paginator and loader if enabled
    showPaginator();
    showLoader();

    /**
     * Get page info from document, resize canvas accordingly, and render page.
     * @param num Page number.
     */
    function renderPage(num) {
      pageRendering = true;
      // Using promise to fetch the page
      pdfDoc.getPage(num).then(function(page) {
        var viewport = page.getViewport({scale: scale});
        canvas.height = viewport.height;
        canvas.width = viewport.width;

        // Render PDF page into canvas context
        var renderContext = {
          canvasContext: ctx,
          viewport: viewport
        };
        var renderTask = page.render(renderContext);

        // Wait for rendering to finish
        renderTask.promise.then(function() {
          pageRendering = false;
          showContent();

          if (pageNumPending !== null) {
            // New page rendering is pending
            renderPage(pageNumPending);
            pageNumPending = null;
          }
        });
      });

      // Update page counters
      document.getElementById('pdf-pagenum-{{ substr (.Get "url" | md5) 0 8 }}').textContent = num;
    }

    /**
     * Hides loader and shows canvas
     */
    function showContent() {
      loadingWrapper.style.display = 'none';
      canvas.style.display = 'block';
    }

    /**
     * If we haven't disabled the loader, show loader and hide canvas
     */
    function showLoader() {
      if(hideLoader) return
      loadingWrapper.style.display = 'flex';
      canvas.style.display = 'none';
    }

    /**
     * If we haven't disabled the paginator, show paginator
     */
    function showPaginator() {
      if(hidePaginator) return
      paginator.style.display = 'block';
    }

    /**
     * If another page rendering in progress, waits until the rendering is
     * finished. Otherwise, executes rendering immediately.
     */
    function queueRenderPage(num) {
      if (pageRendering) {
        pageNumPending = num;
      } else {
        renderPage(num);
      }
    }

    /**
     * Displays previous page.
     */
    function onPrevPage() {
      if (pageNum <= 1) {
        return;
      }
      pageNum--;
      queueRenderPage(pageNum);
    }
    document.getElementById('pdf-prev-{{ substr (.Get "url" | md5) 0 8 }}').addEventListener('click', onPrevPage);

    /**
     * Displays next page.
     */
    function onNextPage() {
      if (pageNum >= pdfDoc.numPages) {
        return;
      }
      pageNum++;
      queueRenderPage(pageNum);
    }
    document.getElementById('pdf-next-{{ substr (.Get "url" | md5) 0 8 }}').addEventListener('click', onNextPage);

    /**
     * Asynchronously downloads PDF.
     */
    pdfjsLib.getDocument(url).promise.then(function(pdfDoc_) {
      pdfDoc = pdfDoc_;
      var numPages = pdfDoc.numPages;
      document.getElementById('pdf-pagecount-{{ substr (.Get "url" | md5) 0 8 }}').textContent = numPages;

      // If the user passed in a number that is out of range, render the last page.
      if(pageNum > numPages) {
        pageNum = numPages
      }

      // Initial/first page rendering
      renderPage(pageNum);
    });
    })();
</script>
