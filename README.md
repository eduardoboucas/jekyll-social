# Jekyll Social
Select what social media platforms to share your Jekyll blog posts on, right from the front matter.

## The idea
If you're the author of a blog, you probably want to share your posts with as many people as possible and you're probably using social media platforms to do that. Instead of doing that manually, you can take advantage of services like [IFTTT](https://ifttt.com/) to automate the process, especially since Jekyll ships with a RSS feed file you can use to communicate with third-parties.

But sometimes you want to share each post on a different set of platforms, and that's where **Jekyll Social** comes handy. It generates a feed for each social platform based on the information you include on the front matter of a post.

### Example
Let's say that you want to share *post 1* on Facebook, *post 2* on Twitter and LinkedIn. You include the following in the posts' front matter:

- *post 1*: `share: facebook`
- *post 2*: `share: twitter linkedin`

If you don't want to share a post at all, simply don't include the `share` property.

## How it works
Instead of serving the same feed file to all different IFTTT channels, **Jekyll Social** creates an individual feed for each social platform which you can then serve its respective IFTTT channel. You can select which posts go into each feed by specifying the `share` property in the post front matter.

### Using your normal feed with IFTTT
![Before Jekyll Social](https://eduardoboucas.com/assets/posts/2015-04-28-sharing-jekyll-posts-on-social-media-using-front-matter-and-ifttt/jekyll-social-before.png)

### Using Jekyll Social with IFTTT
![After Jekyll Social](https://eduardoboucas.com/assets/posts/2015-04-28-sharing-jekyll-posts-on-social-media-using-front-matter-and-ifttt/jekyll-social-after.png)

## How to use
Check [this blog post](https://eduardoboucas.com/blog/2015/04/28/sharing-jekyll-posts-on-social-media-using-front-matter-and-ifttt.html) for detailed information about the implementation and how to set everything up.

## Custom formats
By default, all the social media platforms share the same layout in **Jekyll Social**, but it's possible to create a custom behavior for individual platforms. 

### Twitter and hashtags
For example, we include a feed format specific for Twitter which has the ability to grab post tags and add them as hashtags in a tweet. The [_config.yml](https://github.com/eduardoboucas/jekyll-social/blob/master/_config.yml) included in this repo contains 3 variables the plugin will use to form your tweets:

- `twitter_format`: The format for the tweets. The placeholders `@title`, `@url` and `@tags` tags will be automatically replaced with the post's title, url and tags (as hashtags), respectively. You can add custom text like *Blog post:*.
- `twitter_url_length`: The amount of characters used by Twitter to encode an URL. You shouldn't need to change the default value, unless Twitter changes their platform.
- `twitter_max_length`: The maximum length of a tweet. It is currently 140 characters and I doubt it will ever change, but you never know!

If you want to use hashtags in a post, you'll have to include `twitter--hashtags` in the `share` property of the front matter. **NOTE:** You'll still need the `twitter` identifier as well, so you would have something like `share: twitter twitter--hashtags`.

If you opt for using this custom layout, you will have to configure your IFTTT trigger to just use the `{{EntryTitle}}` ingredient, as the post title, tags and URL will all be fitted into the title field in the feed.
