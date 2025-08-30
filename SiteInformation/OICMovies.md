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

## URLs

### Sitemap

### Posts by ID

<!-- MARK: Footnotes -->
[^help.asl]: https://en.wikipedia.org/wiki/American_Sign_Language
[^help.wordpress]: https://wordpress.com
[^help.mp4]: https://en.wikipedia.org/wiki/MP4_file_format
[^help.regex]: https://en.wikipedia.org/wiki/Regular_expression
[^help.vtt]: https://en.wikipedia.org/wiki/WebVTT
[^help.xml]: https://en.wikipedia.org/wiki/XML
[^help.ogp]: https://ogp.me