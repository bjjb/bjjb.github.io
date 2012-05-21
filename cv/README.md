CV Generator
============

The [Rakefile][rakefile] here generates [my CV][cv] in various formats from the
cv.yml file.  It uses a few gems for this:

* [activesupport][activesupport], for generating the XML/JSON
* [json][json], for generating JSON on Ruby 1.8
* [wicked_pdf][wicked_pdf], for the PDF version (note that
  [webkit2pdf][webkit2pdf] must be installed.)
* [haml][haml], for structuring the HTML
* [sass][sass], for generating the style
* [mustache][mustache], for generating the text version
* [maruku][maruku], for converting the text to HTML

I just run `rake` after updating the YAML file, and everything gets updated.

![preview.png][:preview]

TODO
----

1. Improve the PDF generation. Particularly, as webkit2pdf isn't readily
   available on OSX/Windows, make a web-app to do create the PDF, and use that.
2. Be more generic about the name of the file. Rather than insisting on cv._x_,
   allow the base file name to be anything.

[rakefile]: https://github.com/jjbuckley/jjbuckley.github.com/blob/master/cv/Rakefile
[cv]: http://jjbuckley.github.com/cv/cv.html
[activesupport]: http://as.rubyonrails.org/
[json]: http://flori.github.com/json/
[wicked_pdf]: https://github.com/mileszs/wicked_pdf
[webkit2pdf]: http://webkit2pdf.sourceforge.net/
[haml]: http://haml.info/
[sass]: http://sass-lang.com/
[mustache]: https://github.com/defunkt/mustache
[maruku]: https://github.com/nex3/maruku
[preview]: preview.png "The finished product"
[markdown]: http://daringfireball.net/projects/markdown
