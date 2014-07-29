# Markdown Superscript

[![Build Status](https://travis-ci.org/jambonrose/markdown_superscript_extension.svg?branch=master)](https://travis-ci.org/jambonrose/markdown_superscript_extension)
[![Coverage Status](https://img.shields.io/coveralls/jambonrose/markdown_superscript_extension.svg)](https://coveralls.io/r/jambonrose/markdown_superscript_extension)

An extension to [Waylan Limberg](https://github.com/waylan)'s [Python Markdown](https://github.com/waylan/Python-Markdown) project ([documentation here](https://pythonhosted.org/Markdown/index.html)) that provides support for superscript text in Markdown. The extension treats `^` characters as tags, converting pairs into HTML `sup` tags.

Given the text:

    2^10^ is 1024.

… using Markdown with this extension will output:

    <p>2<sup>10</sup> is 1024.</p>

This project is provided under the [Simplified (2 Clause) BSD license](http://choosealicense.com/licenses/bsd-2-clause/), provided in full in the LICENSE file.

## Installation

Dependencies:

- Python 2.6, 2.7, 3.2+
- Markdown 2.0+

To install the latest stable release (recommended):

```bash
$ pip install MarkdownSuperscript
```

To install the development version:

```bash
$ pip install git+git://github.com/jambonrose/markdown_superscript_extension.git
```

## Basic Usage

### Python

```python
>>> from markdown import markdown
>>> text = "2^10^ is 1024."
>>> markdown(text, ['superscript'])
'<p>2<sup>10</sup> is 1024.</p>'
```

### Command Line

```bash
$ echo '2^10^ is 1024.' > text.md
$ python -m markdown -o html5 -x 'superscript' -f text.html text.md
```

## Development

Development requires the installation of [Python](https://www.python.org/). [Pip](https://pip.pypa.io/en/latest/installing.html) and a virtual environment, such as [virtualenvwrapper](https://pypi.python.org/pypi/virtualenvwrapper) (used in the example below), are recommended. Once these are installed, the following steps may be taken:

```bash
$ git clone https://github.com/jambonrose/markdown_superscript_extension.git
$ cd markdown_superscript_extension/
$ mkvirtualenv markdown_superscript  # recommended, but optional
$ cat requirements/* > requirements.txt
$ pip install -r requirements.txt
```

The `Makefile` provides the ability to run tests by invoking `$ make test`, which will invoke the nose package with the command `$ nosetests --with-coverage --cover-package=mdx_superscript` (incidentally, this is also the command used on [TravisCI](https://travis-ci.org/jambonrose/markdown_superscript_extension) and [Coveralls.io](https://coveralls.io/r/jambonrose/markdown_superscript_extension).
