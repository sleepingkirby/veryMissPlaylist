# veryMissPlaylist
simple/slim HTML and javascript based playlist for media files.

basically, if you have several urls that's an mp4 file, you can use to this queue up a list of them. And when you play, it'll play them in order, decrementing the list as it goes (because you've watched it.).

Something I jammed out quickly. Just a javascript/HTML page that allows you to queue up a list of media files reachable and playable by the browser. Just open mplayer.html to use.

Some considerations:

1) most browsers will do webm and mp4 (h.264). But other formats and/or extensions (.avi's or .mkv's for example) are dicey. Addendum: I've added the option to export to .m3u file. Since VLC *DOES* play from http:// urls (not sure what I did before that made it so that it wasn't working.), this will .m3u playlist file can be directl opened by VLC and played. Thus, circumventing the lack support for .mkv's and .avi's on the webbrowser. (Speaking of which, those came first, are less cpu-intensive to playback and isn't a proprietary format attributed to h.264 codec. Why is that supported but many other open source ones aren't?)
2) the file browser reads off of apache's +indexes page. "what does that mean?" It means that, sometimes webservers like apache, can list the files it has in a directory rather than default to an index.html(as an example) page. The file browser reads that page and displays it to you for your convenience. It's basically scraping all the a tags that it thinks looks like a viable link. So it's possible to navigate to places that doesn't make sense.
3) CORS... If you're serving this page from a webserver and the movies are on the same server, you'll probably not have a problem. If you're running the page locally, the browser you're using might deny browsing the file listings page. If that's the case, you'll either need to restart the browser without web security (something like, start the executable for chrome with "google-chrome --disable-web-security") or set the webserver to be CORS compliant (have the webserver add the header Access-Control-Allow-Origin:* to the response). I don't like it either. I did see that there are add-ons/plug-ins/whatever for browsers that will add that to all the response headers. Might be a good idea.


That's it. Have fun. 
