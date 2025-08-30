
> [!IMPORTANT]  
> This documentation is a **Work In Progress**.

# OIC Movies Technical Information

[OIC Movies](https://www.oicmovies.com) is a site featuring captioned ASL[^help.asl] Videos meant for student practice. Its hosted through WordPress[^help.wordpress] and has a [Membership](https://www.oicmovies.com/membership-account/membership-levels).

## Files

OIC Movies does not check your mebership when you request a file from it's raw URL. All files are hosted through WordPress and thus all URLs are publically indexed through [/wp-content/uploads](https://www.oicmovies.com/wp-content/uploads).


Due to OIC Movie's Open Graph Protocol[^help.ogp] conformance, raw Video URL's are included in eacg post's HTML under the `og:video` and `og:video:secure_url` OGP Meta Properties regardless of membership or authentication status.

### Videos

Videos are stored as MP4s[^help.mp4] at URLs in the format `http(s)://www.oicmovies.com/wp-content/uploads/<#YYYY#>/<#MM#>/<#YYYY#>_<#MM#><#DD#>_<#Content Name#>.mp4`. The full Regex[^help.regex] for this appears to be roughly `/https?:\/\/www\.oicmovies\.com\/wp\-content\/uploads\/\d{4}\/\d{2}\/\d{4}_\d{4}_[a-z0-9_]+\.mp4/gm`.

**Ex:** [`http://www.oicmovies.com/wp-content/uploads/2011/05/2011_0501_cassie_dadicecream.mp4`](http://www.oicmovies.com/wp-content/uploads/2011/05/2011_0501_cassie_dadicecream.mp4)

> [!TIP]
> There are several WordPress-formatted URLs in the HTML; I recommend disambiguating by matching against the enfolding `og:video` or `og:video:secure_url` OGP Meta Property element aswell.

### Caption Files

Captions are stored outside of the MP4s in VTT[^help.vtt] and XML[^help.xml] files. Both the VTT and XML files contain the full caption text and timestamps; presumably the duplication is an artifact from WordPress. Caption files are named the same as the MP4s, however are instead typed `.vtt` or `.xml`.

**Ex:** [`http://www.oicmovies.com/wp-content/uploads/2011/05/2011_0501_cassie_dadicecream.vtt`](http://www.oicmovies.com/wp-content/uploads/2011/05/2011_0501_cassie_dadicecream.vtt)

### Images

Thumbnails and other images, like the video and caption files, are hosted through WordPress. All images are stored in multiple resoultions as JPEGs[^help.jpeg]. Thumbnails are named the same as the MP4 they shadow appended `_thumb0`. Resolutions are incuded in the filenames with the appensions `-100x50`, `-150x150`, `-250x150`, `-270x134`, or `-300x120`. All images, including thumbnails, are named with their resolution.

**Ex:** [`https://www.oicmovies.com/wp-content/uploads/2015/03/2011_0501_cassie_dadicecream_thumb0-270x134.jpg`](https://www.oicmovies.com/wp-content/uploads/2015/03/2011_0501_cassie_dadicecream_thumb0-270x134.jpg)

## URLs

### Sitemap

OIC Movie's Sitemap can be found at [/wp-sitemap.xml](https://www.oicmovies.com/wp-sitemap.xml) or [/static/assets/sitemap.xml](https://www.oicmovies.com/static/assets/sitemap.xml). It indexes every page, including every post ([`/wp-sitemap-posts-post-1.xml`](https://www.oicmovies.com/wp-sitemap-posts-post-1.xml) and [`/wp-sitemap-posts-post-1.xml`](https://www.oicmovies.com/wp-sitemap-posts-post-2.xml)), tag ([`/wp-sitemap-taxonomies-post_tag-1.xml`](https://www.oicmovies.com/wp-sitemap-taxonomies-post_tag-1.xml) and [`/wp-sitemap-taxonomies-post_tag-2.xml`](https://www.oicmovies.com/wp-sitemap-taxonomies-post_tag-2.xml)), branch ([`/wp-sitemap-posts-page-1.xml`](https://www.oicmovies.com/wp-sitemap-posts-page-1.xml)), author ([`/wp-sitemap-users-1.xml`](https://www.oicmovies.com/wp-sitemap-users-1.xml)).

### Posts by ID



<!-- MARK: Footnotes -->
[^help.asl]: [What is ASL?](https://en.wikipedia.org/wiki/American_Sign_Language)
[^help.wordpress]: [What is WordPress?](https://wordpress.com)
[^help.ogp]: [What is the Open Graph Protocol?](https://ogp.me)
[^help.mp4]: [What is an MP4?](https://en.wikipedia.org/wiki/MP4_file_format)
[^help.regex]: [What is a Regex?](https://en.wikipedia.org/wiki/Regular_expression)
[^help.vtt]: [What is a VTT?](https://en.wikipedia.org/wiki/WebVTT)
[^help.xml]: [What is an XML?](https://en.wikipedia.org/wiki/XML)
[^help.jpeg]: [What is a JPEG?](https://en.wikipedia.org/wiki/JPEG)
