---
layout: project
title: Dynamic Jekyll Site
subtitle: The Project of This Blog Site
categories:
- project
tags:
- javascript
- jquery
---

## You're Looking at It
[Jekyll][jekyll] is a great static site generator and I thought it was a perfect solution for the content on this site. I wanted the ability to tag posts _and_ filter posts by tag. With a static site, it’s easy enough to tag posts. But what about tag filtering? In a typical dynamic CMS, a tag filter may look something like:

 `http://example.com/blogs/2012/12/02/topic.html?tag=software`.

 Yet a static site has no way to process the query params. Of course we can lean on the client to perform the tag filtering, but how does the client know how to find the content? As it turns out, I learned a great solution from [these](http://developmentseed.org) guys. Just generate a JSON file with all the site’s content metadata. (It’s an obvious solution in hindsight). So I implemented the solution and pushed it to the [upstream][upstream] repo where I got this theme. With the `site.json` generation in place, I was now ready to implement the client-side filtering. It only makes sense to provide filtering on the index pages, so I created a jekyll include file (see [this][commit] commit) to make it as decoupled as possible. Using some jquery and the [purl][purl] library on the index pages:

{% highlight javascript %}
   $(function() {
        // See if we're entering this page with a tag filter
        var tag = purl().param('tag');
        var filteredUrls = {};
        if (tag) {
            // Now get the site map (often from cache)
            $.get('/site.json', function(data) {
                // Filter posts that don't match the tag
                data.forEach(function(item) {
                    var tags = item.tags;
                    if (tags) {
                       for (var i = 0; i < tags.length; i++) {
                            if (tags[i] == tag) {
                                filteredUrls[item.url] = item;
                                break;
                            }
                        }
                    }
                });

                // Hide non-matching posts
                $('#blog-posts > li > a').each(function() {
                    var href = $(this).attr('href');
                    if (!filteredUrls[href]) {
                        $(this).parent().hide();
                    }
                });
            })

            // Add a tag title
            $('#tag-title').html('<span class="tag">' + tag + '</span>');
        }

    })
{% endhighlight %}

We use jquery to make an ajax call to get the site.json file, then read the contents and identify which posts are relevent based on the tag in question. Next, we use the results to filter and hide unrelated posts. Lastly, we display the filtered tag before the index.

Now we just need some posts to make this effort useful...


[jekyll]: http://jekyllrb.com
[upstream]: https://github.com/swanson/lagom/pull/6
[commit]: https://github.com/spitimage/spitimage.github.io/commit/98e6267cf0a328dd3d36bcea47f3c8e4537aa1fb
[purl]: https://github.com/allmarkedup/purl
