title: Developer Guide

#[intro] Welcome Developer!
This is a brief overview of how this website works. Don't worry if you don't know much about computers or programming. This website is set up so that you can easily create good looking documents with no programming experience. How easy is it you may ask? Well... This instruction page is made using +[/dev.md](this one text file). Crazy right? You can apply all sorts of text formatting and include images, links, and more without any code. Unless you want to make significant changes or improvements, you shouldn't have to edit anything but the markup and jsion files. Read on to learn more about how to use this system.

##[urls] URLs
When a user visits a URL, they are shown the matching markup file. Any trailing `.html` or `/` on the URL is ignored. URLs with `.md` on the end show the raw, unrendered file. The only special case is `/` (the root page) which shows `index.md`. See the table below for examples:

[[
    Path         , File
    `/`          , `/index.md`&&*&&
    `/foo`       , `/foo.md`
    `/foo/`      , `/foo.md`
    `/foo.md`    , `/foo.md`&&**&&
    `/foo.html`  , `/foo.md`
    `/foo/bar`   , `/foo/bar.md`
    `/foo/bar.md`, `/foo/bar.md`&&**&&
]]
&&\*&& Special case\n&&\*\*&& Shows raw text


##[hosting] Hosting

This site is hosted on Google Firebase and the code can be found on the GitHub repository. Whenever you merge a branch to main, a GitHub Action will rebuild and deploy the page. Since this page runs on the free tier of Firebase, try to limit how often you make it rebuild. You can test a local copy of the site on your own device (even on a [https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb/](Chomebook)). Use some external tool to store large amounts of photos. Keep small images and the logos on here, but put other ones somewhere else.

##[headings] Text Headings
Text headings like the one above are actually links so that you can link to individual sections of a page. You can manually set an id in the markup or let the parser generate one.

##[nav] The Nav List
Each element with an id is added to the nav list. The top-most visible element will be marked on the list unless the page is small enough that everything fits.

##[links] External Links
Links to an outside domain get a symbol next to them like this: https://g.co.

##[header_and_footer] Page Header & Footer
The header and footer of the page are generated from `/cfg/header.md` and `/cfg/footer.md` respectivly. Note that the header shouldn't have links in it since the whole header becomes a link to the home page. On the footer, feel free to update the copyright information with whoever is currently maintaining the website. **Please do NOT change any copyrights in JavaScript libraries so you comply with the licenses.** (DomLib, DomLib Extra, and SHML are MIT licensed, JSION is licensed under the Unlicense)

##[properties] Properties (`/cfg/properties.jsion`)
[[
    Property   , Usage
    title      , This property controls the window/tab title. It can be set in `/cfg/properties.jsion` and/or in the individual markup files. A title set in a markup file will override the entry in `/cfg/properties.jsion`. If unset\, the hostname is used.
    themeColor , This proeprty can be any CSS color <</(keyword, hex, rgb, hsl, etc...)./>> It is the accent color of the page. **Note that this property cannot be set in the markup files and must be set in `/cfg/properties.jsion`.**
]]

Other properties may be defined in `/cfg/properties.jsion` and referenced in markup files if you need to embed advanced HTML snippets. **Note that to include HTML, you must define the properties in `/cfg/properties.jsion` NOT in the markup file, or the text will get sanatized.** Look at the `spheroVideo` entry and its usage in [/](`index.md`) for an example.

Try to use cammelCase for property names.

##[symbols] Symbols (`/cfg/symbols.jsion`)
Symbols are similar to propeties except that they can only be defiend in the global config file and are not overridable within each page (Think of them as constant properties). Typically use symbols for things like icons and :tableflip:.


Use kebab-case for symbol names.

##[shml] SHML
SHML is a markup language with a syntax similar to Markdown. If you've used Discord or Reddit before most of the same formatting tricks (ex. `*text*` -> *text*) should work here. For more details on SHML, check out the [https://github.com/SteveBeeblebrox/SHML](documentation).

##[jsion] JSION
Config files for this site are `.jsion` files (**Not `.json`. Note the "i".**). JSION is a forgiving version of JSON with an expanded syntax. Notable features include comments in parentheses and single quoted strings among many others. If in doubt, just write the config as a plain JSON instead, and it will work fine. Check out the JSION [https://github.com/SteveBeeblebrox/JSION](documentation) for a complete feature list.


##[todo] Possible Improvements
If you'd like to take a swing at them, here are some bugs with the site or other things that could be improved:

+ ~~Wrap header in link to main page~~ :check:
+ Hide sidebar if there is nothing to show
+ Improve scoll marking when the page is small
+ Mobile screen support
+ Contribute to SHML on GitHub
+ Improve the footer (Maybe add a GitHub link?)
