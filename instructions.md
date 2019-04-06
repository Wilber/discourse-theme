## Add a Category to AskCI

It's great that you want to add a category to your site! You can follow the instructions here
to develop your style and test a logo, and then you will need to contact a site admin to
do the heavy lifting. If you don't know how to find someone or need more help, you can
reply to this post, get help on the #askci channel on the [Campus Champions slack](https://campuschampions.slack.com/messages/C1EUA57RV/),
or tweet to [Askcybrainfra](https://www.twitter.com/Askcybrainfra).

# 1. Setup

You likely don't have admin on the actual discourse site, so if you want to do any testing of a category
style, you need to run a local instance. @vsoch has put together a [set of instructions](https://github.com/researchapps/discourse-theme)
to run your own mini discourse via Docker, and then test a theme. Specifically, you will want to:

 1. Develop a theme on https://meta.discourse.org/ using the [theme creator](https://meta.discourse.org/t/theme-creator-create-and-show-themes-without-installing-discourse/84942).
 2. Export it, and run the Docker Compose application to create a dummy category and import and test the theme

Instructions for how to do this, and how the actual admin on the AskCi site does it, are further detailed below.
You can likely do many of the steps without testing, but this is not advisable.

# 2. Name your Category

If you look on the [categories page](https://ask.cyberinfrastructure.org/categories) this is where your site
will have a link. Specifically, you want to choose a category name that completely describes your site.
For example, instead of "SRCC" or "Stanford RC" the group at Stanford uses "Stanford Research Computing"
and this renders to the slug "stanford-research-computing." Remember this slug, as it will be important
to know for your category style.

# 3. Choose a Logo

The admin will need to upload the logo to the site in order to get a permalink for it. Generally, you want
to choose a long and flat logo that includes the name of the group (in some respect) along with an image.
For example, the Stanford logo is:

![https://ask.cyberinfrastructure.org/uploads/default/original/1X/70525e0736735302dec325d09b34a3a0b2933c24.jpeg](https://ask.cyberinfrastructure.org/uploads/default/original/1X/70525e0736735302dec325d09b34a3a0b2933c24.jpeg)

And this was uploaded as a static file by an admin. You can share your logo with an admin in the Campus Champions
slack, or over email.

# 4. Write the Style

The style is the most important part, and it's why you are encouraged to test before making a site category page live.
For example, the Stanford logo is red on white, so it's important that the background color is white. How
does this work? Discourse automatically creates a class for each category, so the "stanford-research-computing" slug
has the following selectors we want to edit:

 - .category-stanford-research-computing #site-text-logo: where your logo image will go
 - .category-stanford-research-computing .d-header: the header section, where you should choose the background and text colors

For example, here is the stanford-research-computing style:

```css
.category-stanford-research-computing .d-header {
   color: black !important;
   background-color: white !important;
   background-image: none !important;
   background: white !important;
}
```
```css
.category-stanford-research-computing #site-text-logo {
 content: url("https://ask.cyberinfrastructure.org/uploads/default/original/1X/70525e0736735302dec325d09b34a3a0b2933c24.jpeg
https://ask.cyberinfrastructure.org/uploads/default/original/1X/70525e0736735302dec325d09b34a3a0b2933c24.jpeg
") !important;
 background: url("https://ask.cyberinfrastructure.org/uploads/default/original/1X/70525e0736735302dec325d09b34a3a0b2933c24.jpeg
https://ask.cyberinfrastructure.org/uploads/default/original/1X/70525e0736735302dec325d09b34a3a0b2933c24.jpeg
") no-repeat !important;
 display: inline-block;
 width: 80px;
 font-size: 0;
 margin-top: 5px;
 margin-bottom: 0px;
}
```

These styles are added to the global style, and will be relevant when your category page is being rendered. When you are testing
these out, you can use and follow instructions provided by the [theme creator](https://meta.discourse.org/t/theme-creator-create-and-show-themes-without-installing-discourse/84942).

# 5. Share your Work!

When you finish, send both the image, the name for your category, and the style snippets you've developed to an admin,
and he or she can add them to the site. Likely, you will be asked to preview the category page and make any
changes needed.
