# Shape CMS

Shape is a content management system, written in Clojure. **Currently in progress, docs will appear as things get created.** 

## Installation

All you need to run Shape is the presence of Clojure in your system (meaning the `clj` CLI tool and Java), and then cloning
the repo to wherever you want, and running:

```bash
clj -X shape.core/run
```

Then fire up your browser and visit `localhost:3999/admin`, this should automatically create the SQLite database, and then 
direct you to the setup page (which doesn't yet do anything). 

## The idea

Clojure is lacking a nice, composable CMS. Something that makes it easy for developers to build websites using Clojure, and non-developers to use those websites. 

And so I'm building a CMS like that. 

The idea is quite simple; at the heart of it all are **Content Shapes**, which can be your information pages, blog posts, shop products, whatever it is - you can create infinite amount of these by putting together different data types and naming them (eg text for title, image for thumbnail, number for currency, etc). This lays out the data architecture of the site and is what the end-users will be creating. 

Then there are **Partials**, these are pure-Clojure functions that spit out HTML (via Hiccup, for example). This can be anything you want, and it enables the use of a DSL to fetch data from the previously mentioned **Content Shapes**. Could be a Product View, could be a Blog Post View, whatever you want, these are the building blocks of the website. 

And at last there are **Pages**. Pages are composed out of **Partials**, and they are attached to a URL. The URL could be static, like `/about`, or it could be dynamic like `/blog/{post}`. **Partials** will also have a way to tell what the `{post}` is in case of a dynamic URL, so that you could fetch the right data for your Partial. 

And that's it, pretty straight-forward and this alone should enable the creation of quite many different websites, be it a blog, an online-shop or portfolio. 

## Roadmap to 0.1

- [ ] Site setup / authentication (in progress)
- [ ] Content Shape creation in admin panel
- [ ] Content creation in admin panel
- [ ] Partials implementation
- [ ] Pages creation in admin panel
- [ ] Default theme
