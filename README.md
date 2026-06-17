  Thanks to the [markdown-it](https://github.com/markdown-it/markdown-it) for Node and [Marko](https://pypi.org/project/marko/) for Python this knowledge base interprets standard Markdown if you wish to use it.  Markdown allows you to organize your thoughts by adding emphasis to phrases, adding heading, "links", code segments and even images.  

  The goal is to use **Markdown** in this **C**ontent **M**anagement **S**ystem such that your documents are portable --- can be read in Markdown viewers, or copy and pasted from Markdown documents to instantly render nicely in HTML.  It uses formatting that is interpreted aesthetically in HTML, while keeping the source valid and compatible with other markdown interpreters.  It accomplishes this through syntax that has natural fallbacks when viewed in standard Markdown renders.  

  This article is just a quick start reference guide.  I recommend reading through this one time, but don't worry about trying to memorize everything.  Just get a good idea of what kind of formatting and content you can use in this application, so that when you need it you know what you can look up.  The syntax is so simply, you will automatically memorize it without trying after looking things up a few times.

There is also a great Markdown tutorial and reference at **[Commonmark.org](https://commonmark.org/help/tutorial)**

---

## Text features
Adding simple text features like headings, bold, italics, etc is extremely simple.  

### Headings
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

You'll want to use **heading 2** ``##`` for major sections, and **heading 3** ``###`` for smaller paragraph groupings or headings.  **Heading 4** is available if you need a sub-sub section (for semantic readability) but is basically just a regular bold header.
&nbsp;

### There can only be one
:::float-right
|The "**h**" in ``<h1>`` must stand for **h**ighlander, because there can only be one|
|-| 
:::
<h*n*> tags have a semantic meaning in HTML.  They let the browser know that it is a certain type of heading.  ``<h1>`` tags are for the main title of the page, and there should only be one.  This CMS disables the use of *real* ``<h1>`` tags in articles, because the **one and only** ``<h1>`` tag will be used by the article title.  For Markdown document compatibility ``#`` lines will still be styled as the largest text in an article, so you can still copy and paste your markdown documents into an article without an issue.  However, to maintain ADA compliance they will actually be rendered as ``<h2>`` tags in the html code.

It's much better to just avoid the use of ``#`` markers for subtitles in favor of ``##`` markers.  Semantically the ``##`` lets browsers know that the line is an important subtitle, but not the main title for the page.  These semantics are very important for keyboard navigation, SEO, accessibility, and ADA compliance.


#### Don't confuse the navigation

Notice how the "**Heading 1**" (``#``) above is represented in the Table of Contents as a sibling to "**Heading 2**" (``##``) and not as a parent.  Both headings should be nested within the "*Text Features*" heading because that's the content heading that they are both under, but they are not because "**Heading 1**"  breaks the hierarchy.   which makes navigation more confusing.  That's exactly how it behaves in a screen reader as well.  So, if you must use an ``<h1>`` tag, try to do so only once, and at the top of the page as a subtitle.  That will minimize confusion.

&nbsp;
:::center

    ##c Centered Headings
:::

:::center

## Centered Headings
:::

Usually headings are left justified, but maybe once in a while you want a heading to be centered for some reason.  This CMS also includes non-standard markers for placing centered headers.  Just add a "c" after the hash marks to turn a standard heading into a centered heading.  

==Be aware== that these will not work in any other Markdown renderer.  An alternative is to use positioning fences instead.


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

You can also use a media item as a link by nesting the media syntax inside of the square brackets of the link marker.  This can really come in handy when you want to display a very large image that is too big for the article window.  Images are automatically scaled down to fit the window.  When you need to show a very big image you can display a smaller version of it, and link it to a larger version. 

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
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|
```
:::
&nbsp;
Example Table Caption
|Category 1|Category 2|Category 3|
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|

Tables can be used to show data in a neat and tidy format.  
To create a table use pipes ( ``|`` under the backspace key ) to separate cells as shown in the examples.  The top row must contain the labels, and the second row must contain a row model that shows how many columns each row will have, depicted with pipes and dashes, and it should match the header row.  There must be the same number of columns in each row, but they do not have to line up.
&nbsp;

Notice that you can place an optional caption in a table by immediately preceding it with a line of text.  A brief but descriptive table caption is very important for accessibility.



## Figures: combining tables and media
---

HTML has a ``<figure>`` tag for displaying different types of media with or without a caption.  You can mimic this feature with markdown by inserting media into tables.  Doing so will give you something sort of like an HTML figure.

Fortunately this CMS can take those approximate figures and render them as real figures, while your markdown stays completely valid so it still works in other interpreters.  

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

### Quote
---

Create a quote box using a table with two cells.  Put the quote in the top cell, and the citation in the bottom cell.  The citation in the bottom cell is used as the accessible name.


```markdown
|***If debugging is the process of removing<br>software bugs, then programming must<br>be the process of putting them in***|
|-|
|- Edsger Dijkstra|
```
&nbsp; 
|***If debugging is the process of removing<br>software bugs, then programming must<br>be the process of putting them in***|
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
|Image from cleanpng.com<br>by [Taishna](https://.../@taishna.html)|
```
&nbsp;

|![battlecat](https://cerebrokb.akindeji.net/static/smallcat.png)|
|-|
|Image from cleanpng.com<br>by [Taishna](https://www.cleanpng.com/users/@taishna.html)|

&nbsp;


## Positioning media
---
> *Example floated chart*
```
:::float-right
|Category 1|Category 2|Category 3|
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|
:::
```
&nbsp;

:::float-right
|Category 1|Category 2|Category 3|
|-|-|-|
|value 1|value 2|value 3|
|value 1a|value 2a|value3a|
:::

In this CMS application, media items (other than images) are centered by default, but you can float them to the left by prepending a blockquote mark ``>`` in front of it.  This allows the text after it to float to the right.  This allows you to place a media item right next to a paragraph or explanation about it.


> *Example right floated chart*
```
>> |Category 1|Category 2|Category 3|
>> |----------|----------|----------|
>> |value 1   |value 2   |value 3   |
>> |value 1a  |value 2a  |value3a   |
```


>>|Category 1|Category 2|Category 3|
>>|-|-|-|
>>|value 1|value 2|value 3|
>>|value 1a|value 2a|value3a|

If you place more than one blockquote symbol before a media item it will float to the right instead.

&nbsp;
|**Note**: Floated tables require the blockquote symbols before each line|
|-|

&nbsp;


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

Another feature of **fenced code blocks** in this application is the "**copy to clipboard**" button that appears when the mouse is over the block.  This enables readers to easily copy the code from the document.

Notice the **optional caption** "Creating variables" was created by writing a line of text directly over the fenced code.  Brief and descriptive captions should always be used to help make the document highly accessible.


### Indented Code Blocks

In standard Markdown **indented code blocks** are created by starting a line with four spaces.  A series of four-space-indented lines will all share the same code block

Example syntax
    Example syntax
        This indented code block shows how
        to create an indented code block.

Notice that the caption is written immediately above the first indented line.  Using a brief descriptive caption is highly recommended.

**They are great to use for:**
* **Examples/Scenarios** --- A hypothetical situation or a concrete example to illustrate a concept.
* Displaying preformatted text --- When it is not code and you don't want a "clickable button, copy to clipboard" button announcement breaking up the flow for screen readers.


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


### In-line code segments

Sometimes you don't need a whole block to display an example, but you still want to make it stand out.  We use just two back-ticks `` ` `` for that, instead of three.  The displayed text can be in line with the rest of the text if you wish, or you can put it on its own line.  For instance to display just a variable declaration, you could use the following.

Inline code syntax example
    Add ``const PI = Math.PI;``

Add ``const PI = Math.PI;``


You can display command line interface (CLI) commands by starting the inline code with a prompt symbol.  For instance to display the Linux command to delete a file, you would type the following.

Ex.
```
Enter ``$ rm filename`` to delete the file.
```

>Enter ``$ rm filename`` to delete the file. 

Use `#` for root shell commands, and `C:\>` for windows CLI commands.  

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

|⚠️**Note**: Only the *checked* and *unchecked* markers are in the official markdown standard.  The ``- [-]`` marker for 'excluded' options was added specifically for this CMS, and will not work in other markdown interpreters.|
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
|==**Warning:**==  *This roman numeral marker is not standard markdown and will not work in other interpreters.  Only use it for articles specifically meant for this CMS.*|
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

    Add as many paragraphs as you like.
