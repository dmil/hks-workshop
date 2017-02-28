# Part 2: Unpacking Websites & Hunting for Data

## Data on the Web

Many pages on the web that serve data will do so through APIs. These apis may be internal or external. Before we talk about scraping and data collection, we're going to breifly delve into the world of APIs to better understand how a data-driven website is constructed.

### CRUD

Most data-driven web applications at their core will be what programmers call "CRUD" apps.

CRUD apps perform the following functions, they allow you to 
**C**reate
**R**ead
**U**pdate
and
**D**elete resources.

Someone once told me "The government is essentially just a newtork of crud apps"

* https://en.wikipedia.org/wiki/Create,_read,_update_and_delete

We won't linger on these terms, but I would recommend spending some time googling these, this should get you to some good literature / forums about the basics of website architecture.

### APIs

APIs are what web apps use to communicate. Just as you read a web-page and synthesize data presented on the page via its visual interface, the API is a way for the website to serve the same information in a more structured interface. Usually this interface is consumed by another program and structured either as [XML](https://www.w3schools.com/js/js_json_xml.asp) or [JSON](https://www.w3schools.com/js/js_json_xml.asp) format, though the trend has been towards JSON and away from XML for most simple CRUD apps.

> ... what the world might be like when our software turns to the Web just as frequently and casually as
we do. Today, of course, we can see the faint, future glimmers of such a world.There is software that phones home to find out if there’s an update.There is software where part of its content—the help pages, perhaps, or some kind of catalog—is streamed
over the Web. There is software that sends a copy of all your work to be stored on the Web. There is software specially designed to help you navigate a certain kind of web page. There is software that consists of nothing but a certain kind of web page.
There is software—the so-called “mashups”—that consists of a web page combining information from two other web pages. And there is software that, using “APIs,” treats other web sites as just another part of the software infrastructure, another function it can call to get things done.
>
> Our computers are so small and the Web so great and vast that this last scenario seems like part of an inescapable trend. Why wouldn’t you depend on other web sites whenever you could, making their endless information and bountiful abilities a seamless part of yours? And so, I suspect, such uses will become increasingly common until, one day, your computer is as tethered to the Web as you yourself are
now.
>
>\- [Swartz: Introduction](http://www.morganclaypool.com/doi/pdf/10.2200/S00481ED1V01Y201302WBE005)

### How Web Apps are Structured

> The other week I made one of my rare excursions from my plushly-appointed bed
and attended a local party. There I met a man who made a website for entering
and visualizing data. I asked him whether he had an API, since it seemed so useful
for such a data-intensive site. He didn’t, he said; it would be too much work to
maintain both a normal application and an API.
>
> I tell you this story because the fellow at the party was wrong, but probably
in the same way that you are wrong, and I don’t want you to feel bad. If even welldressed
young startup founders at exclusive Williamsburg salons make this mistake,
it’s no grave sin.
> 
> See, the mistake is, that if you design your website following the principles
in this book, the API isn’t a separate thing from your normal website, but a natural
extension of it. All the principles we’ve talked about—smart URLs, GET and
POST, etc.—apply equally well to web sites or APIs. The only difference is that
instead of returning HTML, you’ll want to return JSON instead.
>
> \- [Swartz (Chapter 5)](http://www.morganclaypool.com/doi/pdf/10.2200/S00481ED1V01Y201302WBE005)



### Resource

Most APIs will follow the [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) convention. Rest stands for "Representational state transfer" and was famously outlined in [Roy Feilding's Dissertation](http://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm). 

Key takeaway from knowing about REST is the concept of a **resource**. 
>"Web resources" were first defined on the World Wide Web as documents or files identified by their URLs, but today they have a much more generic and abstract definition encompassing every thing or entity that can be identified, named, addressed or handled, in any way whatsoever, on the Web
>
> \- [Wikipedia artickle on REST](https://en.wikipedia.org/wiki/Representational_state_transfer)

Lets take an example:

* http://crunchbase.com/ - a website serving data about companies and investors

Explore another example with your neighbor. What are the "resources" in this web application?

* https://beta.fec.gov/data/

Further Reading:

* https://www.programmableweb.com/api-university/what-are-apis-and-how-do-they-work  
* https://www.thoughtworks.com/insights/blog/rest-api-design-resource-modeling

### URLs (URIs)

Uniform Resource Locator (Uniform Resource Identifier)

[What is a URL](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL) | [Anatomy of a URL](https://doepud.co.uk/blog/anatomy-of-a-url)
[![](assets/images/url.png)](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
source: https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177

#### What a URL reveals about a web app

> Furthermore, URLs have to last. Those t-shirts and links and blogs will
not disappear simply because you decided to reorganize your server, or move to a
different operating system, or got promoted and replaced by a subordinate (or voted
out of office). They will last for years and years to come, so your URLs must last
with them.
>
>Moreover, URLs do not just exist as isolated entities (like “http://
example.org/lunch/bacon.html”). They combine to form patterns
(“bacon.html”, “lettuce.html”, “tomato.html”). And each of these
patterns finds its place in a larger path of interaction (“/”, “/lunch/”,
“/lunch/bacon.html”).
>
> Because of all this, URLs cannot be some side-effect or afterthought, as
many seem to wish. Designing URLs is the most important part of building a web
application and has to be done first. Encoded in their design are a whole series of
implicit assumptions about what your site is about, how it is structured, and how it
should be used; all important and largely-unavoidable questions.
>
> \- [Swartz (Chapter 2:: Building for Users: Designing URLs)](http://www.morganclaypool.com/doi/pdf/10.2200/S00481ED1V01Y201302WBE005)

#### More about URLs

URL Encodings (when you see strange characters in a URL, consult this table):

* https://www.w3schools.com/tags/ref_urlencode.asp

Think in terms of "Resources" if you are navigating a well built site, or especially if you're hitting a REST api (which most APIs are). For example, what are the resources on this site? What assumptions if any, can you make about how their data is structured?

### Try It

1. Navigate to https://beta.fec.gov/data/advanced/
2. Observe how the URLs change across the site and discuss with the person sitting next to you. Try to map out the "resources" on their site.
3. Lets discuss as a group what this says about their site and how they store their data. 
4. Together lets look at their API https://api.open.fec.gov/developers/ and how the structure of the FEC API reflects on their site, and again what this reveals about their data.

#### Bonus

5. Lets hit the FEC API, get some JSON, convert it to CSV using an online tool
6. Get an API key, submit the same request via postman

### Why this is useful

You're steps away now from writing a program that can paginate through an API and collect all the data you need. The first step is exploring the URLs, manipulating them, and figuring out where the data you want is.

Even if you're not quite at the place where you can write the code, this will help you at least know what is possible, and a request like "paginate through these urls and give me these fields" is a really small ask. Also once you've done it once, you can do it again.

## HTTP
### HTTP Verbs: GET & POST
http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade#/6/4

GET | POST
----|-----
Requests data from a specific resource. |	Submits data to be processed by a specific resource.
Data is submitted as part of the URL | Data is submitted in the request body
Less secure but faster |	More secure but slower
Can be cached by browser |	Not Cached by Browser
Length Limited by URL size |	MaxLength determined by server

Source: 

http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade#/6/5

http://www.w3schools.com/tags/ref_httpmethods.asp

### HTTP: Headers

![](http://www.tcpipguide.com/free/diagrams/httprequest.png)

![](http://www.tcpipguide.com/free/diagrams/httpresponse.png)

[http://www.tcpipguide.com/free/t_HTTPResponseMessageFormat-3.htm](http://www.tcpipguide.com/free/t_HTTPResponseMessageFormat-3.htm)

### HTTP: Status Codes

https://www.w3schools.com/tags/ref_httpmessages.asp

https://en.wikipedia.org/wiki/List_of_HTTP_status_codes

### HTTP: Additional References

https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177

http://httpbin.org
https://requestb.in/

### Try It

1. Open the postman app
2. Open http://httpbin.org in chrome
3. Lets try the following examples of GET requests together. First in chrome, then in postman

	* `/` This page.
	* `/ip` Returns Origin IP.
	* `/user-agent` Returns user-agent.
	* `/get` Returns user-agent.
	* `/response-headers?key=value` Returns given response headers.

4. Lets try the following POST requests, first on the site, then via postman

	* `/post` Returns POST data
	* `/forms/post` HTML form that submits to /post

5. Make a GET request to the following URL in postman

	 https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json
	 
	  Drop the JSON into a [JSON to CSV converter](https://www.google.com/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=json+to+csv+converter) and download the CSV file that results. Open that file in excel


### HTTP requests from the terminal with `curl` & `wget`

Print results of HTTP request body to the terminal

```
curl https://pp-projects-static.s3.amazonaws.com/congress/staffers/2016Q3-house-disburse-detail.csv
```

Save results of HTTP request body to file

```
wget https://pp-projects-static.s3.amazonaws.com/congress/staffers/2016Q3-house-disburse-detail.csv
```

Save results of several HTTP requests to several files

```
wget https://pp-projects-static.s3.amazonaws.com/congress/staffers/20{09,10,11,12,13,14,15,16}Q{1,2,3,4}-house-disburse-detail.csv
```
### Why this is Useful

* You can get data with curl
* If you know how to manipulate URLS, you can get data with postman
* Writing scrapers is essentially just the art of figuring out which GET and POST requests to make in which order and selecting data with CSS selectors. Figuring out those things means you've already done most of the legwork leading up to writing a scraper.

## Hunting for Data

### The Network Tab: Finding a Hidden API
* http://www.realclearpolitics.com/epolls/2016/president/mi/michigan_trump_vs_clinton_vs_johnson_vs_stein-6008.html
* http://www.gallup.com/poll/113980/Gallup-Daily-Obama-Job-Approval.aspx
* https://venmo.com/

### Try It
Can you find the data?

* http://data.desmoinesregister.com/iowa-caucus/candidate-tracker/index.php
* http://polling.reuters.com/#poll/TR130
* https://obamawhitehouse.archives.gov/interactive-budget

### Journalism from the Network Tab

http://money.cnn.com/2015/01/21/technology/security/obamacare-website-advertisers/

https://www.eff.org/deeplinks/2015/01/healthcare.gov-sends-personal-data

https://fivethirtyeight.com/features/fandango-movies-ratings/



## Cleaning Data


### Regular Expressions (find and replace)
* https://regexone.com/
* https://regex101.com/

### Multi Line Cursor in Sublime Text
* Click & drag to select column(s): <kbd>Option⌥</kbd> + <kbd>LeftMouseBtn</kbd>
* Add other column(s) to selection by click & drag: <kbd>Option⌥</kbd> + <kbd>LeftMouseBtn</kbd>
* Add individual cursors: <kbd>Cmd ⌘</kbd> + <kbd>LeftMouseBtn</kbd>

alternatively

* select all with <kbd>Cmd</kbd> + <kbd>a</kbd>
* <kbd>Cmd ⌘</kbd> + <kbd>Shift</kbd> + <kbd>l</kbd> to get multiline cursor at the end of the line

moving the cursor

* one character a at a time: <kbd>←</kbd> and <kbd>→</kbd> 
* one word at a time: <kbd>alt</kbd> + <kbd>←</kbd> and <kbd>alt</kbd> + <kbd>→</kbd>
* one line at a time: <kbd>Cmd ⌘</kbd> + <kbd>←</kbd> and <kbd>Cmd ⌘</kbd> + <kbd>→</kbd>

### Try It (Together)
Clean the data using regular expressions and sublime text

Lets grab the data from Donald Trump's approval ratings on gallup: 

link to website:

http://www.gallup.com/poll/201617/gallup-daily-trump-job-approval.aspx

link to data:

http://www.gallup.com/viz/v1/xml/6b9df319-97d6-4664-80e1-ea7fe4672aca/POLLFLEXCHARTVIZ/TRUMPJOBAPPR201617.aspx

and paste it into both sublime text

1. Remove all the parts of that document that do not contain the data you're looking for
2. write regular expressions to extract only the parts we want
3. use multi-line cursor or regular expressions to convert the document into a list of comma separated values (CSV) which can be opened in excel


## Additional Resources
* Make a Simple Website
	* Best [tutorial](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web) in my opinion is Mozilla:
		- Part 1: [HTML](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
		- Part 2: [CSS](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
		- Part 3: [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
	* Code for my [simple website](https://dmil.github.io/simple-website/) to copy: github.com/dmil/simple-website
* JavaScript for Cats [http://jsforcats.com/](http://jsforcats.com/) 
	- Learn the basics of JavaScript using the console window in your browser. Takes only about an hour!
* Adding JS snippets to your console window.
  * `console.save` command: https://coderwall.com/p/prhwzg/add-console-save-to-chrome
  * More! http://bgrins.github.io/devtools-snippets/

### Software to Know About

* [Charles Proxy (Mac)](https://www.charlesproxy.com/)
* [Yesware](http://www.yesware.com/)
* [WireShark](https://www.wireshark.org/)
* [Postman Interceptor](https://chrome.google.com/webstore/detail/postman-interceptor/aicmkgpgakddgnaphhhpliifpcfhicfo?hl=en)

