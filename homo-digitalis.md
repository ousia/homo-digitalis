---
title: Four Useful Printing Features
author: Pablo Rodríguez
date: 2016
publisher: <http://www.homo-digitalis.tk>
lang: en
license: © 2016 Pablo Rodríguez. All rights reserved.
#cover-image: ensayo-escritura.svg
stylesheet: homo-digitalis.css
...

## What Is PDF?

PDF stands for “portable document format.” It has been developed by _Adobe_ for decades. It is _the_ portable document format, and not simply _a_ portable document format. This is even based on the fact that “portable document format” is a trademark granted to _Adobe_ in many jurisdictions.

Leaving legal issues aside, PDF documents are known by average users as being specially suited for printing the file contents without any modification at all. In fact, many of these users even think that a PDF file is unalterable. They say PDF documents cannot be modified in any case. Just for the record, unencrypted PDF documents can be modified also. Although editing them—you may use _LibreOffice Draw_ for this purpose—is not so easy as editing files in a word processor format.

The PDF format—I know there is an internal redundancy here, but I am going to leave it that way—is the standard in the printing industry. Your local copyshop may allow its customers even to print even large documents in any format format its computers can read. But professionals demand documents in PDF format. Or they will charge for text typesetting too.

The average user understands that PDF may be considered the “printing document format”. And this basic perception that captures the final purpose of the PDF is right. PDF is the best option when you want to print finished documents without any modifications—independent from the computer, operative system or printer used for printing.

## A Real Standard

Since _Adobe_ develops the PDF, many think that you can only generate and read PDF documents with _Adobe_ products. This would leave mainly _Adobe Reader_ and _Adobe Professional_—named _Acrobat Reader_ and _Acrobat Professional_ before.

But the previous statement isn’t simply true. Not only by the fact that there are other programs that allow PDF generation and display. There are many of them. The reason behind this colorful diversity is that the PDF is a standard—the ISO 32000–1. _Adobe_ pushed for its first version and the second version is in the works. The released version is publicly accessible from its website containing references to its licensing policy.

Due to this practice, PDF has become the standard for printed matters in a networked world. Some professionals use _Adobe_ products for document generation, printing or display. Many other don’t use products from _Adobe_ and that software matches or surpasses _Adobe_ in professional performance and output. One of the best programs—not being typesetting systems themselves; such as <span class="tex-logo">pdfTeX</span>, <span class="tex-logo">XeTeX</span> or <span class="tex-logo">LuaTeX</span>—would be _Ghostscript_. Because of the documented standard, their quality only depends in how far and faithful any software implements its specification.

The PDF standard is public. It isn’t open, because third parties may only propose implementations to the standard. _Adobe_ has the final word and they can reject any proposed change.

## A Glimpse Into the Features

The PDF document faithfully represents the physical page as it has been exactly designed by its original author. Any—conformant—reader will render the same layout, with fonts and any other characteristics. This makes it perfect for printing. No matter which devices or even software you use, you will get exactly the same output.

PDF has been used not only for printing, but for sharing documents. This is still the case in electronic documents that are a replacement for physical pages. Legal documents are one example. Since screens differ in size, ranging from smartphones and handheld devices to ultrawide screens or ultra–HD TV screens, choosing PDF may not fit all screen sizes in one file. This is the reason why the ePub format is more suitable for electronic editions.

Some advanced features in the PDF are both interactive and multimedia features. The interactive features include digital signatures, a wide variety of annotations, form filling and even interactive forms. Multimedia features include the embedding of arbitrary media types in the PDF document and the reproduction of embedded media in multiple ways. PDF documents may be even extended with _Javascript_ code in all their elements.

The most important property for PDF documents is that they can be generated automatically for preexisting data. PDF generation requires only the coding for the program that merges the data and outputs the PDF documents. This is on–the–fly document generation and requires no further human interaction.

## Printing Features

As already described, PDF is mainly used for printing. The layout is already defined in the document. But when you: work with many documents a day, deal with other people’s file or even go—to copyshops or even professionals—to print your documents, there are many minor issues that can cause big trouble.

This description doesn’t cover faulty implementations. Printing requires three error–free elements: document, program and printing device. The document is generated by a different number of programs and many of them implement these features. As far as I know, no other program than the ones from _Adobe_ can read the information from the PDF document. And the device requires that its driver understands and performs the information provided by the program.

