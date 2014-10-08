---
title: Working with PDFs
layout: default
---

{:toc}

# Introduction to Portable Document Format

The Portable Document Format (or "PDF") is an excellent way to share documents. Documents consistently render across all devices -- from desktop computers to smart televisions -- in the exact manner which the publisher of the document intended. Unfortunately, the advantages which the PDF format gives to publishers of *documents* are mostly the same as the disadvantages which the PDF format gives to publishers of *data*.

## Some Background on PDFs

#### Pulling *data* out of PDF *documents* can be an arduous task.

PDF documents are essentially an image format. This is why they are so often used when scanning and displaying documents -- and what allows for documents to render consistently across devices. As such, text within a PDF is rendered in layers. When a document generating program renders a PDF what happens is that it compiles an image of the page. If there is text which is to be rendered that text is, depending on how the PDF was constructed, rendered as an additional layer underneath the image. While the PDF Reference does allow for numerous publishing particularities to render text appropriately, many programs -- particularly with regards to Form documents or scanned documents -- do not formulate their PDFs in such a manner. This is why when you select text from a PDF viewer there is sometimes an offset in the text that is selected and that which the human eye is seeing. More simply PDF viewers show you the image of the page but when you want to select text the PDF selects the background layer which contains the text if that is how the PDF was built.

