---
layout: post
title: Introducing Drekyll!
date: 2014-09-01T14:51:11.002Z
---

### Note: I have deprecated Drekyll

So im new to Jekyll and so far I’m loving it, I already use it for two of my sites (this and TeenTech's website). My only complaint is that I couldn't find a good Markdown editor. I'm Dyslexic and my spelling is atrocious, when i'm writing lots of text I want to use an editor with good spell check and all the other niceties. The trouble is most text editors, such as Sublime or Textwrangler, are use primarily for coding. As such they have no or a very limited spell check. My first thought was to use MS Word as a text editor but it turns out that editing Markdown files in Word doesn't work all that well. It was when I was playing around with some autoCrat stuff that it hit me. I could use Google docs!

<!--more-->

<span style="font-style:italic;text-decoration:underline;font-weight:bold;">Underline</span>

Google docs would<span style="font-style:italic;">be perfect, t</span>hey have a solid spell check and all the other stuff you want from a text editor and as an added bonuses e<span style="font-weight:bold;">verything i</span>s saved in the cloud. Now I know what you're thinking. “Thats great Tim but how are you going to get the docs into a post?” But that’s the best part!

<h3 style="page-break-after:avoid;">

				Introducing Drekyll

	</h3>

<span style="font-style:italic;">Through the power of Google Apps Script and Github Api. Posting a formatted google doc to a Jekyll powered site can be done from the push of a button. Google automagicly adds all the needed Html Tags if you don't like markdown. but you can still have the power of markdown through the use of some magic regex’s.</span>

<span style="font-style:italic;">eg, Here is some inline code:</span>

{% highlight javascript linnos %}
//We can have block code
/* With syntax highlighting! */
function test(var someting){
   var this = document.getelementbyid("test");
   for (var i = 0; i &lt; someting; i ++){
      doSometingAwesome("yes thats right!")
   }
   return "It did everything and more"
}
{% endhighlight %}

But I admit its not perfect, to use the syntax highlighter you need to wrap it in a `&lt;code&gt;&lt;/code&gt;` tag.
That said, I was able to post this directly from a google doc.

