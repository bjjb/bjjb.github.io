CV Generator
============

The [Rakefile] here generates [my CV][cv] in various formats from the
cv.yml file.  It uses a few gems for this:

* [activesupport], for generating the XML/JSON
* [json], for generating JSON on Ruby 1.8
* [wicked_pdf], for the PDF version (note that
  [webkit2pdf] must be installed, or [wkhtmltopdf])
* [haml], for structuring the HTML
* [sass], for generating the style
* [mustache], for generating the text version
* [maruku], for converting the text to HTML

I just run `rake` after updating the YAML file, and everything gets updated.

![Preview here...](https://github.com/bjjb/bjjb.github.io/raw/master/cv/preview.png "The finished product")

Copyright & thanks
------------------

It's free. I got the icons from [here][icons], I think.

TODO
----

- [ ] Improve the PDF generation. Particularly, as webkit2pdf isn't readily
  available on OSX/Windows, make a web-app to do create the PDF, and use that.
- [ ] Be more generic about the name of the file. Rather than insisting on
  _cv_ allow the base file name to be anything.

[Rakefile]: https://github.com/bjjb/bjjb.github.io/blob/master/cv/Rakefile
[cv]: http://jjbuckley.github.com/cv/cv.html
[activesupport]: http://as.rubyonrails.org/
[json]: http://flori.github.com/json/
[wicked_pdf]: https://github.com/mileszs/wicked_pdf
[webkit2pdf]: http://webkit2pdf.sourceforge.net/
[wkhtmltopdf]: http://code.google.com/p/wkhtmltopdf/
[haml]: http://haml.info/
[sass]: http://sass-lang.com/
[mustache]: https://github.com/defunkt/mustache
[maruku]: https://github.com/nex3/maruku
[markdown]: http://daringfireball.net/projects/markdown
[icons]: http://effectivefive.deviantart.com/
