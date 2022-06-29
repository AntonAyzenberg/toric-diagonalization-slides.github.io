# README for the presentation

## Story 

This repository contains the sourcecode for the 
[slides](https://antonayzenberg.github.io/toric-diagonalization-slides.github.io) of the talk 

"Matrix Odyssey: from computational algebra to toric topology and back" by [Anton Ayzenberg](https://www.ayzenberg.xyz/)

at the seminar of [International Laboratory of Algebraic Topology and its Applications](https://cs.hse.ru/en/ata-lab/), 
Faculty of Computer Science, NRU HSE on June 10, 2022.

## Sources and materials

The presentation is made with html+css+javascript. 

The slides' functionality is based on [reveal.js](https://revealjs.com/).

Math formulae are compiled with [KaTeX](https://katex.org/).

Math functionality of the slides (such as QR-decomposition) utilizes [math.js](https://mathjs.org/).

[model-viewer](https://modelviewer.dev/) is used to display a 3d-model in a single place.

[Unity](https://unity.com/ru) and C# were used to generate a gif with animated hexagonal solid torus.

The model of equilateral Goldberg polyhedron by [Gerry in Québec](https://sketchfab.com/quebec?utm_medium=embed&utm_campaign=share-popup&utm_content=136d354b0f9f40efa8d0f7af18d8a4de) is
used for demonstration purposes.

The [running letters effect](https://dev.to/gnsp/making-the-matrix-effect-in-javascript-din) by Ganesh Prasad is used in one slide
just for fun.

The [pixelated image effect](https://redstapler.co/how-to-create-pixelated-image-with-javascript/) by the Red Stapler is used
to animate most of the figures.

Two pictures of permutohedra were downloaded from [Wikipedia](https://en.wikipedia.org/wiki/Permutohedron).

## A friendly note for those who want to make something similar.

* You are free to use any part of my code, including "letter typesetting effect" used to animate text blocks throughout the slides. 
* I would be happy, however, if you put a reference to either my presentation or this GitHub page - if it really inspired you.

## How-to (I share my personal experience)

Here is a general list of advices for TeX-people who had never prepared slides in html format but want to start doing this. 
If you understand the basics of frontend development, you can certainly ignore the rest of this readme-file.

1. We all like TeX, but pdf-files have a very limited functionality. The format was created for documents, not presentations.

2. There exist lazy ways of presentation-making such as PowerPoint or Google Slides. The latter even has plugins to compile TeX. 
To be honest, it is very inconvenient in practice, as well as Microsoft-style formulae. If your slides contain >10 formulae, 
PowerPoint and Google Slides are not your bros. 

3. Although, PowerPoint and Google slides have many options for animation, they do not allow too much programming and customization.

4. The good solution is to make everything in html+javascript, since it theoretically allows any type of functionality you may think of 
(it is great to have opportunity to [run Doom](https://js-dos.com/DOOM/) right inside your slides). 

5. Luckily, nowadays there exist really cool technologies to make html-slides.

6. An open-source [Reveal.js](https://revealjs.com/) provides a general framework for slides' making, built on Javascript. 
With reveal.js you can transform your pure html-page into a collection of switchable slides, fragments, etc. It's kind of magic!

7. Another powerful modern thing is [KaTeX](https://katex.org/). It is embedded in Reveal.js, so you don't need to care too much about 
installation. The explanations and examples of usage provided at the website of Reveal are very clear and easy to follow.

8. I think KaTeX is better than [MathJax](https://www.mathjax.org/) because the output of mathjax on a webpage is something mysterious 
(neither a text, nor an image), while KaTeX produces a plain text inside html-tags. It runs very quickly, 
the output can be copied to clipboard with no need to deTeXify, it preserves css-styles in a fancy way, and so on and so forth. 
I haven't try to render complicated math stuff, though. 

9. If you want to make Reveal slides in a graphical editor similarly to Google-slides, you can use Reveal-editor. 
Its free version has limited functionality. I haven't tried the full version because I was not sure if it allows manual
work with html and javascript code (if not, I don't see any point in using it, but I just don't know).

10. Since you are still reading, I presume you are not a web-developer. In this case you will certainly be scared of the necessity to 
install Git --> node.js --> reveal.js, maybe even using command prompt to run the stuff. Don't panic. You don't have to understand all these 
things. To get the basic functionality of Reveal, you only need a couple of js-files with a compactified unreadable code, a bunch of
html-examples, and a collection of css-templates. The way this stuff appears on your computer is absolutely non-essential, I believe. 

11. I uploaded [Git](https://git-scm.com/), [node.js](https://nodejs.org/en/), 
and [reveal.js](https://revealjs.com/) following the instructions on the corresponding websites. 
Reveal contains all that is needed, other stuff can be forgotten.

12. In Windows, I use [Visual Studio](https://visualstudio.microsoft.com/ru/) 
to edit html/css/javascript files. [WinEdt](https://www.winedt.com/) can also work with html, 
but to my opinion, it is less convenient for html than for tex.

13. Basically, you can run html-file on your computer by just clicking it. It will open in your default browser. 
This works perfectly well for the examples of slides provided in the Reveal package.

14. However, this is not going to work for the presentation from this repository, even if you carefully downloaded all my files
to some directory on your computer.

15-0. There will be bugs with pixelation-animation of images (this effect is used in my particular presentation). 
To make the pixelation effect, I create html-canvas and try to access individual pixels of 
an image uploaded to canvas. Most browsers consider such procedure unsafe - in the case
the image is uploaded from a source different from the directory of the main html-file. 

15-1. So anyway, if the files are in the same directory, why the hell it's not working? 
Because your browser authomatically considers all your local files as originating from different
sources. From its point of view all your local images are alien files, and the attempt to access their pixels is a threat banned by the
browser.

15-2. Such problems can be resolved by running html-file from a local server. This is done as follows.

15-3. Install local server. I did the sequence: install [XAMPP](https://www.apachefriends.org/ru/index.html),
run XAMPP control panel, start Apache.

15-4. In the directory of XAMPP on your computer find the subdirectory named htdocs (this is for Windows, maybe different in other systems),
and copy all files of the presentation to this directory.

15-5. To run presentation, type in your browser's address line "http://localhost/MyPresentation.html" where MyPresentation.html is the name 
of your presentation, stored in htdocs.

15-6. Now you should be able to extract pixels. If not, you may force your local server to allow "tainted-canvases" from
alien sources. 

15-7. To do this, find the Apache configuration file httpd.conf in XAMPP folder, and copy 
[a certain mantra from this page](https://developer.mozilla.org/en-US/docs/Web/HTML/CORS_enabled_image) to this configuration file.

16. Now you can try writing your own code. [W3schools](https://www.w3schools.com/) seems a perfect source of general information
on typesetting/coding in html/css/javascript.

17. If you got used to tex-->pdf, you will be pleasantly surprized that you don't have to "compile" your html presentation. 
Just refresh your page in browser. It is very cheap to make small corrections and see the result.

18. Remember, however, that changes in a css-file sometimes can't be seen if you simply refresh the page. 
This is because your browser stores css-info in hash, I guess. So if you change css-files, be sure to use hard refresh 
(Ctrl+"refresh browser button" or Ctrl+Shift+R in Chrome) to update.

19. Now when everything works, write your presentation using general html/css/javascript features and Reveal.js API. The ordinary 
tex commands are compiled within the surroundings \\\[ ... \\\] or \$ ... \$ by KaTeX, if Reveal is correctly initialized with KaTeX.

20. Notice, however, that the signs '<' and '>' in your tex insertions may cause errors, because IDE/browser may consider them as 
parts of html-tags. You may replace these signs by the commands \lt, \gt respectively. 

21-0. You are able to show your presentation from your computer, in Zoom or anywhere. However, if you travel to the conference,
you need to understand how to run the presentation from other people's PC. I see two global options for this. In both cases,
you should check things in advance to make sure that javascript is enabled on theirs' computer, and other stuff of this sort.

21-1. If your presentation runs smoothly from a file (without localhost), just copy the whole directory of the project to a 
flash drive and run on anyone else's computer. 

22-2. If you need a server to run your presentation, you need to have a presentation on a server, that's pretty obvious. 
You can try to set up a remote server in a hardcore way, or simply upload your presentation as a site to GitHub (as I did). How to do the 
latter is explained e.g. [here](https://medium.com/@svinkle/publish-and-share-your-own-website-for-free-with-github-2eff049a1cb5). 
I guess, you'd better rename your main presentation file index.html to make things work.

22-3. If the place where you plan to give a talk lacks both the internet connection and the specialists who can
set up a local server, then well... poor you.

## Hope this manual helps somebody. Good luck!


