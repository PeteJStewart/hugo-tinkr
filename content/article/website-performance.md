+++
date = 2018-09-17T13:56:19+01:00
publishdate = 2018-09-17T13:56:19+01:00

title = "Website Performance"
subTitle = "Perceived load time & Time to interactive"
tags = ["Web Perf"]

description = "In this article I’m going to look at improving the perceived load time and reducing the time it takes the end user to be able to interact with the website.  Although website performance as a whole is a much larger subject, these are two of the main issues many websites face."

type = "article"

styles = ["https://fonts.googleapis.com/css?family=Noto+Serif+JP:500,700"]

[amp]
    elements = []
    
[article]
    lead = "Looking at improving the perceived load time and reducing the time it takes the end user to be able to interact with the website."
    category = ""
    related = []

[author]
    name = "Pete Stewart"
    image = "/img/authors/80dHNPJ7P3vme7tC5po0-small.jpg"
    bio = ""
    homepage = ""



[image]
    src = "/img/articles/web-performance.png"
    title = ""
    author = ""
    link = ""
    license = ""
    licenseLink = ""

[sitemap]
  changefreq = "monthly"
  priority = 0.5
  filename = "sitemap.xml"

+++
For more information on the impact load time can have on overall website performance, take a look at the following infographic created by skilled.co:
https://skilled.co/wp-content/uploads/2016/11/Website-speed_Infographic_Skilled_Final.jpg

How long it takes for a website to load or at least for the user to perceive it has loaded, and for them to be able to use the site, comes down to a few basic factors:

* Assets (the content and the code that defines the style and functionality of the site)
* Rendering (how this code is generated, whether that be dynamically or statically)
* Delivery (where this code is coming from and how it is being sent)

## Asset Development
Optimisation of website assets is often the largest issue when looking at website performance.  
According to [http archive][1] the average page weight is 1200 - 1500 KB, comprising of  67 - 75 requests, where  ~30 of these requests are JS, CSS & fonts (400 KB,  50 KB & 90 KB respectively). 

### Javascript
Hand crafting Javascript rather than using a number of libraries and plugins should really help here.  I often see web pages loading 20 - 30 Javascript files, when the page is actually only using one of two of these or about 5% of the total JS code.

I also highly recommend moving interaction animations to CSS as they are often smoother and more reliable.  Doing so should also reduce user interaction lag, as JS is not being processed to create the animation.

Once javascript bloat is no longer an issue, you can then look at optimising the JS itself to reduce the processing time and ultimately the time to interaction.

### CSS
Using well established methodologies such as BEM & SMACSS when writing CSS can really help to improve performance and reduce file size.  Writing your CSS in an order of specificity should help to reduce unnecessarily overriding style and therefore also reduce required CSS.  Start writing CSS with the least specific selectors, such as elements, and then work up to the most specific selectors, such as a class modifier.

##### CSS Example:
```css
p {
      Font-size: 16px;
      Color: #333;
}

.c-services__body {
  Margin: 10px;
}

.c-services__body--bold {
  Font-weight: bold;
}
```

##### html Example:
```html
<p class="c-services__body c-services__body--bold">
  Bold service body text
</p>
```

In this example the CSS is relatively flat, so the order is the main specificity factor and there is complete inheritance with each following class. 

### Fonts
You can often reduce fonts that are needed by using SVGs for icons and perhaps variable fonts if suitable.  

### Images
Images have often been an issue discussed when website performance is concerned.  These days WebP image format is pretty well supported and can be set to have a JPEG/PNG fallback by using the html5 picture element. [Studies show that WebP gives additional 25%-34% compression gains compared to JPEG][2]. So it’s definitely worth using when we consider images are ⅓ of the bytes transferred for an average web page.

Combining well compressed images with lazy loading, can hugely improve page load time.  [Lazy loading can be achieved with some simple javascript][3], and soon may even be a built-in feature for Chrome if not other browsers.

