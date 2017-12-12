# spiffe.github.io
spiffe.io website source.

The website uses [Jekyll](http://jekyllrb.com/) templates and is hosted on GitHub Pages. Please make sure you are familiar with these before editing.

If you have docker installed, you can run the site locally with:

`docker run --rm --label=jekyll --volume=$(pwd):/srv/jekyll  -it -p 127.0.0.1:4000:4000 jekyll/jekyll jekyll serve`

If you have Ruby and bundle installed, and have run `bundle install`:

`bundle exec jekyll serve`
