# [Forever Jekyll - A simple, elegant & full featured Jekyll theme](https://forever-jekyll.github.io)
`Forever Jekyll` is a theme-template-boilerplate for `Jekyll`. Primary goal of `Forever Jekyll` is to make the task of building a personal website with `Jekyll` so easy that even a person with non-computing background should be able to do it with ease.  


## How to run
This page should be hosted on GithubPages by default at `https://brtnlaw.github.io/food_blog`. You can make sure of this by checking the repo at `Settings => Pages => Source` and make sure that `Branch: main` is set to `/ (root)`.
To run this locally, try ```bundle exec jekyll serve --livereload```

## Troubleshooting
This is a fork of `Forever Jekyll`, refer to `https://github.com/forever-jekyll/forever-jekyll`, the README.md in particular, for updating functionality.
## Enabling comments
Comments are not enabled by default in `Forever Jekyll` but this functionality can easily be added.  
`Forever Jekyll` uses `Cactus Comments`. It is a privacy respecting federated comment system built on Matrix protocol.  
`Cactus Comments` is completely free and open source.  
First you need to register your site with `Cactus Comments`. To do so, click on the following link,  

[chat with @cactusbot:cactus.chat](https://matrix.to/#/@cactusbot:cactus.chat)  

Clicking on that link will take you to the `Matrix` page and you'll be prompted to choose an app to continue.  
Select `Element` and click on `continue`.  
On the next page click on `Continue in your browser`.  
On the next page click on `Send a Direct Message`. It'll prompt you to either `Sign In` or to `Create Account`.  
After signing in to your account send following text as a direct message,  
```
register <YOUR-SITE-NAME>
```  
For example,  
```
register elaine-thompson.github.io
```  
50% of work done.  

Right click on the following link and select `Save link as...` option and save the file with the name `default.html`.  

[default.html](https://github.com/forever-jekyll/propaganda/raw/a6a98c79f871fb51fc18ba2fc6f3364ce33c4d62/default-with-comments-.html)  

Right click on the following link and again select `Save link as...` option and save the file with the name `post.html`.  

[post.html](https://github.com/forever-jekyll/propaganda/raw/main/post-with-comments.html)  

Save the following link with the name `_cactus.scss` just like we did earlier.  

[_cactus.scss](https://github.com/forever-jekyll/propaganda/raw/main/_cactus.scss)  

Now Navigate back to your site repository and open the folder `_layouts`.  
Upload the `default.html` file via `Add file` -> `Upload files` option.  
Open this file `default.html` in your site repository and go to the line number **120**,  
```
siteName: "elaine-thompson.github.io",
```  
Replace `elaine-thompson.github.io` with the site name you just registered on `Cactus Comments`.  
Don't forget to save the changes by clicking on `Commit Changes` button.  

Next upload the `post.html` file to the folder `_layouts` via `Add file` -> `Upload files` option.  
In your site repository go to folder `_sass` and upload `_cactus.scss` file via `Add file` -> `Upload files` option.  
And finally open the file `style.scss` in your site repository. Add the following line at the very end of the file,  
```
@import "cactus";
```  
Save the changes by clicking on `Commit Changes` button.  

That's it. Kudos! You have successfully enabled commenting system on your site.  

## Enabling web analytics
Like comments web analytics is not enabled by default in `Forever Jekyll` but this can easily be added.  
`Forever Jekyll` uses `GoatCounter`. It is an open source and privacy friendly web analytics platform.  
`GoatCounter` is free for non-commercial use. To sign up for `GoatCounter` click open the following link,  

[Sign up for GoatCounter](https://www.goatcounter.com/signup)  

Next navigate back to your site repository and open the file `default.html` in the folder `_layouts`.  
Right at the end of the file you'll see following closing tags,  
```
</body>
</html>
```  
Add the following snippet right before those closing tags,  
```
<script data-goatcounter="https://MYCODE.goatcounter.com/count"
        async src="//gc.zgo.at/count.js"></script>
```  
Of-course you'll have to replace `MYCODE` in the snippet above with your actual `GoatCounter` code acquired during the sign up.  
Save the changes by clicking on `Commit Changes` button.  

Well-done! You have successfully enabled an ethical and privacy friendly web analytics system for your site.  

## Enabling Google analytics  
It's quite easy to implement `Google analytics` in `Forever Jekyll`. Here is how you can do it,  

Create a file with the name `google-analytics.html` in the `_includes` directory. Add the following code into it and save the file,  

```html
<script async src="https://www.googletagmanager.com/gtag/js?id={{ site.google_analytics }}"></script>
<script>
  window['ga-disable-{{ site.google_analytics }}'] = window.doNotTrack === "1" || navigator.doNotTrack === "1" || navigator.doNotTrack === "yes" || navigator.msDoNotTrack === "1";
  window.dataLayer = window.dataLayer || [];
  function gtag(){window.dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', '{{ site.google_analytics }}');
</script>
```

Next open-up the `_config.yml` file and add,  

`google_analytics: UA-XXXXXXXX-X`

Of-course, replace `UA-XXXXXXXX-X` with your actual `Google tracking ID` above.  

And finally, add the following code snippet to the `default.html` file in the `_layouts` directory right below the `{% include meta.html %}` line,  

```html
{%- if jekyll.environment == 'production' and site.google_analytics -%}
  {%- include google-analytics.html -%}
{%- endif -%}
```

Save the file and voila! you have successfully enabled `Google analytics` for your website!

## Support

If you like `Forever Jekyll`, please consider supporting it, even the smallest contribution goes a long way:  

[![Support via PayPal](https://cdn.jsdelivr.net/gh/twolfson/paypal-github-button@1.0.0/dist/button.svg)](https://paypal.me/hakerdefo)  
[!["Buy Me A Coffee"](https://user-images.githubusercontent.com/1376749/120938564-50c59780-c6e1-11eb-814f-22a0399623c5.png)](https://www.buymeacoffee.com/hakerdefo)  
[![Support via Liberapay](https://liberapay.com/assets/widgets/donate.svg)](https://liberapay.com/hakerdefo/donate)  

## Writing posts
The `_posts` folder is where your blog posts live.  
Posts in `Jekyll` are text files and `Jekyll` provides everything you need to turn it into a blog.  
`Jekyll` posts are typically written in `Markdown` but you can also write in `HTML` if you wish.  
All post files must begin with front matter. What's a front matter?  
A front matter is typically used to set a layout or other meta data.  
But at this point in time all that technical stuff is strictly not necessary for you to remember.  
All you need to remember is, you'll have to begin every new post with following snippet,  
```  
---
layout: post
title: Title of your post
categories: [category 1, category 2]
---
```  
`title:` in the above snippet is obviously the title of your post.  
`categories:` A blog category can either be a word or a group of words separated by a comma.  
Choose them wisely and use them to give a gist of the post or post's content.  
`Categories` can play a crucial role in organizing your site’s posts properly. It is also considered a good SEO practice.  
`Categories` makes it easy for your potential web visitors to navigate around your site and offers a good user experience.  

Now coming to actual writing. `Markdown` doesn't require any special application. You can write in `Markdown` everywhere.  
Here is a very good resource to get you started with `Markdown`=> [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).  
But for someone who is new to `Markdown` I would recommend any of these three editors,  
 - [Abricotine](https://abricotine.brrd.fr/)  
 - [Mark Text](https://marktext.app/)  
 - [Zettlr](https://www.zettlr.com/)  

After you have completed your post, you'll have to save the post file in `_posts` folder in your repository.  
`Jekyll` is very particular about the post filename format. Every post filename must follow this format,  
```
YEAR-MONTH-DAY-title.md
```  
An example,  
```
2011-12-31-new-years-eve-is-awesome.md
```  
One more example,  
```
2012-09-12-how-to-write-a-blog.md
```  
A bit odd but not that difficult, right?!?  

It is always a great idea to keep the main (index) page of your blog uncluttered and concise. So rather than displaying the complete post on the main page, we can display summery or excerpt of the post there. `Forever Jekyll` makes it really easy to truncate post and let you select the amount of content you wish to display on the main page. All you have to do is, add `<!--more-->` on a newline from where you want to truncate the post. An example. Say you have following post you want to publish,  
```
But I must explain to you how all this mistaken idea of re-probating pleasure and extolling pain arose. To do so, I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally encounter consequences that are extremely painful. Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but occasionally circumstances occur in which toil and pain can procure him some great pleasure. To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it? But who has any right to find fault with a man who chooses to enjoy a pleasure that has no annoying consequences, or one who avoids a pain that produces no resultant pleasure?  
On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain and trouble that are bound to ensue; and equal blame belongs to those who fail in their duty through weakness of will, which is the same as saying through shrinking from toil and pain. These cases are perfectly simple and easy to distinguish. In a free hour, when our power of choice is untrammeled and when nothing prevents our being able to do what we like best, every pleasure is to be welcomed and every pain avoided. But in certain circumstances and owing to the claims of duty or the obligations of business it will frequently occur that pleasures have to be repudiated and annoyances accepted. The wise man therefore always holds in these matters to this principle of selection: he rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains.  
```
You want to only display the first paragraph and truncate the post after that on the main page. It can easily be done by just adding `<!--more-->` like this,  
```
But I must explain to you how all this mistaken idea of re-probating pleasure and extolling pain arose. To do so, I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally encounter consequences that are extremely painful. Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but occasionally circumstances occur in which toil and pain can procure him some great pleasure. To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it? But who has any right to find fault with a man who chooses to enjoy a pleasure that has no annoying consequences, or one who avoids a pain that produces no resultant pleasure?  
<!--more-->
On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain and trouble that are bound to ensue; and equal blame belongs to those who fail in their duty through weakness of will, which is the same as saying through shrinking from toil and pain. These cases are perfectly simple and easy to distinguish. In a free hour, when our power of choice is untrammeled and when nothing prevents our being able to do what we like best, every pleasure is to be welcomed and every pain avoided. But in certain circumstances and owing to the claims of duty or the obligations of business it will frequently occur that pleasures have to be repudiated and annoyances accepted. The wise man therefore always holds in these matters to this principle of selection: he rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains.  
```

I highly recommend adding excerpts to your posts using `<!--more-->` as shown above to keep your main blog/site page uncluttered and easy to navigate. You can find more examples of this on `Forever Jekyll` demo site as every post there has been truncated using the above technique.  

I've included a sample post in `_posts` directory to get you started. Feel free to delete it when you are ready with your first post.  

## Conclusion
I'm pretty sure that this should be good enough for almost everyone to get started with `Forever Jekyll` in particular and `Blogging` in general.  
But I'm also aware that I must have missed a few things in this README and there will be a few unexplained things left behind.  
In such a case feel free to [start a discussion](https://github.com/forever-jekyll/forever-jekyll/discussions/). Everything related to `ForeverJekyll` is welcome.  

> Your personal website or blog might not change the world but it will certainly change you.  
~ Me  

> It is necessary to write, if the days are not to slip emptily by. How else, indeed, to clap the net over the butterfly of the moment? for the moment passes, it is forgotten; the mood is gone; life itself is gone.  
~ Vita Sackville-West  
