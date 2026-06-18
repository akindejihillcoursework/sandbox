  Thanks to the [markdown-it](https://github.com/markdown-it/markdown-it) for Node and [Marko](https://pypi.org/project/marko/) for Python this knowledge base interprets standard Markdown if you wish to use it.  Markdown allows you to organize your thoughts by adding emphasis to phrases, adding headings, "links", code segments, and even images.  

  The goal is to use **Markdown** in this **C**ontent **M**anagement **S**ystem such that your documents are portable --- can be read in Markdown viewers (with minimal tweaks), or be copy and pasted from Markdown documents to instantly render nicely in HTML.  It uses formatting that is interpreted aesthetically in HTML, while keeping the source valid and compatible with other markdown interpreters.  It accomplishes this through syntax that has natural fallbacks when viewed in standard Markdown renderers.  

  This article is just a quick start reference guide.  I recommend reading through this completely one time, but don't worry about trying to memorize everything.  Just get a good idea of what kind of formatting and content you can use in this application, so that when you need it you know what you can look up.  The syntax is so simple, you will automatically memorize it without trying, after looking things up a few times.

There is also a great Markdown tutorial and reference at **[Commonmark.org](https://commonmark.org/help/tutorial)**

---

## Headings
:::float-right

Heading levels
|hashes|equivalent tag|
|-|-|
|#|``<h1>``|
|##|``<h2>``|
|###|``<h3>``|
|####|``<h4>``|
|#####|``<h5>``|

:::

The word "Headings" above is a good example of a heading.

**Standard markdown:**  
* Start a line with a ``#`` mark and a space for ``<h1>`` text.  
* Two ``##`` renders ``<h2>`` text. 
* Three ``###`` renders ``<h3>`` text, and so on


Browsers typically render ``<h1>`` tags as very large text and ``<h2>``, ``<h3>`` etc get smaller from there.  

:::center
:::float-left

Heading syntax
    # Heading 1
    ## Heading 2
    ### Heading 3
:::
:::float-right

# Heading 1
## Heading 2
### Heading 3


:::
:::

Always keep in mind that headings are just as important for semantic readability and navigation, as they are for aethetics.

You'll want to use **heading 2** ``##`` for major sections, and **heading 3** ``###`` for sub-sections.  **Heading 4** is useful to denote smaller paragraph groupings or headings, but by default looks the same as bold text.  

>Heading levels 5 and 6 are also available but they look like regular text.  If you need to go this deep, then it might be better to consider re-organizing your document.
&nbsp;

### There can only be one
:::float-right
|The "**h**" in ``<h1>`` must stand for **h**ighlander, because there can only be one|
|-| 
:::
<h*n*> tags have a semantic meaning in HTML.  They let the browser know that it is a certain type of heading.  ``<h1>`` tags are for the main title of the page, and there should only be one.  This CMS disables the use of *real* ``<h1>`` tags in articles, because the **one and only** ``<h1>`` tag will be used by the article title.  For Markdown document compatibility ``#`` lines will still be styled as the largest text in an article, so you can still copy and paste your markdown documents into an article without an issue.  However, to maintain ADA compliance they will actually be rendered as ``<h2>`` tags in the html code.

It's much better to just avoid the use of ``#`` markers for major section headers in favor of ``##`` markers.  Semantically the ``##`` lets browsers know that the line starts a major section, but is not the main title for the page.  These semantics are very important for keyboard navigation, SEO, accessibility, and ADA compliance.


#### Don't confuse the navigation

Notice how the "**Heading 1**" (``#``) above is represented in the Table of Contents as a sibling to "**Heading 2**" (``##``) and not as a parent, because as already mentioned, it's actually rendered as an ``<h2>`` tag.  

Also, both headings belong nested within the "*Headings*" topic but they are not because using an equal or higher heading tag like "**Heading 1**" breaks the hierarchy and starts a new one.  If headings aren't used properly it makes navigation confusing.  In the way that it makes the TOC confusing, that's exactly how it makes a screen reader confused as well.  So, place your headings in the proper order, without skipping over any.  

Further more, if you must use an ``<h1>`` tag, try to do so only once, and at the top of the page as a subtitle.  That will minimize confusion.

&nbsp;
:::center

    ###c Centered Headings
:::

:::center

### Centered Headings
:::

Usually headings are left justified, but maybe once in a while you want a heading to be centered for some reason.  This CMS also includes non-standard markers for placing centered headers.  Just add a "c" after the hash marks to turn a standard heading into a centered heading.  

==Be aware== that these will not work in any other Markdown renderer.  An alternative is to use [positioning fences](/posts/2#POSITIONING-MEDIA) instead.


&nbsp;

## Horizontal rules
---
The line above is a horizontal rule.  Like headings, horizontal rules can help with sectioning an article.  Making them is super easy.  Just put three dashes, underscores, or asterisks on a line by themselves.  

Three ways to create a rule bar
    ---
    ___
    ***


---
___
***

&nbsp;

## Emphasis
---
To add **emphasis** to a phrase:

* Surround it with ``*`` asterisks for *italics*

* Surround it with ``**`` double asterisks for **bold** text. 
* Surround it with ``==`` double equals for ==Highlighted== text 
* Surround it with  ``~~`` double tildes for ~~Striked out~~ text

:::center
example
    I'm feeling **bold** today
:::
&nbsp;

## Superscript and Subscript
---
Surround a character in ``^`` to make is a superscript character,  Great for exponents.

Suround a character in ``~`` to make a subscript character.

:::center
:::float-left
Example syntax:
    y=x^2^
    H~2~O
    ^1^/~4~
:::

y=x^2^
H~2~O
^1^/~4~ 
:::

&nbsp;
## Links
---
There are two types of links you can use in Markdown.  There are in-line links and reference like links.

### In-line links
Links can be placed in-line with the text by simply typing a URL enclosed in angle brackets like
 
Example inline link
    <http://www.disneyworld.com> 

&nbsp; <http://www.disneyworld.com> 

You can also turn text into a link by enclosing a label with square brackets ``ex. [label]`` followed immediately by a URL in parenthesis ``ex. (https://mylink.com)`` 

Example
    Let's go to [Disney World!](http://disneyworld.com) !

&nbsp; Let's go to [Disney World!](http://disneyworld.com) !


### Reference Links

Similar to in-line links, you enclose the label in square brackets ``[label]`` but instead of a URL, you follow with a set of parenthesis containing an ID number `` [1] ``.  Then elsewhere in the page, usually at the bottom, you will want to assign a URL to each ID number.


Example reference links
    I was at [Disney World][1] last week, and someone asked me, 
    "Yo, how often do you come to [Disney World][1]?"

    [1]:https://www.waltdisneyworld.com

>I was at [Disney World][1] last week, and someone asked me, "yo, how often do you come to [Disney World][1]?"

[1]:https://www.waltdisneyworld.com
Notice that I used the same reference number for both labels because they are both using the same link.  That is very convenient in this case because "**Walt** Disney World" recently changed it's name to just "Disney World", and now that URL is wrong.  But I only have to update it in one place, and both broken links will be fixed.  What will I do with *all* that time I saved?



## Blockquotes 
---
Blockquotes are semantic elements that tell browsers that the content is sourced from somewhere else or is an important note or summary.  They are usually styled to stand apart from the normal flow of text in some way.


Example blockquote
    > "According to experts **blockquotes** should be used primarily for long quotes that relate to the context."

> "According to experts **blockquotes** should be used primarily for long quotes that relate to the context.  However they can also be used for other important text."

The most important rule for blockquotes is that they are semantic elements, not styling elements. They carry a specific meaning for web browsers, search engines, and screen readers.  Using them wrong can reduce the accessibility and indexing of your content.

**Blockquotes should be used for:**
* **Direct Quotes** --- Words spoken or written by someone else, often accompanied by the source.
* **Key Takeaways** --- A "bottom-line" summary of the points you have just discussed.
* **Definitions or Explanations**: A concise, formal definition of a term you are using.
* **Pro-Tips or Warnings**: Helpful advice or important caveats that the user should be mindful of.

**Blockquotes should not be used for:**
* **For Short, Inline Phrases** --- use regular quotation marks for words or short sentences that fit in a paragraph; or use the ``<q>`` tag to identify a short quote. 
* **Visual Indentation** --- Screen readers announce ``<blockquote>`` content as a "quotation" or "cited text." If the are really just indentations, visually impaired users will be mislead and confused.  In this application you can use tabbed lines instead.
* **For Emphasis or visual decorations** --- using them just to break up the "monotony" of a long page undermines the semantic purpose of the element.  Use a text-box instead.
  * If a search engine crawls your page, it may incorrectly attribute the text to an external source or mistakenly categorize it as a citation.
  * It creates "noise" for users navigating by element type. Professional accessibility tools allow users to jump to the next blockquote to find citations or source material; if your page is full of "decorative" quotes, that navigation tool becomes useless.


This application gives blockquotes a special effect when you combine them with asterisks.  

example
    Sometimes you just need block quotes...
    >***Because originality is over-rated.***

Sometimes you just need blockquotes...
>***Because originality is over-rated.***


Block quotes are super easy to do.  Just start a line with a ``>`` and the text following it will be included

example
    >And sometimes you need a ***quote***

> And sometimes you need a ***quote***


## The q and br tags

For simplicity as well as security, articles are formatted almost exclusively using markdown syntax.  HTML written into articles is not rendered, but instead displayed as literal text.  However there are two very specific exceptions.

1. The **quote** tag ``<q>...</q>`` is supported.  If you wish to semantically mark a short passage as a quote, or even attach a citation to it, you can just wrap the quoted content with the ``<q>`` tag.  The browser will automatically add the appropriate quotation marks.

:::center

    According to so and so <q cite="https://sonso.com"> You are what you eat.</q>
:::
&nbsp;

&nbsp; This transforms your quotes from simple text into structured data. While a human sees quotation marks, a computer sees a string of confusing, inconsistent characters; by using ``<q>``, you give machines a clear, unambiguous map of your content, ensuring your insights are perfectly preserved, correctly cited, and fully accessible to every reader.


2. **The line break tag** ``<br />`` can be used in Markdown table cells.  The source text for a table row must remain on one line, which means the only way to create a line break is to use this tag.



## Media
---
Images, audio, and video can be embedded into posts in a very similar syntax to links.  However take note that there is no Markdown standard for embedding audio or video.  This feature is provided in this CMS through non-standard markup extensions. 

### Images
The image syntax is just like a link except with an  exclamation point in front.  Instead of enclosing a label in square brackets, you enclose an ``alt`` text.  An ``alt`` or "**alternative**" text is what screen readers display instead of the image for the visually impaired.  Sometimes they are also displayed instead of the image if the image can't be found.  

&nbsp;
:::center
Image syntax
```markdown
![my cat](cat.png)
```
:::
![my cat](https://cerebrokb.akindeji.net/static/cat.png)

**⚠️Don't forget the Alt text❗**  

|By default the CMS fills in the alt text with the file name.  You **must** replace that with a brief description of the image.  Alt text violations are one of the biggest factors in accessibility law suits.|
|-|

If an image is purely decorative, like a border or seperator, use ``alt=""`` so that it can be ignored by screen readers.


### Audio
Standard markdown does not support embedding audio or video into documents, so this app uses a custom syntax to accomplish this. Insert an audio file like this:


```markdown    
[Caption text](audio:https://mysite.com/sound.mp3)
```

[Caption text](audio:/static/music.mp3)

&nbsp;

### Video
To insert a video use the prefix 'video:' before the URL.

*example*
```markdown
[Caption text](video:https://mysite.com/cerebro.mp4)
```

[Caption text](video:/static/Brain1.mp4)


### YouTube and other streaming services

[Has to be](youtube:https://www.youtube.com/watch?v=hAgwpO_gMnc)

YouTube videos can be embedded by prefixing "youtube:" instead of "video:" to the url.

*Example, embedding YouTube*
```markdown
[Has to be](youtube:https://www.youtube.com/watch?v=hAgwpO_gMnc)
```

You can also embed:
* Wistia ``[](wistia:url)``
* Vimeo ``[](vimeo:url)``
* YouTube playlists ``[](youtube-playlist:url)``.


### Media as links

You can also use a media item as a link by nesting the media syntax inside of the square brackets of the link marker.  For example, when you need to share a very big image you can display a smaller version of it, and link it to a larger version. 

*Example, Linking an image*
```markdown
[ ![reduced size battlecat image](../smallcat.png) ](../cat.png)
```
[ ![reduced size battlecat image](https://cerebrokb.akindeji.net/static/smallcat.png) ](https://cerebrokb.akindeji.net/static/cat.png)




## Tables
---
Inserting tables into markdown is easy and intuitive.

:::center
*Example 1*
```markdown
Example Table Caption
|Category 1|Category 2|Category 3|
|----------|----------|----------|
|value 1   |value 2   |value 3   |
|value 1a  |value 2a  |value3a   |
```
:::
&nbsp;
Example Table Caption
|Category 1|Category 2|Category 3|
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|

Tables can be used to show data in a neat and tidy format.  
To create a table:
* use pipes ( ``|`` under the backspace key ) to separate cells as shown in the examples.  
* The top row must contain the labels
* The second row must contain a row model that shows how many columns each row will have.  It's depicted with pipes ``|`` and dashes ``-``, and can match the size of the header row to make it easier to visualize, but they only require one dash.  
* There must be the same number of columns in each row, but they do not have to line up.
* A table row must be defined on one line; pressing enter to continue cell content on a new line will break the table.  To insert a line break in a table cell's content, use the ``<br />``  tag

Notice that you can place an **optional caption** in a table by immediately preceding it with a line of text.  A brief but descriptive table caption is very important for accessibility.

&nbsp;
|**Did you know?** Each row of a table must be on the same line<br /> in your source, but you can still use *html break tags* ``<br />``<br />inside a table cell to render line breaks.|
|-|

&nbsp;

## Figures: combining tables and media
---

HTML has a ``<figure>`` tag for displaying different types of media with or without a caption.  You can mimic this feature with markdown by inserting media into tables.  Doing so will produce something very close in appearance to an HTML figure.

This CMS can take those '*make shift*' figures and render them as real figures, while your markdown stays completely valid so it still works in other interpreters.  

### Text-Box
---
Placing text in a table with one cell will create a text box.  These are often called "call outs" or "pullout quotes".  They are decorative and pull a readers attention back to the text with something that stands out.

*creating a textbox using a table*
```markdown
|**Something you should know:**<br>Don't eat yellow snow!|
|-|
```

&nbsp;
|**Something you should know:**<br>Don't eat yellow snow!|
|-|

&nbsp;
These are great for:
* Emphasis and visual decoration - This is what you want to use for breaking up the 'monotony' of long sections of text, instead of a blockquote.
* Alerts, warning, or messages that are related to the content.  


### Quote
---

Create a quote box using a table with two cells.  Put the quote in the top cell, and the citation in the bottom cell.  The citation in the bottom cell is used as the accessible name.


```markdown
|***If debugging is the process of removing<br />software bugs, then programming must<br />be the process of putting them in***|
|-|
|- Edsger Dijkstra|
```
&nbsp; 
|***If debugging is the process of removing<br />software bugs, then programming must<br />be the process of putting them in***|
|-|
|- Edsger Dijkstra|

&nbsp;

### Frame
---
Placing media inside a single celled table centers and frames it.

*Example framed image*
```markdown
|![battecat](https://mysite.net/smallcat.png)|
|-|
```
&nbsp;
|![battlecat](https://cerebrokb.akindeji.net/static/smallcat.png)|
|-|

&nbsp;

### Image-Caption
---
You can create captioned media using a table with two cells by placing the media in the top cell, and the caption in the bottom cell.

*crating an image caption using a table*
```markdown
|![battle cat](../smallcat.png)|
|--------------------------|
|Image from cleanpng.com<br />by [Taishna](https://.../@taishna.html)|
```
&nbsp;

|![battlecat](https://cerebrokb.akindeji.net/static/smallcat.png)|
|-|
|Image from cleanpng.com<br />by [Taishna](https://www.cleanpng.com/users/@taishna.html)|

&nbsp;


## Positioning Fences
---

:::float-right
*Example right floated chart*
```
:::float-right

|Category 1|Category 2|Category 3|
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|

:::
```
:::
&nbsp;

:::float-right
|Category 1|Category 2|Category 3|
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|
:::

In this CMS application, media items (other than images) are centered by default, but you can float them to the left or right by encapsulating them in positioning fences.  This allows you to place a media item right next to a paragraph or explanation about it.

To use a fence to position an item, encapulate the whole element in a fence opening like ``:::center`` and a fence closing ``:::``.  


|Fence|Position|
|-|-|
|``:::center``|Center|
|``:::float-right``|Right|
|``:::float-left``|Left|
|``:::sr-only``|Invisible to browsers but <br /> visible to screen readers|
|``:::no-sr``|Invisible to screen readers|


>*Example floated image*
```
>|![reduced size battlecat image](https://mysite.net/smallcat.png)|
>|-|
```


>|![reduced size battlecat image](https://cerebrokb.akindeji.net/static/smallcat.png)|
>|-|

Images are the only media items that cannot be floated using block quotes alone.  If that were the case, it would remove the ability to place inline images inside of block quoted paragraphs or other items.  So to preserve the ability to use inline images, centered and floated images must be *framed* by placing them inside of a one cell table.  Then the whole table can be floated using block quote symbols in front of each row.




## Code blocks
---
Normal web page text does not preserve spaces.  This makes normal flowing text unsuitable to display programming code, text based diagrams, or ASCII images.  Standard Markdown provides two methods of creating code blocks for these purposes: ``Fenced Code blocks`` and ``Indented Code Blocks``.  


### Fenced Code Blocks

Fenced code blocks are the best choice for displaying computer language code because it uses clear beginning and end markers, and supports metadata to customize the display.  

Fenced code blocks are encapsulated in  a pair of triple back-tick `` ``` `` marks, or triple tildes `` ~~~ ``, like below.

Fenced code example
    Creating variables
    ```javascript
        let ten = 10
        let twenty = ten * 2;
    ``` 

Creating variables
```javascript
    let ten = 10
    let twenty = ten * 2;
```

Your code will be displayed with preserved spacing in a special box like the one above.  The **'language'** metadata after the opening marks are optional, but if you use them properly it will enable syntax highlighting for the coding language you are using.

Notice the **optional caption** "Creating variables" was created by writing a line of text directly over the fenced code.  Brief and descriptive captions should always be used to help make the document highly accessible.

Another feature of **fenced code blocks** in this application is the "**copy to clipboard**" button that appears when the mouse is over the block.  This enables visitors to easily copy the code from the document.  
&nbsp;
|**Accessibility concern**: Hearing the announcement "**clickable button, copy to clipboard**" from a screen reader gets quite annoying after a while when *fenced code blocks* are over used.  You can use the *indented code block* to render preformated text without the button.  It's highly recommend to use that whenever you do not need to display programming code.|
|-|

&nbsp;

### Indented Code Blocks

In standard Markdown **indented code blocks** are created by starting a line with four spaces.  A series of four-space-indented lines will all share the same code block

Example syntax
    Example syntax
        This indented code block shows how
        to create an indented code block.

Notice that the caption is written immediately above the first indented line.  Using a brief descriptive caption is highly recommended.
&nbsp;
|**Portability vs Accessibility**: Indented code blocks will not render in the Github markdown viewer unless there is a space between the caption line and the code block.  Although screen readers will still read the line, this breaks the explicit link between the caption and the block.|
|-|

**They are great to use for:**
* **Examples/Scenarios** --- A hypothetical situation or a concrete example to illustrate a concept.
* **Preformatted text** --- that is not code.
* **Accessibility** --- There is no "copy" button.  Use this instead when you don't want a screen reader to break up the flow by announcing  "clickable button, copy to clipboard".  That gets very annoying, very quickly.

:::sr-only
ASCII art by [Joan G. Stark]
:::

:::no-sr
ASCII art by [Joan G. Stark](https://www.asciiart.eu/art/8a42e16bbfdc388a) and folder diagram
         .-"-,
        /_ _  \      Folder Tree
        \@ @  /      
        (_= _)       📂/ (root)
          `)(_         ├── etc
          /((_`)_,     ├── home
          \__(/-"      ├── opt
         __|||__       ├── usr
    jgs ((__|__))      └── var
:::
&nbsp;
### In-line code segments

Sometimes you don't need a whole block to display an example, but you still want to make it stand out.  We use just two back-ticks `` ` `` for that, instead of three.  The displayed text can be in line with the rest of the text if you wish, or you can put it on its own line.  For instance to display just a variable declaration, you could use the following.


Inline code syntax example
    Add ``const PI = Math.PI;`` to the top.

Add ``const PI = Math.PI;`` to the top.


You can display command line interface (CLI) commands by starting the inline code with a prompt symbol.  For instance to display the Linux command to delete a file, you would type the following.

Ex.
```
Enter ``$ rm filename`` to delete the file.
```

>Enter ``$ rm filename`` to delete the file. 

Use `#` or `$` for linux shell commands, and `C:\>` for windows CLI commands.  

Ex: Listing files in a folder:
* Windows: `C:\> dir`
* Linux: `$ ls`
* Root shell: `# ls`



## Lists
---
Lists are super easy to do in Markdown.  


### Unordered lists
  
>Ex. Just start a line with an asterisk, dash, or plus sign.
```
#### Shopping List
* eggs
+ bacon
- milk
```
#### Shopping List
* eggs
+ bacon
- milk


### Task Lists
Task list are a great way to display what you have accomplished, what you still plan to do, and what you do not plan to do.
```
- [x] create bugs in my application
- [ ] fix bugs in my application
- [-] ~~ship application with bugs~~
```

- [x] create bugs in my application
- [ ] fix bugs in my application
- [-] ~~ship application with bugs~~

|⚠️**Portability Note**: Only the *checked* and *unchecked* markers are in the official markdown standard.  The ``- [-]`` marker for 'excluded' options was added specifically for this CMS, and will not work in other markdown interpreters.|
|-|

&nbsp;
### Ordered Lists
Ordered lists start with a number followed by a period or closing parenthesis.

Ex.
```
#### Things do do at Disney World
1. Get pictures with all the princesses and Mickey and friends.
2. Eat in Cinderella's castle during the fire works show
3. Ride Space mountain

```

**Things to do at Disney World**

1. Get pictures with all the princesses and Mickey and friends.
2. Eat in Cinderella's castle during the fire works show
3. Ride Space mountain

**Roman numerals:**

You can use Roman numeral list items by appending ``r.`` after the number.
&nbsp;
|==**Portability Warning:**==  *This roman numeral marker is not standard markdown and will not work in other interpreters.  Only use it for articles specifically meant for this CMS.*|
|-|

&nbsp;

```
1r. Top level
    1r. Nested level
    2r. second nested item
2r. Another top level
```

1r. Top level
    1r. Nested level
    2r. second nested item
2r. Another top level

&nbsp;

### Nested Lists
To nests lists, you just use 3 spaces to indent list items underneath a higher level list item.

Example nested list
```
#### Things to do at Disney World
1. Get pictures with all the princesses and Mickey and friends.
   - [ ] remember to bring autograph book this time 
   * pee before you get in line
2. Eat in Cinderella's castle during the fireworks show
   * call every hour of every day for the next 6 months to make a reservation until something opens up.
3. Ride Space mountain
   * don't get your hands chopped off

```
#### Things to do at Disney World
1. Get pictures with all the princesses and Mickey and friends.
   - [ ] remember to bring autograph book this time 
   * pee before you get in line
2) Eat in Cinderella's castle during the fireworks show
   * call every hour of every day for the next 6 months to make a reservation until something opens up. 
3. Ride Space mountain
   * don't get your hands chopped off


Example nested outline:
```
#### Outline
1r. Introduction
    1. Background information
        1r. Brief history
            * 1800 - 1900
            * 1900 - present
        2r. Current state
```
#### Outline
1r. Introduction
    1. Background information
        1r. Brief history
            * 1800 - 1900
            * 1900 - present
        2r. Current state


## Tabs and Indents
---

  You may often find youself in need of a way to push a paragraph inwards, away from the left margin.  There is no standard markdown syntax for this, so this interpreter uses methods that are invisible to standard Markdown, while also being quite aesthetic in HTML.  

### Indentation

  To create a typographically pleasing paragraph with a "**hanging indent**" like this, all you have to do is **start a line with 2 spaces**.  This will only work on paragraphs that begin at "column 0" of the document, or the very left edge.  This will not work on paragraphs inside of tables, blockquotes, lists, etc.

### Tabs
One use case for tabs is to align paragraphs according to a subject hierarchy to improve visual navigation.  For example:

**#1.  Topic** 
Introduction blah blah

&nbsp; **#1.1 Sub topic**
&nbsp; Introduction blah blah
&nbsp;
&nbsp; Another paragraph

**#2.  Another Topic**  
&nbsp;
|⚠️ **Funny story**:  I originally used stacked blockquote markers ``>>>`` to create nested ``<blockquote>`` elements, as if they were tabs.  That was before I learned what a semantic nightmare that caused for accessibility.  The ability to stack blockquotes has been removed from the markdown interpreter in favor of tabs.  **Never use a blockquote just to indent a paragraph**.|
|-|

&nbsp;
For me, another common need for a tab has been when I have a very long list item that absolutely requires a line break, and continuation at the same indentation level.

*For example*

Things to do on Mars:
* Wish you were back on earth --- Once you move to mars you will wonder why we didn't just fix things on a planet that is already habitable.
&nbsp; ==Instead we decided to ruin the planet and run to a new one.  I realise now that it was all just a scam.==
* Die --- Your misery will most likely be brief.

Without using a tab, the second line of the first bullet would be at the left margin of the page.  
&nbsp;
|**Accessibility concern**: While tabs can visually line up a paragraph with a list, semantically it may break the list up into multiple lists.  A screen reader may inform the visiter of the wrong number of list items|
|-|


Example syntax
    &nbsp; To indent a whole paragraph simply start a line with **"\&nbsp; "**, that is the html code for "no break space" followed by a regular space bar key.  To quickly insert the "\&nbsp;" code press ``CTRL-SPACE`` on your keyboard while in the editor.  Then to make a tab, add a space after that.

    &nbsp; &nbsp; Add the sequence multiple times to tab over further.


&nbsp; To indent a whole paragraph simply start a line with **"\&nbsp; "**, that is the html code for "no break space" followed by a regular space bar key.  To quickly insert the "\&nbsp;" code press ``CTRL-SPACE`` on your keyboard while in the editor.  Then to make a tab, add a space after that.

&nbsp; &nbsp; Add the sequence multiple times to tab over further.


## Footnotes
---
Footnotes appear at the bottom of the page, but you can fill out their content anywhere on the page.
&nbsp;
```

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    ```python
    print("You can even put code in a footnote")
    print("But why though?")
    ```

    Add as many paragraphs as you like.
```

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    ```python
    print("You can even put code in a footnote")
    print("But why though?")
    ```

    Add as many paragraphs as you like.&nbsp;
