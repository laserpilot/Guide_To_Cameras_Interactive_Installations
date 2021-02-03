# Markdown chapter

This is a chapter written in markdown.

## Internal links

You can link to other files simply by making an internal [link](#second-chapter-id). The build process will automatically search for this ID in all files, and append the filename if needed for the particular format.

## Images

You can insert images simply by adding an image tag with the name of the image. This will look for an image located in `images/bruce.jpg`, but you can easily change this location if you want.

![Picture of Bruce Springsteen](bruce.jpg)

## Code examples

Code examples can be written using the markdown syntax, and they
will automatically be converted to HTMLBook programlistings. Here's an
example of using the `console.log` function.

```js
console.log("hello");
```

## Footnotes

You can also write footnotes using the Markdown syntax^[They are great], or the HTMLBook syntax<span data-type="footnote">They are great too</span>.

Then you use the following `footnotes` liquid tag to insert the footnote references on the page. This is often done at the bottom of the page.

{{ footnotes }}
