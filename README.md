readability-extract
===================

The goal of this library is to provide a function that will extract article text from a webpage. It is based on the [Readability bookmarklet](https://code.google.com/p/arc90labs-readability/) and the [Kerrick/readability-js](https://github.com/Kerrick/readability-js) repository.

Overview of changes
-------------------
The Readability bookmarklet extracts article text from the current webpage, but it also modifies the current page to display article in an easy to read fashion. This fork's contribution is to pull that article extracting functionality out into a function that leaves the page unchanged.

Usage
-----
```
readability.extract(function(article){
  console.log(article.title);   // logs the title of the article
  console.log(article.content); // logs the body of the article
});
```
`extract` is an asynchronous function. If the article is paginated, `extract` will retreive the subsequent pages and concatenate them. `extract`'s only argument is a callback which will be executed when the entire article has been retrieved and processed.
