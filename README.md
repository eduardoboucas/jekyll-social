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
