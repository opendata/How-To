---
title: Working with PDFs
layout: default
---

{:toc}

# Introduction

The Portable Document Format (or "PDF") is an excellent way to share documents. Documents consistently render across all devices -- from desktop computers to smart televisions -- in the exact specification the publisher designed. Unfortunately, the advantages which the PDF format gives to publishers of *documents* are mostly the same as the disadvantages which the PDF format gives to publishers of *data*.

## Some Background on PDFs

<!-- TODO: link out this section to the PDF spec. -->

Pulling *data* out of PDF *documents* can be an arduous task. The PDF document format is mostly an image format. Text which is encoded within a PDF document is encoded according to lines which are given X, Y coordinates as to the corners of the block of text (which can be a line, a sidebar, a table, or any other block of text). So rather than having text be associated semantically, tabular, or any other way in which structured *data* should be kept, text is simply given an X, Y coordinate and a blob of text.

PDF documents are essentially an image format. This is why they are so often used when scanning and displaying documents -- and what allows for consistent rendering across devices. As such, text within a PDF is rendered in layers. When a document generating program renders a PDF what happens is that it compiles an image of the page. If there is text which is to be rendered that text is rendered as an additional (hidden) layer over the image. This is why when you often select text from a PDF viewer there can be an offset in the text that is selected and that which the human eye is seeing. More simply PDF viewers show you the image of the page but when you want to select text the PDF selects the hidden layer which contains the text.

Layers are a powerful device for rendering consistent documents but it does not give effect to the placement of text within the page, nor is there any inherent mechanism for semantically linking text together. For example, headers in HTML files (like the text blob above this text which contains the text, "Some Background on PDFs") are noted using an `<h2>` and `</h2>` tag. Headers come in levels so `h2` could be any number between 1 and 9, 2 is only chosen as an example and means second level header. Header tags allow machines to understand that the `h2` is (a) nested underneath the preceding `h1` and (b) the text which follows until the next `h2` or `h1` tag is linked to this particular `h2`. This is powerful when one is trying to parse text. PDF documents do not have such a semantic structuring. The PDF specification, which, again, was meant as a rendering format not a communication format, does not have a semantic system. Whatever program one is using to make a PDF will simply output the `h2` as text which is somehow different in font, or size, or however the document designer has meant for it to be.

Lastly, PDF documents need not consistently render text in any particular order. This is an advantage for working with a highly stylized report because text can be layered and added at different times. Because text within a PDF document only needs a blob of text and the X, Y coordinate for the corners, even when exporting to PDF from an office program or from a web browser one cannot rely upon the ordering of the text in the PDF document to establish the order of the text that will be displayed until one displays the whole page with the X, Y coordinates for each of the blobs of text. If one has ever tried to copy and paste from a PDF one has seen this because when one pastes the text block into another program the end of the lines as rendered by the PDF original are almost always pasted in as new lines into the new program. Lawyers have likely wasted, collectively, thousands of billable hours of client time simply backspacing out the new lines from a block of PDF text after pasting into word processors. Indeed, the author's very first piece of open source software was a [text editor plug-in](TODO:link paste pdf) which would ease such a process.

## Why is This Important

The above (albeit brief) overview is important to understand because PDF has become somewhat of a default standard for publication of *data*. This is particularly true in the legal field, but it is also true in other fields. This is suboptimal for a few reasons.

The main reason publishing information via PDF documents is suboptimal is that getting *information in context* out of PDF documents is difficult. Data alone is important, but data in context is even better. This is especially important when the data being communicated, published, or transmitted is not simply a raw data feed but instead is data of a more complex nature (e.g., legal data and other data which is highly context driven).

What can be frustrating to those within the open data, open law, and open government communities who consume such data feeds, is that the information is *usually* (but not always) built in context but then all of that contextual data is lost when the information is rendered to a PDF.

For example, to process judicial opinions one must understand how to deal with footnotes. Any lawyer who has sent a judicial opinion to their ebook reader knows the pain that this causes. It is certainly not the makers of the ebook reader's responsibility to handle footnotes, because the computer programs used to change the PDF format of the judicial opinion to the ebook reader's format has no way to connect a blob of smaller text at the bottom of the page with (perhaps) a leading number offset just a small amount on the X axis as a footnote and to be able to link that back to a superscript number higher in the page. When the document was written, either in a free and open source word processor such as LibreOffice or in a paid and proprietary word processor such as Microsoft Word, that semantic linking of the text of the footnote to the footnote citation is maintained. However, when the document is rendered to PDF the semantic linkage between the footnote and the citing text is lost. The same reasoning applies to legislation, regulations, and many other sets of data which require context and semantics in order for machines to process them properly -- which would increase the flexibility in how entities and individuals consume that data.

## Authenticity of Publication

One of the largest reasons for why lawyers in particular publish documents (which really should be thought of as "content data") in PDF format is because PDFs are more difficult to modify. This is a valid observation. And it is (mostly) true. However, as with all digital formats, PDF's *can* be changed. All one really needs to change a PDF format is some clever [GIMP](TODO:link GIMP) skills. Even Adobe Acrobat PRO can allow one to change a PDF document. To change a PDF one needs to change the image layer and the text layer, but this is not a difficult process.

To combat such an ability to change the document, Adobe allows document publishers to "lock" PDFs. <!-- TODO: Confirm the following... --> blah, blah, blah.

While it is true that the above *works*, it begets the question as to whether it is the optimal way to ensure that the *information* is authentic. The challenge which well intentioned individuals are trying to overcome is a laudable goal: ensuring the legitimacy of the information. Where the implementation of that goal is suboptimal is in locking a public agency into an expensive, proprietary format which, in truth, solves a different problem set. The problem set which Adobe Acrobat Pro's "locking" feature is trying to solve is to ensure the *presentation* of the information is accurate and complete. The feature does ensure that the information is accurate and complete, but only derivatively and indirectly. There are other methods of ensuring that the data one is publishing is accurate and complete which do not require expensive, proprietary vendor lock in. <!-- TODO: Write this and link it here. -->

# Working with PDFs

Despite PDFs distinct disadvantages for publishing data, many public agencies still publish data in PDF formats.