### Development Tools
It’s always best to combine, compress and optimise your assets during development, rather than on the server.  I recommend using a development tool such as [Webpack][4], [Gulp][5] or [Grunt][6] to automate these tasks while you’re developing.  It’s also worth considering [static compression using Brotli][7] at this stage.

## Rendering
How the code is rendered will mainly affect the Time To First Byte (TTFB).  

### Dynamic Websites
Website content is often dynamically rendered using server side languages such as PHP. For many website this isn’t a huge issue, as their rendering code — whether that be a  popular CMS, Framework or custom code — is well optimised and the TTFB is respectable.
I have however come across website that have a Time To First Byte that is over the 2 seconds we’re aiming to have the whole site loaded within.    

If it is essential to render dynamically, then optimising the process with server caching, and making sure the code and the server are running as expected should help.   

There is a lot that can be done to improve dynamic rendering, but if it’s not essential, not much can beat static, pre rendered html and assets!
Static Site Generators
There are many modern static site generators that can often be used instead of dynamic code.  Using pre rendered html can hugely improve server response time and can also reduce server costs.  There are many benefits to gain from using static code, but it doesn’t suit every website.

## Delivery
How the website and its assets are delivered can make the world of difference.  If you’re serving your site from a single shared server miles away from the majority of your users, then it’s probably going to take a while to get to them.  

### Content Display Networks (CDN)
If on the other hand you are serving your website through a Content Display Network (CDN) that has many servers all over the world and can deliver the assets from the nearest one to each user, then it should be much quicker.

Delivery isn’t just to do with where your content is coming from, though.  It’s also important what technology is being used to get it there.  

### HTTPS & HTTP/2
Running your website over https doesn’t only make your website much more secure for yourself and it’s users, it also allow you to use http/2.  

http/2 enables Multiplexing, which basically mean many of your assets can be requested at the same time, rather than one after the other.  This can often half the load time of a website!

### SSL/TLS Cipher & Caching
To enable https you used to need an SSL (Secure Sockets Layer) Certificate.  This has now been superseded by TLS (Transport Layer Security) Certificates.  There are many cipher that can be used with both SSL & TLS, some are more secure and also faster.
The connection parameters can also be cached to reduce overheads. 

### Compression
There are two main compression types to look at, gzip & brotli.  Gzip is usually faster at on-the-fly compression, whereas brotli will usually give a much smaller file size for the same end quality of compressed assets.  You can compress assets during development  using brotli, and then serve them without the need for on-the-fly compression. 
However, if your website is mainly dynamically generating content and assets, this might not suit you, and gzip may be better. 

### Hardware
It’s relatively standard to be able to get a server that is using Solid State Disks these days, along with fast RAM, Processors and Network connections.  It’s always worthwhile spending a little more to get a server that is the correct specification for your needs.

## In Summary 
When looking at the load performance of a website, we should be aiming to have the website usable within 2 seconds, otherwise we will see a significant drop off of users, which could cause long term damage to the website user base.

Careful thought when it comes to the architecture of the code can reduce assets bloat and improve overall performance.

Choosing the right tool for the job can also bring great improvements when we’re looking at website load time and TTFB, so make sure this is properly explored.

How the content and assets are served can make a huge difference, so make sure you’re using the latests technology and adequate hardware.

I’ll be writing more detailed articles on each of these topics in the future.

[1]: http://httparchive.org/reports/page-weight?start=2017_08_15&end=latest&view=list "HTTP Archive"
[2]: https://developers.google.com/speed/webp/docs/webp_study "WebP Study"
[3]: https://developers.google.com/web/fundamentals/performance/lazy-loading-guidance/images-and-video/ "Simple Javascript Lazyloading"
[4]: https://webpack.js.org/ "Webpack"
[5]: https://gulpjs.com/ "Gulp"
[6]: https://gruntjs.com/ "Grunt"
[7]: https://css-tricks.com/brotli-static-compression/ "Static Brotli Compression"
