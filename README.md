# RawJavascript-usage-example
An example how to use OpenSheetMusicDisplay with plain JS/HTML. http://opensheetmusicdisplay.org

## Usage
* Clone or download this repository

* Download an OSMD build (`opensheetmusicdisplay.min.js`) from our [Github Releases](https://github.com/opensheetmusicdisplay/opensheetmusicdisplay/releases)
  * put it in the same folder (where the index.html already is).
* Open `index.html` with your browser of choice (we mostly use and support Chrome)
  * Select a sample xml or musicxml file to load (we provide one in this repository)
  * You should be able to load and see up to ten scores
* Alternatively, open indexSimpler.html, which is a bit simplified and only shows one score at a time.

For a screenshot, see the [Wiki](https://github.com/opensheetmusicdisplay/RawJavascript-usage-example/wiki).

## Using a local server to serve files (node http-server)
The code becomes much simpler when not using a choose file dialogue:
* [Install npm](https://nodejs.org/en/download/), open a console/terminal window
* Run `npm install http-server -g`.
* Run `http-server ./resources -p 8080 --cors`
* open `indexHTTPServer.html` or `indexHTTPServer-fetch.html` (alternative method)
Note: This may still cause CORS issues with Chrome, even with `http-server --cors`. Try Firefox.
The next section explains why we use a file server.

## File Loading
Due to [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) security settings, it's unfortunately hard to access files from your local hard drive directly via script, without file choosing dialogue.
`indexCORS.html` does this and is the simplest possible implementation of OSMD.
But browsers like Chrome will block this by default.
That's why we used a local file server in the previous example.
