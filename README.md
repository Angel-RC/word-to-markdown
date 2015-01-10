# Word to Markdown converter

A Ruby gem to liberate content from [the jail that is Word documents](http://ben.balter.com/2012/10/19/we-ve-been-trained-to-make-paper/#jailbreaking-content)

[![Build Status](https://travis-ci.org/benbalter/word-to-markdown.svg?branch=master)](https://travis-ci.org/benbalter/word-to-markdown) [![Gem Version](https://badge.fury.io/rb/word-to-markdown.png)](http://badge.fury.io/rb/word-to-markdown) [![Inline docs](http://inch-ci.org/github/benbalter/word-to-markdown.png)](http://inch-ci.org/github/benbalter/word-to-markdown) [![Build status](https://ci.appveyor.com/api/projects/status/1hmk6643hqsx3bt3?svg=true)](https://ci.appveyor.com/project/benbalter/word-to-markdown)


## The problem

> Our default content publishing workflow is terribly broken. [We've all been trained to make paper](http://ben.balter.com/2012/10/19/we-ve-been-trained-to-make-paper/), yet today, content authored once is more commonly consumed in multiple formats, and rarely, if ever, does it embody physical form. Put another way, our go-to content authoring workflow remains relatively unchanged since it was conceived in the early 80s.
>
> I'm asked regularly by government employees — knowledge workers who fire up a desktop word processor as the first step to any project — for an automated pipeline to convert Microsoft Word documents to [Markdown](http://guides.github.com/overviews/mastering-markdown/), the *lingua franca* of the internet, but as my recent foray into building [just such a converter](http://word-to-markdown.herokuapp.com/) proves, it's not that simple.
>
> Markdown isn't just an alternative format. Markdown forces you to write for the web.

**[Read more](http://ben.balter.com/2014/03/31/word-versus-markdown-more-than-mere-semantics/)**

**[Demo](http://word-to-markdown.herokuapp.com/)**

## Install

```bash
gem install word-to-markdown
```

## Usage

```ruby
file = WordToMarkdown.new("/path/to/document.docx")
=> <WordToMarkdown path="/path/to/document.docx">

file.to_s
=> "# Test\n\n This is a test"

file.document.tree
=> <Nokogiri Document>
```

### Command line usage

Once you've installed the gem, it's just:

```
$ w2m path/to/document.docx
```

*Outputs the resulting markdown to stdout*

## Supports

* Paragraphs
* Numbered lists
* Unnumbered lists
* Nested lists
* Italic
* Bold
* Explicit headings (e.g., selected as "Heading 1" or "Heading 2")
* Implicit headings (e.g., text with a larger font size relative to paragraph text)
* Images
* Tables

## Requirements and configuration

Word-to-markdown requires `soffice` a command line interface to LibreOffice.

## Installing on OS X

Follow the instructions for [Installing LibreOffice on OS X](https://www.libreoffice.org/get-help/install-howto/os-x/)

## Installing on ubuntu

```
sudo apt-get update
sudo apt-get install libreoffice
```

## Testing

```
script/cibuild
```

## Server

[Word-to-markdown-demo](https://github.com/benbalter/word-to-markdown-demo) contains a lightweight server for converting Word Documents as a service.

A live version runs at [word-to-markdown.herokuapp.com](http://word-to-markdown.herokuapp.com).