In a perfect world, this would be an everyday reality. But as you guessed, this isn’t always the case. Not all PDF generators support the addition of this information to the PDF document. As far as I know, only the readers from _Adobe_ can read it in the document, from version 9. And printer drivers have also bugs. Your local copyshop may not have the reader or the printer drivers updated to latest version. Any of these two may lead to wasted paper. No matter who pays for that, wasted paper is no gain for anyone.

Just in case anyone wonders, I will briefly describe how I discovered these features. I was working on the typographic composition of a rather short work. I had to go to a printer on a bookstore and stationery nearby. It was a PDF document, which had the page with four composed pages. The document had to be printed in duplex flipping the long edge and with no print scaling. Both features, due to the small size of each page already imposed on each paper sheet, were critical.

I had to inform always about the double–sided printing with right flipping. And I had to be aware they don’t imposed the pages again with the booklet option from _Adobe Reader_, as it once happened. Sometimes I simply forgot to tell about disabling the page scaling. I considered the whole scenario as highly ineffective. I wasn’t paying for errors in their interpretations, but this was uneasy for me. Not that I wanted to pay, but I had to avoid those stupid mistakes. Everybody was loosing there.

I checked the PDF specification in the search for some light about this. And there were four entries that suited perfectly for my needs. These needs aren’t particular to myself, but useful for the rest of us. I saw them and I proposed the implementation of a couple of these features to the main developer of the typesetting system I use: <span class="tex-logo">ConTeXt</span>. You guessed it, the ones related to duplex printing and page scaling. The developer was kind enough to implement them in less than a week. As I need the other two features for the document merging system we use at work, I’m going to propose the further implementation.

I’m going to explain these features, but not how to enable them in any particular program. My purpose is to show their utility. And as to enable them, you will get more reliable sources of information than myself on the net.

Titles in the next four sections contain the code invoked in the PDF document source. It is the part that you don’t see, unless you extract the PDF contents and browse them with a special editor.


### `/Duplex`

This option enables duplex printing. That is single– or double–sided printing. In the latter, it specifies how the page should be flipped to output matching page sides.

Simplex printing is essential in printers where the default is duplex printing in portrait mode. These aren’t the most if of them, but there are some in working environments to avoid paper waste. Being that default a sensible one, it may not fit all needs all the time.

Flipping the long side of the paper is the most common option in portrait duplex printing. Of course, duplex printing can’t be enabled when the printer doesn’t have the feature. Short–side flipping is essential for landscape duplex printing.

### `/PrintScaling`

The current PDF specification only allows two options. Either the page is printed with no zooming at all, or the page contents are subject to the default value from the application. There are no so many options for page scaling in the specification as _Adobe_ offers in their products.

The common option would be to set the default of page scaling to fit into the printable area. This option as a default enables most correct printings. And if the user knows that the document contains no element outside the printing area, printing scale should be set to none in that particular document.

There is something important about this feature to be considered. When the option is selected, _Adobe_ software fits the page contents into the printer margins, _required or not_. Not zooming the page when not required, would make the printing size not that bit smaller.

### `/NumCopies`

As the name reads, this field sets up the number of copies we want from a given document. For security reasons, even if the specification allows the highest number from the printing dialogue—wich seems to be 999 in most PDF viewers—, the maximum number of copies is set to five.

This feature is important when third persons print our files. We can forget about printing. It is also a valuable help with systems that automagically generate PDF documents. In some work scenarios, you may be required to have different number of copies from the documentation. Even for the same customer or operation, when the documents belong to different kinds. In all these cases, five copies is a good limit to prevent security issues.

### `/PickTrayByPDFSize`

This last feature is essential when printing to different paper sizes. If the printer is provided with trays for different paper sizes, it will select the right one from the page size of the document. It can be enabled or disabled in the document.

Another possibility is to print to paper sizes other than the default from the printer. In this case, it is essential to have the option enabled. It is better to have it in the document, to avoid forgetting or overlooking this. Otherwise, the document will be double centered—in both axes—in the page, but it won’t be scaled.

## Useful?

The usefulness of these four printing options is to avoid errors when printing. A side efect is to be faster when printing PDF documents.

The basic idea is that the user—either she has generated the document or only receives it—can print the document by invoking the printing dialog and just confirming what has been already selected. This is a faster process and less prone to errors.