Text which is encoded within a PDF document is encoded, usually, on a line by line basis where the lines are given X, Y coordinates as to the corners of the block of text (which can be a line, a sidebar, a table, or any other block of text). (More information as to how a PDF renders text can be found at the [PDF Reference](http://www.adobe.com/content/dam/Adobe/en/devnet/acrobat/pdfs/pdf_reference_1-7.pdf) -- in particular Chapter 5.) So rather than having text be associated semantically, tabular, or any other way in which structured data would normally be stored or presented, text is simply given an X, Y coordinate and a blob of text.

Indeed, these text blocks are not stored in any particular order within the PDF file itself. The exception is that text is delineated according to the pages of the document. The semi-random storing of text blocks within a PDF file is important because when a program is attempting to work with data or text which is contained within a PDF document, the program cannot necessarily rely on the order that the text is contained within the PDF document. Instead, the program must process an entire *page* of text (which is the base unit of a PDF document) and establish the order of the various text blocks within the page using the X, Y coordinates before the program will have a proper understanding of how the text is ordered on the page. In addition, because the base unit of a PDF document is a *page* of text, any programs seeking to work with the data within the document must also be able to address changes in pages and connect one page to another. While it is true that human brains are capable of processing chunks of information in page size bits, it adds unnecessary complexity for computers to process the information.

Another challenge which the PDF specification presents to programs which seek to process and use the information contained within a PDF document is that there is no inherent mechanism within the PDF Reference for semantically linking text together. For example, headers in HTML files (like the text blob above this text which contains the text, "Some Background on PDFs") are noted using an opening `<h2>` tag and a closing `</h2>` tag. In HTML and most text-based markup specifications, headers come in levels; the `h2` could be any number between 1 and 9, 2 is only chosen here as an example and means second level header. Header tags are extraordinarily helpful when processing text as they allow programs to understand that the `h2` is (a) nested underneath the preceding `h1` and (b) the text which follows until the next `h2` or `h1` tag is linked to this particular `h2`. PDF documents do not have such a semantic structuring. Whatever program one is using to make a PDF will simply output the `h2` as text which is somehow different in font, or size, or however the document designer has meant for it to be. The PDF Reference does include an ability to bookmark text and formulate a table of contents from this, but those features are additive layers rather than contained within the text layer itself.

Another downside to the manner in which PDF documents do not consistently render text in any particular order affects a user's ability to even copy and paste text from a PDF document into another program for citations or other purposes. If one has ever tried to copy and paste from a PDF one has seen this because when one pastes the text block into another program the end of the lines as rendered by the PDF original are almost always pasted in as new lines into the new program. Lawyers, academics, and others who work with PDF documents on a consistent basis have likely wasted, collectively, thousands of hours of simply backspacing out the new lines from a block of PDF text after pasting into word processors.

## Why is This Important

The above (albeit brief) overview is important to understand because PDF has become somewhat of a default standard for publication of *data*. This is particularly true in the legal field, but it is also true in other fields. This is suboptimal for a few reasons.

The main reason publishing information via PDF documents is suboptimal is that getting *information in context* out of PDF documents is difficult. Data alone is important, but data in context is even better. This is especially important when the data being communicated, published, or transmitted is not simply a raw data feed but instead is data of a more complex nature (e.g., legal data and other data which is highly context driven).

What can be frustrating to those within the open data, open law, and open government communities who consume such data feeds, is that the information is *usually* (but not always) built in context but much of that contextual data is lost when the information is rendered to a PDF.

For example, to process judicial opinions one must understand how to deal with footnotes. Any lawyer who has sent a judicial opinion to their ebook reader knows the pain that this causes. Footnotes within a PDF are a particular annoyance when trying to read an opinion on an ebook reader; while ebook formats contain a method for handling footnotes in a manner which is helpful to readers, when PDFs are converted to ebook reader formats the linkage of a footnote to its citating text are lost.

It is certainly not the makers of the ebook reader's responsibility to handle footnotes, because the computer programs used to change the PDF format of the judicial opinion to the ebook reader's format have no way to connect a blob of smaller text at the bottom of the page with (perhaps) a leading number offset just a small amount on the X axis as a footnote and to be able to link that back to a superscript number higher in the page. When the document was written, either in a free and open source word processor such as LibreOffice or in a paid and proprietary word processor such as Microsoft Word, that semantic linking of the text of the footnote to the footnote citation is maintained. When the document is rendered to PDF, however, the semantic linkage between the footnote and the citing text is lost.

The same reasoning applies to legislation, regulations, and many other sets of data which require context and semantics in order for machines to process them properly -- which would increase the flexibility in how entities and individuals consume that data.

## Authenticity of Publication

One of the largest reasons for why lawyers in particular publish documents in PDF format is because there is a perception that PDFs are more difficult to modify. This perception is not completely wrong. Neither is it completely correct. As with all digital formats, which are simply a collection of `1`'s and `0`'s PDF's *can* be changed. All one really needs to change a PDF format is some clever [GIMP](http://www.gimp.org/) or Photoshop skills. Even Adobe Acrobat PRO can allow one to change a PDF document. While it takes some work to change a PDF, PDF's should not be thought of as an immutable format; for example, to change a text based PDF one needs to change the image layer and the text layer, but this is not a difficult process. To combat such an ability to change the document, Adobe allows document publishers to "lock" PDFs. However, there are [numerous web sites](https://www.google.com/search?q=unlock+pdf&gws_rd=ssl) which allow users to "unlock" PDFs.

This begets the question as to whether using PDFs is the optimal way to ensure that the *information* they contain is authentic. The challenge which well intentioned individuals are trying to overcome is a laudable goal: ensuring the legitimacy of the information. Especially when it comes to governmental information it is a very productive use of time to provide a mechanism whereby consumers of information have some ability to rely on the information's authenticity.

However, many public agencies, in pursuit of this laudable goal, have locked themselves in to a suboptimal, expensive, proprietary format which, in truth, was developed to solve a different problem set. The problem set which PDF were meant to solve was to provide a consistently rendered document not to ensure the authenticity of the document's information. There are other methods of ensuring that the data one is publishing is accurate and complete which do not require expensive, proprietary vendor lock in.

One such inexpensive and non-proprietary method of ensuring the authenticity of a document is the Free and Open Source PGP (Pretty Good Privacy) system which is available for all major operating systems. Using PGP, document publishers are able to sign a document as being authentic. This electronic "signature" performs a cryptographically secure function on the `0`s and `1`s of any file to formulate a unique "fingerprint" of these bits. If any single bit of all of the bits is changed then the fingerprint of the file will change. What a PGP signature does is it adds an authentic electronic signature to verify a particular fingerprints authenticity. PGP has a very simple mechanism for not only signing a file, but also for verifying a signature. This method of certifying a document's authenticity is not only free and open source, but also **significantly** safer than only relying on even a "locked" PDF.

# Working with PDFs

Despite the distinct disadvantages which PDFs have as a format for publishing data, many public agencies still publish data in PDF formats. The remainder of this page will discuss the various methods for extracting data from published PDFs.

There are two major "flavors" of PDF documents: those that have a text layer and those which do not. If you are unsure whether the set of PDFs you are seeking to work with has a text layer or does not, try opening the PDF in a PDF viewer and selecting the text with your mouse or keyboard. If you are able to select text with your mouse or keyboard then the PDF *does have a text layer*, if you are not able to select text with your mouse or keyboard or if you can only select an entire page then the PDF *does not have a text layer*.

As with any data-driven task, one of the most important aspects of extracting data from PDFs is to have a plan for how one will handle the task. The below sections cover some of the different aspects which may be included in the overall plan. Generally speaking, if the document one is working with does not have a text layer then there will be three main steps one must take to derive data from the PDF source:

1. Recognize the text on the document.
2. Ensure the text layer is "cleaned" of noise.
3. Process the text into the required data format.

When one is dealing with documents which already have a text layer to them, the first two steps would generally be ignored. The three step process outlined above is general in nature and is meant only to be illustrative. Each data derivation task will require its own plan for how to transform the PDF documents into machine usable data.

## Step 1 -- Recognize the Document's Text

Optical Character Recognition, or OCR, is the task of processing image data and extracting useful text out of the image. It is sort of like machines "reading" a document. In actuality what is happening is that the machine is analyzing the pixels on the screen and matching the boundaries of differences in the pixel colors against patterns which have been preprogrammed into the OCR software.

### Optical Character Recognition -- Background

Digital images, for those who are not aware, are a set of very small squares (also called pixels) which have a specific color. Below is an example of the English language character "e" which has been zoomed in using GIMP.

![pixelated letter e](/{{ site.images_dir }}/pdf/letter-e.png)

In the image above, viewers are mostly likely able to recognize the pattern of an English language "e" as well as the pixels (or squares) of colors. In order to simplify the example, we built the image as black text on a white background. However, the viewer can see that some of the pixels are shades of colors in between pure black and pure white. This is what allows fonts to render smooth curves and generally appear "nice" to the human eye.

In the next image, which is the exact same image only with the English language "e" written in a different font, you can see a greater amount of pixels which are neither pure black nor pure white in color.

![pixelated letter e](/{{ site.images_dir }}/pdf/letter-e-redux.png)

As the above two images demonstrate, when "looking" at pixels and trying to derive patterns from those pixels there is a great difference in how fonts are rendered as images. This is important because as explained above, what an OCR program is attempting to do is to match the pixels of an image against various patterns that the OCR software knows about.

The patterns which a piece of OCR software understands are exceedingly important to the success of the software as they provide the basis which the software is using to match patterns of the image against. There is a process of "training" OCR software which can be used to improve the output of an OCR rendering process. This training process has been leveraged by the CAPTCHA and ReCPATCHA program to improve the scanning reliability of text while also providing the main function these were designed for -- proving that the node entering data into a form is actually a human and not a robot. A good place to start if one is interested in learning more about this process is [this TED talk](http://www.ted.com/talks/luis_von_ahn_massive_scale_online_collaboration).

OCR software is exceedingly complex for a number of reasons. Differences in how images are taken, differences in fonts and how those are rendered as pixels in a digital image, differences in language patterns, and "noise" within the image all contribute to the challenges which OCR software developers face.

For this reason, perhaps among others, the state of free and open source OCR software is not currently optimal. [Here is a Wikipedia comparison of OCR software](http://en.wikipedia.org/wiki/Comparison_of_optical_character_recognition_software).  Although it is only one test, this blog post is a demonstrator of [the differences in OCR software](http://www.splitbrain.org/blog/2010-06/15-linux_ocr_software_comparison). At this time, proprietary OCR software drastically outperforms free and open source OCR software and as such could be worth a public agency's investment depending on the amount and type of OCR jobs the public agency is needing to perform.

### Optical Character Recognition -- Top Tips

Working with OCR software can be a challenge, but it is often more efficient than typing large amounts of pages. As stated above, there are numerous variables which contribute to the success of an OCR rendering process; there are, however, two main variables which users can somewhat control: the "noise" on the page which a OCR software is forced to analyze, and the "area" of the page which the OCR software is forced to analyze.

Noise to an OCR rendering process is pixels on the digital image which render closer to the text color than to the background color but which are not actually text. An example of this is when there is a dot on a page (perhaps from a pen marking or any other process) which then the OCR software may render as a backtick ("`").

Noise also works in the reverse, pixels which are closer to the background color than to the text color but actually should be rendering as text. An example of this is when there may be a lighter few pixels in the midst of an "l" character so that the OCR software will "think" that the closest pattern is actually an "i" character instead of the "l".

Below are some examples of noise and how that renders after the OCR process.

![noise example 1](/{{ site.images_dir }}/pdf/noise1.png)

In this example, you can see how all of the background pixels have a similar color to the pixels which define the "text" of this image. You can also see how the middle word (reimbursement) is not at all clear. In particular the "s" in the middle of the word has been smudged so that there is no defined pattern which an OCR software can utilize.

![noise example 2](/{{ site.images_dir }}/pdf/noise2.png)

In this example, you can see even more noise. The green is used by the OCR software which was used for this example to mean "I will recognize text within this space". When the OCR software used for this example began it did a pre-process of the text and attempted to define where text was. As any human can see there is no reasonable text within this green area; however the computers don't have such advanced pattern recognition skills as humans do so it only sees that there appear to be dark pixels against a white background so there is likely text to recognize within this block.

![noise example 3](/{{ site.images_dir }}/pdf/noise3.png)

In this example, you can see some of the results which noise produces. This image was produced after the OCR process was finished and the output was opened in a spreadsheet program the noise from the example produces quite a bit of unusable information which will get in the way of accomplishing a clean OCR of the document.

**TOP TIP TO REDUCE NOISE**: *get good scans*. The best way to reduce noise in a digital image is a good scan of the document. Over the past two decades scanner technology has increased dramatically. So if the documents one is working with are older documents, it may be worth the time to rescan the document if it is an old one. However, if the only hard copy of the document which is available is an old photocopy with lots of noise on it, then there is little one can do about such a situation.

The second variable which users of OCR programs can utilize to improve the accuracy of an OCR process is to minimize the OCR'ed area. This will greatly reduce the amount of noise which is captured during the OCR process. Each OCR program has its own way of defining the area of the image in which it should look for text, so users will have to consult their own particular OCR software to determine the manner in which it operates.

![area example before](/{{ site.images_dir }}/pdf/area1.png)

As mentioned above, in the OCR software used for this example the area which the OCR software will look in to find text is marked in green by the software when it loads image files.

![area example after](/{{ site.images_dir }}/pdf/area2.png)

After modification, there is much less area for the OCR software to look in.

**TOP TIP TO INCREASE ACCURACY**: *minimize the OCR-ed area*. Minimizing the OCR-ed area is not available with all OCR software. In some OCR software suites, one can select via a graphical user interface, the area which the OCR software will analyze. The benefit of closely matching the area of the image which the OCR software will analyze to that human determined area of text on the page is that it will minimize the amount of noise a bad scan will output, as noise which is not within text blocks will not be analyzed. The screenshots below demonstrate how to do this in one OCR software.

### Optical Character Recognition -- Exporting

Many OCR software suites are capable of exporting to different formats. The Wikipedia article linked to above comparing OCR software suites has a column for exporting formats. This is important mostly because how one approaches the general Step 2 of cleaning the noise from the text will depend on the type of data and how one is attempting to approach cleaning the noise from the text.

## Step 2 -- Clean the Text Layer

In general the second step in processing PDF documents into machine usable data is to clean the text which has been recognized by the OCR software. This step can be a grind because in general it requires human judgment to determine what is noise and what is not. Human judgment need not *always* be required, there are methods for machine cleaning of OCR analyzed documents which shall be covered below; however, human judgment is currently the safest method of analyzing documents. There is a middle ground between manual (human) cleaning and automatic (machine) cleaning of the text layer which is to perform an initial sweep of the text layer manually and then finalize the cleaning process via an automated process.

### Manual Cleaning of the Text Layer

The goal of this step is to get the text layer into a state where the machines can then churn through the text layer and turn it into a usable format. As stated above, manual cleaning, while slow, is currently the safest way to process data derived from PDF documents. One must be forewarned, this is slow and arduous work. There is a reason why people call this work, "the depths of the OCR mines" or "eyeball bleeding work". However, at times it is necessary.

When manually cleaning the text rendered by OCR software, the strategy one adopts will usually depend on the type of document being analyzed. If one is parsing a document which contains tabular data, then a spreadsheet may be the most relevant piece of software to utilize for the cleaning step. If one is parsing a document which contains text blocks, then a good text editor with regular expression support is likely to be the most relevant piece of software to utilize for the cleaning step. In general, word processors are usually not useful to clean data driven documents because word processors generally add another layer of complexity to the overall file structure, do not handle text documents with ease, and generally do not have regular expression support.

### Automatic Cleaning of the Text Layer

In order to use computers to clean the text layer of a document which has been analyzed by OCR software you must first have an understanding of what the "signal" and "noise" once the OCR process has ended. This requires, at a minimum, opening the output of the OCR process and skimming through a good portion of the document to see what has been outputted.

Usually the best way to perform an automatic cleaning of the text layer is to build a script in the scripting language which you are most familiar with to purge the document of unwanted characters. The script which one builds will likely rely heavily upon regular expressions. Regular expressions, for those unfamiliar with that term, are a powerful method of matching characters in a block of text against various patterns. One book which is commonly referred to as the "bible" of regular expressions is Mastering Regular Expressions by Jeff Friedl, however there are many books on this subject. If one is in a job which requires a significant amount of OCR or PDF processing work, it may be beneficial to have a keen understanding of regular expressions.

## Step 3 -- Process the Text Into the Required Data Format

This step is outside the scope of this page as once the data is processed into usable text, then it is a simple matter of transforming the text into the required format.