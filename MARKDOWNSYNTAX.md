# **MARKDOWN SYNTAX**

It is important to note that there is a slight difference between this Markdown and common Markdown, as it allows for the definition of meta-information such as author, language, voice, etc. within an HTML comment at the beginning of every document. The document will describe all of these elements in more detail in the "Macros" section. All of these macros start with a single word, followed by a colon. If more space is required, such as for "comment:" or "link:", multiple lines can be used, with every following line starting with an indentation.

![image](images/markdown.png) <!-- style="height:200px;width:250px;"-->

**1.** **`Headers:`** You can create a heading by using one to six hash symbols (#) followed by a space and the heading text.

**Example:** 

```
# Heading 1
## Heading 2
### Heading 3
```

**2.** **`Emphasis:`** You can make text bold or italic by using asterisks (*) or underscores (_) before and after the text. 

**Example:** 

```
*This is italic*
**This is bold**
***This is bold and italic***
```

**3.** **`Lists:`** You can create ordered and unordered lists by using numbers followed by a period (for ordered lists) or hyphens, asterisks, or plus signs (for unordered lists) followed by a space.

**Example:**  

```
Ordered list:
1. Item 1
2. Item 2
3. Item 3

Unordered list:
- Item 1
- Item 2
- Item 3
```

**4.** **`Links:`** You can create an inline link by wrapping link text in brackets [ ], and then wrapping the URL in parentheses ( ). 

**Example:** 

`[Google](http://google.com)`.


**5.** **`Images:`** Similar to links, but add an exclamation mark (!) before the brackets.

**Example:** 

`![Image](image.jpg)`

**6.** **`Code:`** You can indicate inline code by wrapping it in backticks (`), and you can create code blocks by wrapping the code in triple backticks (```).

**Example:** 

`code` or ````python```` to create a python code block.

**7.** **`Blockquotes:`** You can indicate blockquotes with a > followed by the quote text.

**Example:** 

`>` This is a blockquote.

**8.** **`Horizontal lines:`** Use the ---, ___, or *** syntax to create a horizontal line.

**9.** **`Paragraphs:`** Paragraphs in Markdown are just one or more lines of consecutive text, followed by one or more blank lines.

**Example:**

```
This is a paragraph.

This is another paragraph.
```

![image](images/metainformation.gif)


## **STUCTURING**

1. **Markdown Structure:** A course in LiaScript is structured like any other Markdown document, using hash-tags (#) to denote hierarchy. The number of hash-tags determines the level of hierarchy for each section.

2. **Parsing Approach**: Unlike most Markdown parsers, LiaScript uses a two-step approach:

    - **`Parsing Sections:`** Firstly, LiaScript parses the sections of the document, identifying their structure and metadata.

    - **`Content Parsing:`** Secondly, the actual content of each section is parsed. However, this parsing only occurs if the section is being displayed to the user. This helps optimize performance, as parsing content can be time-consuming.

3. **Caching:** Once a section's content has been parsed for the first time, the resulting view is stored in a local cache. Subsequent requests to view the same section retrieve the cached content instead of parsing it again, improving the user experience by reducing processing time.

### **SEMANTIC CORRECT HTML**

Semantic HTML is the use of HTML elements that accurately describe the content of a webpage, rather than just defining its presentation or look. This makes it easier for search engines to understand the content of a page, and for screen readers to interpret the content for visually impaired users.

**1.** **`<header>:`** Defines a header section of a document or a section.

**Example:**

```
<header>
  <h1>Welcome to My Website</h1>
  <nav>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>
```

**2.** **`<nav>:`** Defines a section of a document that contains navigation links.

**Example:**

```
<nav>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

**3.** **`<main>:`** Defines the main content of a document.

**Example:**

```
<main>
<main>
  <h1>About Us</h1>
  <p>We are a company that specializes in web development and design.</p>
</main>
```

**4.** **`<section>:`** Defines a section of a document, such as a chapter or a tab.

**Example:**

```
<section>
  <h2>Our Services</h2>
  <p>We offer a variety of web development and design services.</p>
</section>
```

**5.** **`<article>:`** Defines an independent, self-contained content.

**Example:**

```
<article>
  <h3>Web Development</h3>
  <p>We specialize in creating custom websites using the latest technologies.</p>
</article>
```

**6.** **`<aside>:`** Defines a section of a document that is related to the main content, but not essential.

**Example:**

```
<aside>
  <h3>Related Articles</h3>
  <ul>
    <li><a href="#article1">Article 1</a></li>
    <li><a href="#article2">Article 2</a></li>
  </ul>
</aside>
```

**7.** **`<footer>:`** Defines a footer section of a document or a section.

**Example:**

```
<footer>
  <p>Copyright © 2023 My Website</p>
</footer>
```

**8.** **`<figure>:`** Defines a self-contained content, like an image, a diagram, or a code snippet.

**Example:**

```
<figure>
  <img src="image.jpg" alt="An image">
  <figcaption>An image caption</figcaption>
</figure>
```

**9.** **`<details>:`** Defines additional detailsthat the user can view or hide.

**Example:**

```
<details>
  <summary>More Information</summary>
  <p>This is some additional information that the user can view or hide.</p>
</details>
```

### **SUB-TITLES** 

Sub-titles in Markdown are created using the ## or ### symbols. The number of # symbols used corresponds to the heading level. 

**Example:**

```
#  This is a first-level heading
## This is a second-level heading
### This is a third-level heading
#### This is a four-level heading
##### This is a five-level heading
###### This is a six-level heading
```

## **CONTENT BLOCKS **

Content blocks in Markdown are used to organize and format text, images, and other elements. They can be created using various Markdown syntax elements such as headers, lists, blockquotes, and code blocks.

**Example:**

```python
# Heading 1

This is a paragraph of text.

## Heading 2

- List item 1
- List item 2

> This is a blockquote.

# This is a code block
print("Hello, world!")
```

## **TEXT-FORMATTING **

Text-formatting in Markdown is used to change the appearance of text. This can include making text bold, italic, or strikethrough, as well as adding links, images, and other elements.

`*italic*` → *italic*

`_also italic_ `→ _also italic_

`**bold**` → **bold**

`__also bold__ `→ __also bold__

`***bold and italic ***` → ***bold and italic ***

`___also bold and italic___` → ___also bold and italic___

`~strike~` → ~strike~

We define some additions to common Markdown, such as underline and superscript, which can be defined with the following syntax:


`~~underline~~` → ~~underline~~

`~~~strike and underline~~~` → ~~~strike and underline~~~

`^superscript^` → ^superscript^

### **COMBINATIONS**

Combinations in Markdown refer to the use of multiple formatting elements in a single block of text. This can include bold and italic text, links and images, and other combinations.

**1.** **`Headers with Lists:`**

```
## Header 2
    - Item 1
    - Item 2
1. Subitem 1
2. Subitem 2
```

**2.** **`Text Emphasis within Lists:`**

```
- *Italic Text*
- **Bold Text**
- ***Bold and Italic***
```

**Output:**

- *Italic Text*
- **Bold Text**
- ***Bold and Italic***

**3.** **`Combining Headers with Emphasis:`**

```
### **Bold Header with Italic Text**
```

**Output:**

**Bold Header with Italic Text**


**4.** **`Blockquotes with Lists:`**

```
> This is a quote
> - Item 1
> - Item 2
```

**Output:**

> This is a quote

> - Item 1

> - Item 2

**5.** **`Headers with Inline Code:`**

```
   ## `Inline Code Header`
```

**6.** **`Code Blocks within Lists:`**


```
- Some text
```

**Output:**

- Some text



**7.** **`Combining Tables with Headers:`**

```
| Header 1 | Header 2 |
| -------- | -------- |
| Content 1| Content 2|
```

**Output:**

| Header 1 | Header 2 |
| -------- | -------- |
| Content 1| Content 2|


### **ESCAPE CHARACTERS**

Escape characters in Markdown are used to display characters that would otherwise be interpreted as formatting or special characters by Markdown rendering engines. These characters are preceded by a backslash `\ `to indicate that they should be treated as regular characters.

**Example:**

Suppose you want to display an asterisk `*` without it being interpreted as the start of italic text. You would use the escape character `\` before the asterisk like this: `\*`.

**OUTPUT**

To display an asterisk \*, use an escape character: \\\*


## **SYMBOLS & UNICODE**

**`Arrows:`**

1. `-> →:` This represents a right arrow.

    **Example:** 

    -> becomes →.

2. `--> ⟶:` This represents a longer right arrow.

    **Example:**

    --> becomes ⟶.

3. `<-- ⟵:` This represents a left arrow.

    **Example:**

    <-- becomes ⟵.

4. `<--> ⟷:` This represents a bidirectional arrow.

    **Example:**

    <--> becomes ⟷.

5. `==> ⟹:` This represents a right arrow with a double equal sign, indicating implication.

    **Example:**

    ==> becomes ⟹.

6. `<== ⟸:` This represents a left arrow with a double equal sign, indicating reverse implication.

    **Example:**

    <== becomes ⟸.

7. `<==> ⟺:` This represents a bidirectional arrow with a double equal sign, indicating equivalence.

    **Example:**

    <==> becomes ⟺.

`Smileys:`

1. `:-) 🙂:` This represents a smiling face with eyes and a smiling mouth.

    **Example:** 

    :-) becomes 🙂.

2. `;-) 😉:` This represents a winking face with eyes and a winking mouth.

    **Example:** 

    ;-) becomes 😉.

3. `:-D 😀:` This represents a smiling face with eyes and an open mouth showing teeth.

    **Example:**

    :-D becomes 😀.

4. `:-O 😮:` This represents a face with wide open eyes and mouth, indicating surprise.

    **Example:**

    :-O becomes 😮.

5. `:-( 🙁:` This represents a frowning face with eyes and a downturned mouth.

    **Example:**

    :-( becomes 🙁.

6. `:-| 😐:` This represents a neutral face with straight-line eyes and a straight mouth.

    **Example:**

    :-| becomes 😐.

7. `:-/ 😕:` This represents a face with a perplexed expression, showing a combination of confusion and dissatisfaction.

    **Example:**

    :-/ becomes 😕.

8. `:-P 😛:` This represents a face with tongue sticking out, indicating jest or playfulness.

    **Example:**

    :-P becomes 😛.

9. `:-* 😗:` This represents a face blowing a kiss.

    **Example:**

    :-* becomes 😗.

10. `:') 😂:` This represents a face with closed eyes and tears of joy, indicating laughter.

    **Example:** 

    :') becomes 😂.

11. `:'( 😢:` This represents a face with closed eyes and tears, indicating sadness.

    **Example:** 

    :'( becomes 😢.

## **REFERENCES**

1. [**SIMPLE LINKS**](#SIMPLE-LINKS)
2. [**IMAGES**](#IMAGES)
3. [**AUDIO**](#AUDIO)
4. [**MOVIES**](#MOVIES)
5. [**AUDIO**](#AUDIO)
6. [**SO WHAT IS LEFT??**](#SO-WHAT-IS-LEFT??)

### **SIMPLE LINKS**

In Markdown, simple links are created using square brackets `[ ]` to define the link text and parentheses `( )` to provide the URL.

**`Syntax:`**

```python
[Link Text](URL)
```

- `**Link** Text:` The text you want to display for the link.
- `**URL:**` The destination URL that the link points to.


**`CODE`**

```
[YOUTUBE](https://www.youtube.com/@liascript4180/videos)
```

**Output:**

[YOUTUBE](https://www.youtube.com/@liascript4180/videos)


#### **PREVIEW-LIA**

This Markdown syntax creates a link titled "preview-lia" that, when clicked, will load the remote course document specified by the raw URL provided (in this case, the LiaScript documentation from GitHub). The meta-information such as title, version, comment, logo, email, and tags will be parsed from the main HTML-comment at the top of the document.

To use the advanced preview link in LiaScript, you would structure it like this:

```python
[preview-lia](https://raw.githubusercontent.com/LiaScript/docs/master/README.md)
```

**Output:**

[preview-lia](https://raw.githubusercontent.com/LiaScript/docs/master/README.md)

#### QR-CODES

Provides a brief explanation of what QR codes are.

**Example:**

Shows how to include a QR code image using Markdown syntax. Replace the URL with the desired data you want to encode in the QR code.

```python
## QR Codes

A QR code (Quick Response code) is a type of matrix barcode that contains information encoded within it. It can be scanned using a QR code reader, usually found on smartphones.

### Definition

A QR code consists of black squares arranged on a white square grid. The information encoded can be text, URL, or other data types.

### Example

Below is an example of a QR code containing the URL to OpenAI's website:

![QR Code](https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://raw.githubusercontent.com/LiaScript/docs/master/README.md)
```

**OUTPUT:**

Scan the QR code below with a QR code reader to visit OpenAI's website:

![QR Code](https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://raw.githubusercontent.com/LiaScript/docs/master/README.md)

#### EMAIL & TELEPHONE

eMail and Telephone links are two additional link types that can be used within the <a> tag, but LiaScript supports them natively.

**Example:**


`EMAIL:`

```
[Write me a Mail](mailto:LiaScript@web.de) ⟶ Write me a Mail

[LiaScript\@web.de](mailto:LiaScript@web.de) ⟶ LiaScript@web.de
```

`TELEPHONE:`

```
[Call me](tel:+49-12345-67890) ⟶ Call me

[+49-12345-67890](tel:+49-12345-67882) ⟶ +49-12345-67882
```

**Output:**

`EMAIL:`

[Write me a Mail](mailto:tamaraiselvan98@gmail.com) ⟶ Write me a Mail

[LiaScript\@web.de](mailto:LiaScript@web.de) ⟶ LiaScript@web.de


`TELEPHONE:`

[Call me](tel:+919688814221) ⟶ Call me

[+919688814221](tel:+919688814221) ⟶ 9688814221

### IMAGES

Images in Markdown are defined using the syntax `![alt-text](url "optional title")`. The `alt-text` is the alternative text for the image, which is displayed if the image cannot be loaded. The `url` is the location of the image, which can be either relative to the Markdown document or an absolute URL. The `optional title` is a title attribute for the image, which is displayed as a tooltip when the user hovers over the image..

**`Example:`**

```
Image-notation:![alt-text](url "optional title")

relative URL:![Beautiful Lenna](img/lenna.jpg)

Beautiful Lenna
absolute URL:![Annunciation of...](https://upload.wiki...jpg)

Annunciation of the brith of Christ
```

**Output:**

Image-notation:![alt-text](images/OIP.jpg"optional sub-title")

 2  relative URL:Beautiful Lenna

Beautiful Lenna absolute URL:Annunciation of...

URL:![Annunciation of...](images/OIP.jpg)

#### GALLERIES

To interpret a paragraph full of images as a gallery, you would essentially present the images in a visually appealing format that allows the viewer to interact with each image individually.

When encountering a paragraph full of images, presenting them as a gallery provides the most engaging and user-friendly experience. In a gallery layout, each image is displayed as a thumbnail or preview, allowing the viewer to click on each image for a closer inspection.

`Features of a Gallery:`

- **Clickable Images:** Each image in the gallery is clickable, allowing the viewer to interact with it.

- **Zooming Feature:** Upon clicking on an image, a zooming feature enables the viewer to inspect the image in detail.

- **Navigation Controls:** Navigation controls such as arrows or pagination may be provided to allow easy browsing through the images.

- **Responsive Design:** The gallery layout should be responsive, ensuring that it looks good and functions well across various devices and screen sizes.

**`Example:`**

In the gallery below, you can click on each image to inspect it closely with the zooming feature:

![Image 1](images/pexels-eberhard-grossgasteiger-1367192.jpg)
![Image 2](images/pexels-eberhard-grossgasteiger-691668.jpg)
![Image 3](images/pexels-eberhardgross-1366919.jpg)
![Image 4](images/pexels-simon-berger-1183099.jpg)

This gallery layout enhances the viewer's experience by providing easy access to each image while allowing for closer inspection when desired.

### AUDIO

If an exclamation mark indicates visual content, why not using a question mark to indicate auditive content. (From our perspective it resembles an ear.) Everything is similar to images and the URLs can be either relative or absolute.

**`Syntax:`**

```
?[a horse](https://www.w3schools.com/html/horse.mp3 "hear a horse")
```

**`Example:`**

?[a horse](https://www.w3schools.com/html/horse.mp3 "hear a horse")

Additionally, you can also directly reference music from the SoundCloud website or from Music.YouTube. The associated song will be automatically embedded for you.

Syntax: 

```
?[soundcloud](https://soundcloud.com/glennmorrison/beethoven-moonlight-sonata)
```

**`Example:`**

?[soundcloud](https://soundcloud.com/glennmorrison/beethoven-moonlight-sonata)

### MOVIES

Images are marked with a starting exclamation mark before the link, audio by a
starting question mark and movies are made of images and sound, that is why you
combine both marks `!?`. Defining resources this way shows at least the links
correctly in other Markdown parsers or on GitHub. There is baked-in support for
[YouTube](https://YouTube.com), [Vimeo](https://Vimeo.com),
[PeerTube](https://peertube.tv), [DailyMotion](https://www.dailymotion.com) and
[TeacherTube](https://TeacherTube.com), which means that you only have to
include the link and the resource will be embedded appropriately.

**Movie-notation: `!?[alt-text](movie-url)`**

- **`YouTube:`** `!?[The Future of Programming](https://www.youtube.com/watch?v=PGulF4H6iC0)`

  !?[The Future of Programming](https://www.youtube.com/watch?v=PGulF4H6iC0)

- **`relative path:`** `!?[Something about math](images/WhatsApp%20Video%202024-04-18%20at%2018.44.36_dc658e80.mp4)`

!?[Something about math](images/WhatsApp%20Video%202024-04-18%20at%2018.44.36_dc658e80.mp4)

- > # List of supported Video Platforms
  >
  > * [DailyMotion](https://www.dailymotion.com)
  > * [PeerTube](https://peertube.tv)
  > * [TeacherTube](https://TeacherTube.com)
  > * [Video TU-Freiberg](https://video.tu-freiberg.de)
  > * [Vimeo](https://Vimeo.com)
  > * [YouTube](https://YouTube.com)

### SO WHAT IS LEFT??

If it is something else that you want to embed something else from another website, then you should try out the link syntax with two starting question marks. This means, LiaScript will try to use the [oEmbed](https://oembed.com) service, which is offered by a couple of websites. If this succeeds, this will embed only a specific part. If it fails, then LiaScript will at least try to embed the website via an `iframe`.

**`Examples:`**

* [SketchFab](https://sketchfab.com): `??[ear model](https://www.youtube.com/watch?v=PGulF4H6iC0)`

  ??[ear model](https://www.youtube.com/watch?v=PGulF4H6iC0)

* [StoryMaps](https://storymaps.arcgis.com): `??[presentation](https://storymaps.arcgis.com/stories/583f8b48a857442cb8d27411c93a9664)`

  ??[presentation](https://storymaps.arcgis.com/stories/583f8b48a857442cb8d27411c93a9664)

* [CirquitJS](https://www.falstad.com/circuit): `  ??[Simulation: Noninverting Amplifier](https://www.falstad.com/circuit/circuitjs.html?startCircuit=amp-noninvert.txt)`

  ??[Simulation: Noninverting Amplifier](https://www.falstad.com/circuit/circuitjs.html?startCircuit=amp-noninvert.txt)

## REFERENCES KEY

if to learn click this link button 👇

1. [Reference link](https://www.youtube.com/@liascript4180/videos)

2. [Reference link](https://github.com/LiaScript/docs)


### LIASCRIPT LIVE EDITER

1. [LIASCRIPT LIVE link](https://liascript.github.io/LiveEditor/)
