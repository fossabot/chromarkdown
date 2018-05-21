# Chromarkdown

![Go Version](https://img.shields.io/badge/Go%20Version-latest-brightgreen.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/Depado/chromarkdown)](https://goreportcard.com/report/github.com/Depado/chromarkdown)
[![Build Status](https://drone.depado.eu/api/badges/Depado/chromarkdown/status.svg)](https://drone.depado.eu/Depado/chromarkdown)
[![codecov](https://codecov.io/gh/Depado/chromarkdown/branch/master/graph/badge.svg)](https://codecov.io/gh/Depado/chromarkdown)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/Depado/chromarkdown/blob/master/LICENSE)
[![Godoc](https://godoc.org/github.com/Depado/chromarkdown?status.svg)](https://godoc.org/github.com/Depado/chromarkdown)
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/Depado)

Build single-file static HTML page with Chroma (syntax highlighting) and Markdown

![screenshot](https://github.com/Depado/chromarkdown/blob/master/img/screenshot.png)

## Introduction

Chromarkdown is a tool to generate single-file static HTML pages from a
Markdown file input. This tool has no external dependecies and performs the
following operations:

- Syntax highlighting thanks to [chroma](https://github.com/alecthomas/chroma)
- Markdown rendering using [blackfriday](https://github.com/russross/blackfriday)
- Embedded [Roboto](https://fonts.google.com/specimen/Roboto) and 
[Roboto-mono](https://fonts.google.com/specimen/Roboto+Mono) fonts
- Dynamic CSS for Syntax Highlighter according to the chosen theme
- Single-file (one HTML file) output with embedded styles and fonts (no network 
call)
- Responsive page with simple design according to 
[bettermotherfuckingwebsite](http://bettermotherfuckingwebsite.com/)

## Build

Chromarkdown is using [dep](https://github.com/golang/dep) for its dependency
management

```sh
$ go get github.com/Depado/chromarkdown
$ cd $GOPATH/Depado/chromarkdown
$ dep ensure
$ packr build
```

For a standalone installation, chromarkdown is using [packr](https://github.com/gobuffalo/packr)
to embed the template in the go binary.

```sh
$ go get -u github.com/gobuffalo/packr/...
$ packr build
$ # or, to embed and install: 
$ packr install
```

## Install

## Usage

Once installed you can run the `chromarkdown` command:

```
$ chromarkdown --help

Chromarkdown uses a combination of blackfriday and chroma to render an input markdown file.
It generates standalone HTML files that includes fonts, a grid system and extra CSS.

Usage:
  chromarkdown [input file] [flags]

Flags:
  -h, --help            help for chromarkdown
      --no-toc          Disable the table of content
  -o, --output string   specify the path of the output HTML (default "out.html")
      --theme string    Specify the theme for syntax highlighting (default "monokai")
  -t, --title string    Specify the title of the HTML page (default "Ouput")
```
