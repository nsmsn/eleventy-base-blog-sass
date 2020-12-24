# eleventy-base-blog-sass

This is a simple fork of the [eleventy-base-blog](https://github.com/11ty/eleventy-base-blog), a starter repository showing how to build a blog with the [Eleventy](https://github.com/11ty/eleventy) static site generator. This is almost the perfect starter for me, but I wanted to use scss files to compile my CSS. If you're looking for a simple Sass starter with some pre-built sample posts for an Eleventy project, I hope this helps you out.


## The big diffs

* This project uses a folder named 'src' for all the data and templates, and outputs to a 'public' folder (personal preference).
* styles are composed is src/sass/ and output to public/css/
* In .eleventy.js there is a configuration to watch the sass folder and 
* BrowserSync config uses "public/404.html" for the error


## Thank You

I wouldn't have been able to figure this out without [@5t3ph](https://github.com/5t3ph/)'s 'Eleventy from Scratch in 20 Minutes' [course on egghead.io](https://egghead.io/playlists/build-an-eleventy-11ty-site-from-scratch-bfd3)


## Getting Started

### 1. Clone this Repository

```
git clone https://github.com/nsmsn/eleventy-base-blog-sass.git my-blog-name
```


### 2. Navigate to the directory

```
cd my-blog-name
```

Specifically have a look at `.eleventy.js` to see if you want to configure any Eleventy options differently.

### 3. Install dependencies

```
npm install
```

### 4. Edit _data/metadata.json

### 5. Run the build process

```
npm start
```

Or in debug mode:
```
DEBUG=* npx eleventy
```


### Implementation Notes

* `about/index.md` shows how to add a content page.
* `posts/` has the blog posts but really they can live in any directory. They need only the `post` tag to be added to this collection.
* Add the `nav` tag to add a template to the top level site navigation. For example, this is in use on `index.njk` and `about/index.md`.
* Content can be any template format (blog posts needn’t be markdown, for example). Configure your supported templates in `.eleventy.js` -> `templateFormats`.
	* Because `css` and `png` are listed in `templateFormats` but are not supported template types, any files with these extensions will be copied without modification to the output (while keeping the same directory structure).
* The blog post feed template is in `feed/feed.njk`. This is also a good example of using a global data files in that it uses `_data/metadata.json`.
* This example uses three layouts:
  * `_includes/layouts/base.njk`: the top level HTML structure
  * `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
  * `_includes/layouts/post.njk`: the blog post template (wrapped into `base.njk`)
* `_includes/postlist.njk` is a Nunjucks include and is a reusable component used to display a list of all the posts. `index.njk` has an example of how to use it.
