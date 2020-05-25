Title: Getting Pelican set-up
Date: 2020-05-24 11:25
Category: howto
Status: Published

Making this complicated by including the CSS for Tufte.
Getting pelican setup, but read down to the virtualenv section first

https://docs.getpelican.com/en/stable/install.html

```bash
# make a directory
mkdir ~/alittleknowledge
cd ~/alittleknowledge
# setup a python virtualenv
pyenv install 3.8.3
pyenv virtualenv 3.8.3 alittleknowledge
pyenv local myproject
# confirm installation
pyenv which python
# install pelican
pip install Pelican Markdown typogrify
```

## Deploying 

Quite a lot of hassle getting localhost to be visible across the network (i.e. when developing from the ipad); fixed via https://www.bleepingcomputer.com/news/security/wsl2-now-supports-localhost-connections-from-windows-10-apps/ ... where we had to make the server accessible to all addresses. This seems to be the case for both WSL and Mac OS.

```bash
pelican --listen -b 0.0.0.0:8000
```

## Themes

Found a [page of themes](https://github.com/getpelican/pelican-themes), but of greater interest is that I have found a [Tufte theme for Pelican](https://github.com/fabianp/TuftePelican). It looks a bit neglected but we'll see.

<section>
  <h2>Sidenotes: Footnotes and Marginal Notes</h2>
  <p>One of the most distinctive features of Tufte’s style is his extensive use of sidenotes.<label for="sn-extensive-use-of-sidenotes" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-extensive-use-of-sidenotes" class="margin-toggle"/><span class="sidenote">This is a sidenote.</span> Sidenotes are like footnotes, except they don’t force the reader to jump their eye to the bottom of the page, but instead display off to the side in the margin. Perhaps you have noticed their use in this document already. You are very astute.</p>
  <p>Sidenotes are a great example of the web not being like print. On sufficiently large viewports, Tufte CSS uses the margin for sidenotes, margin notes, and small figures. On smaller viewports, elements that would go in the margin are hidden until the user toggles them into view. The goal is to present related but not necessary information such as asides or citations <em>as close as possible</em> to the text that references them. At the same time, this secondary information should stay out of the way of the eye, not interfering with the progression of ideas in the main text.</p>
  <p>Sidenotes consist of two elements: a superscript reference number that goes inline with the text, and a sidenote with content. To add the former, just put a label and dummy checkbox into the text where you want the reference to go, like so:</p>
  <pre class="code">
&lt;label for="sn-demo" class="margin-toggle sidenote-number"&gt;&lt;/label&gt;
&lt;input type="checkbox" id="sn-demo" class="margin-toggle"/&gt;</pre>
  <p>You must manually assign a reference <span class="code">id</span> to each side or margin note, replacing “sn-demo” in the <span class="code">for</span> and the <span class="code">id</span> attribute values with an appropriate descriptor. It is useful to use prefixes like <span class="code">sn-</span> for sidenotes and <span class="code">mn-</span> for margin notes.</p>
  <p>Immediately adjacent to that sidenote reference in the main text goes the sidenote content itself, in a <span class="code">span</span> with class <span class="code">sidenote</span>. This tag is also inserted directly in the middle of the body text, but is either pushed into the margin or hidden by default. Make sure to position your sidenotes correctly by keeping the sidenote-number label close to the sidenote itself.</p>
  <p>If you want a sidenote without footnote-style numberings, then you want a margin note.
    <label for="mn-demo" class="margin-toggle">&#8853;</label>
    <input type="checkbox" id="mn-demo" class="margin-toggle"/>
    <span class="marginnote">
      This is a margin note. Notice there isn’t a number preceding the note.
    </span> On large screens, a margin note is just a sidenote that omits the reference number. This lessens the distracting effect taking away from the flow of the main text, but can increase the cognitive load of matching a margin note to its referent text. However, on small screens, a margin note is like a sidenote except its viewability-toggle is a symbol rather than a reference number. This document currently uses the symbol &#8853; (<span class="code">&amp;#8853;</span>), but it’s up to you.</p>
  <p>Margin notes are created just like sidenotes, but with the <span class="code">marginnote</span> class for the content and the <span class="code">margin-toggle</span> class for the label and dummy checkbox. For instance, here is the code for the margin note used in the previous paragraph:</p>
  <pre class="code">
&lt;label for="mn-demo" class="margin-toggle"&gt;&amp;#8853;&lt;/label&gt;
&lt;input type="checkbox" id="mn-demo" class="margin-toggle"/&gt;
&lt;span class="marginnote"&gt;
This is a margin note. Notice there isn’t a number preceding the note.
&lt;/span&gt;</pre>
  <p>Figures in the margin are created as margin notes, as demonstrated in the next section.</p>
</section>

List of modifications
- dropped google analytics
- trying to drop disqus blog roll

## Try out inline mermaid diagrams

<div class="mermaid">
graph LR;
  A-->B;
</div>
<script async src="https://unpkg.com/mermaid@8.2.3/dist/mermaid.min.js"></script>

## Now Math

This is $x^2+y^2=z^2$.

And this is a math block.

$$
\frac{n!}{(n-k)!k!}
$$
