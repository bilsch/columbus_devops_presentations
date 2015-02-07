== reveal.js

I could not figure out how to add a dir from a remote tagged release
of reveal.js. Contents of reveal.js-3.0.0 are from
https://github.com/hakimel/reveal.js/tree/3.0.0 and are subject to
their license
  - https://github.com/hakimel/reveal.js/tree/3.0.0/LICENSE

Incidentally if someone knows how to add a remote/submodule against
a tagged release post a pull request and I'll be happy to merge it!

== Installation

1. Install nodejs
  * I used pre-built one from http://nodejs.org/download/
1. cd reveal.js && npm install && npm install -g grunt-cli
1. mv cap_pres.html reveal.js/index.html
1. grunt serve
