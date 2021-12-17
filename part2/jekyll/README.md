# Part 2: Jekyll

For this part 2 option, you will turn your site into a Jekyll project. Jekyll
is a static website generator. It is the most popular option, since it is
the only one supported by GitHub pages, a free static website host for GitHub
projects and users.
 * https://jekyllrb.com/
 * https://docs.github.com/en/pages

## Getting set up
Jekyll has a number of prerequisites which can be tricky to install. You should
follow the guides in the official documentation:
https://jekyllrb.com/docs/installation/

Once you have installed Jekyll, open a terminal and run
```
simon@rosalyn:~$ jekyll --version
jekyll 3.8.6
```
to verify that you have installed Jekyll and everything is working.

## Make your website
Typically you would run `jekyll new` to create a new Jekyll site. Since we've
already made a website, we need to bring in that work as a theme. Jekyll makes
this a bit tricky, so I've done a lot of that work for you.

Here is what _you_ need to do:
 1. Copy `index.html` into the `_layouts` folder and name it `default.html`.
    This folder holds HTML templates for different page types on your website.
 2. Copy `style.css` into the `assets` folder. This folder holds static content
    that you don't expect to edit much, like stylesheets, pictures, or music.
 3. In `default.html` copy everything _between but not including_
    `<div id="content">` and the corresponding `</div>` and paste it in the file
    called `index.html` in the `jekyll` directory, underneath the three dashed
    lines.
 4. Replace the text you just copied with `{{ content }}`. It should now look
    something like this:
    ```html
    <div id="content">
        {{ content }}
    </div>
    ```
 5. Replace the `<link>` that loads style.css with
    ```html
    <link rel="stylesheet" href="{{ "/assets/style.css" | relative_url }}" />
    ```

Now, depending on how you installed Jekyll, you should be able to run either
`jekyll serve` or `bundle exec jekyll serve` then visit http://127.0.0.1:4000 to
see your site. It should look exactly the same as it did before.

## Explore a bit more
At this point, you're done. However I strongly encourage you to keep exploring
and maybe add some cool new features to your website.

Take a look through the documentation, especially the quickstart section, to get
an idea of what's possible: https://jekyllrb.com/docs/

The _main point_ of Jekyll, which we have totally ignored in this tutorial, is
making blogs. Consider creating a brand new Jekyll project unrelated to this one
with `jekyll new` to get a sense of what the code for that sort of site might
look like.

## Submitting your project
Zip up _only_ the folder containing your Jekyll project and submit it on Moodle.