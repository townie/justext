## New project page ##

Since Google Code is about to close down, jusText is now hosted at corpus.tools:
http://corpus.tools/wiki/Justext

## About jusText ##

jusText is a tool for removing boilerplate content, such as navigation links, headers, and footers from HTML pages. It is designed to preserve mainly text containing full sentences and it is therefore well suited for creating linguistic resources such as Web corpora.

[Changelog](http://code.google.com/p/justext/source/browse/trunk/CHANGES)

## Installation ##
  1. Make sure you have [Python](http://www.python.org/) and [lxml](http://lxml.de/) library version 2.2.4 or later installed.
  1. Download the sources:
```
wget http://justext.googlecode.com/files/justext-1.2.tar.gz
```
  1. Extract the downloaded file:
```
tar xzvf justext-1.2.tar.gz
```
  1. Install the package (you may need sudo or a root shell for the latter command):
```
cd justext-1.2/
python setup.py install
```

## Quick start ##
```
wget -O page.html http://planet.python.org/
justext -s English page.html > cleaned-page.txt
```
For usage information see:
```
justext --help
```

## Python API ##
```
import urllib2
import justext

page = urllib2.urlopen('http://planet.python.org/').read()
paragraphs = justext.justext(page, justext.get_stoplist('English'))
for paragraph in paragraphs:
    if paragraph['class'] == 'good':
        print paragraph['text']
```

## Online demo ##
http://nlp.fi.muni.cz/projects/justext/

## Related links ##
Mišo Belica created a [jusText fork on GitHub](https://github.com/miso-belica/jusText) with some tweaks.

jusText is also [available on PyPi](https://pypi.python.org/pypi/jusText).

## Acknowledgements ##
This software has been developed at the [Natural Language Processing Centre](http://nlp.fi.muni.cz/en/nlpc) of [Masaryk University in Brno](http://nlp.fi.muni.cz/en) with a financial support from [PRESEMT](http://presemt.eu/) and [Lexical Computing Ltd](http://lexicalcomputing.com/). It also relates to author's [PhD research](http://is.muni.cz/th/45523/fi_d/phdthesis.pdf).