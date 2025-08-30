> [!IMPORTANT]  
> This documentation is a **Work In Progress**.

# OIC Movies Technical Information

[OIC Movies](https://www.oicmovies.com) is a site featuring captioned ASL[^help.asl] Videos meant for student practice. Its hosted through [Wordpress](https://wordpress.com) and has a [Membership](https://www.oicmovies.com/membership-account/membership-levels).

## Files

OIC Movies does not check your mebership when you request a file from it's raw URI[^help.uri]. All files are hosted through Wordpress and thus all URIs are publically indexed through [/wp-content/uploads](https://www.oicmovies.com/wp-content/uploads).


Not only does OIC Movies not verify membership when fetching files, it appears it only ever checks Client-Side[^help.clientSide]. That is to say, Video URI's are included in the page's HTML under the `og:video` and `og:video:secure_url` Meta Properties regardless of membership or authentication status.

### Videos

Videos are stored as MP4s[^help.mp4] at URIs in the format `https://www.oicmovies.com/wp-content/uploads/<#YYYY#>/<#MM#>/<#YYYY#>_<#MM#><#DD#>_<#Content Name#>.mp4`. The full Regex[^help.regex] for this appears to be roughly `/https:\/\/www\.oicmovies\.com\/wp\-content\/uploads\/\d{4}\/\d{2}\/\d{4}_\d{4}_[a-z0-9_]+\.mp4/gm`.

> [!TIP]
> There are several Wordpress-formatted URLs in the HTML; I recomend disambiguating by matching against the enfolding `og:video` or `og:video:secure_url` Meta Property element aswell.

### Caption Files

Captions are stored outside of the MP4s in VTT[^help.vtt] and XML[^help.xml] files. Both the VTT and XML files contain the full caption text and timestamps. Presumably the duplication is an artifact from Wordpress.

### Images

## URLs

### Sitemap

### Posts by ID

<!-- MARK: Footnotes -->
[^help.asl]: https://en.wikipedia.org/wiki/American_Sign_Language
[^help.uri]: https://en.wikipedia.org/wiki/Uniform_Resource_Identifier
[^help.clientSide]: https://www.cloudflare.com/learning/serverless/glossary/client-side-vs-server-side
[^help.mp4]: https://en.wikipedia.org/wiki/MP4_file_format
[^help.regex]: https://en.wikipedia.org/wiki/Regular_expression
[^help.vtt]: https://en.wikipedia.org/wiki/WebVTT
[^help.xml]: https://en.wikipedia.org/wiki/XML