ko.js-debugger
==============

_version 0.9.0_

When building a project with [Knockout.js](http://knockoutjs.com/), you might, at times, want to see what your `View Model` looks like. This little tool lets you do that with a toggle-able, minimally-intrusive display.

[**Check out a live example** @ http://jmeas.com/projects/ko.js-debugger/](http://jmeas.com/projects/ko.js-debugger/)

_The source of the example is simply everything in the `/source` directory of this repository_

##Usage

There are three components to this tool: some `html`, a `.css` file, and a `.js` file. To use the tool, just include the three pieces in your project and make sure that they're properly referenced.

###The HTML

The HTML consists of a `div` that holds the toggle button and data window. It can go anywhere at all within the `body` tag of your document, as its set to `fixed` positioning in the `css`.

    <div class='kojs-debugger'>
      <button id='viewModel-toggle'>Show View Model</button>
      <div>
        <pre id='viewModel-display' style='display: none;' data-bind='text: ko.toJSON(viewData.myViewModel, null, 2)'>
        </pre>
      </div>
    </div>

_Note: be sure to update the first parameter of the `ko.toJSON` function to match the variable that is storing your view model_

###The CSS

The CSS file provides the divs with some styling. You can load it in the `header` of your page with a `link` element:

    <link rel="stylesheet" href="/css/kojs-debugger.css">

###The JavaScript

Place this script element for the Javascript toward the bottom of your page.

    <script src="/js/ko-debugger.js"></script>

##Dependencies

- Knockout.js

##Licensing

This is released under the [WTFPL](http://www.wtfpl.net/); that means you can do whatever you want with it.

_I'd like to thank Ryan Niemeyer for writing [the first article](http://www.knockmeout.net/2011/06/10-things-to-know-about-knockoutjs-on.html) that I read which mentioned using the `ko.toJSON` utility to debug your viewModel, which ultimately inspired me to make this thing._

##Version 1.0

Version 1 will include a filtering system. This will allow you to show only computed values, for instance, or otherwise other specific pieces of your view model. This feature should help with debugging the largest of view models.