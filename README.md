This repository contains all files associated with the 'Slow Down: Teaching students to encode their close reading' workshop, held at the **Teaching History in Higher Education Conference**, 8 September 2015 at the Institute of Historical Research, London.

# CLOSE READING WITH TEI
This workshop will explore a historical text and help you create a digital record of your analysis
## SETTING UP YOUR WORKSPACE
Visit http://www.github.com/mhbeals/tei_ihr_workshop
On the right-hand side, you will see the option to ‘Download ZIP’. Left-click on this and save the file to your computer (where you can find it)
Open the zip folder and drag-and-drop (or extract) the file folder onto your computer. A good place is on your desktop (if it is not too cluttered)
Start WordPad or another plaintext editor (not Word). Open the file transcription.xml, which is inside your downloaded folder. 
You will see a short section of XML code before and after the transcription. This is vital, so please do not delete or alter it. Everything you will edit will be between the body tags ```<body>``` and ```</body>```
You are now going to encode or mark-up your text.
## ENCODING YOUR TRANSCRIPTION
The first thing you will do is put in some basic typographical notations.
At the start of your transcription, and at the start of every new paragraph (or heading), place a ```<p>```. This explains to the computer that a new paragraph has begun. At the end every paragraph (or heading), place a ```</p>```. 
Save your file and open your browser.  Because of some security settings, this should be either Internet Explorer or Firefox, rather than Chrome. Safari (for Apple aficionados) should also work.
Drag the file transcription.xml from your file folder into your browser window. 
You should now see a basic transcription, with correct paragraphing. 
Look over your transcription and find the various people and places you have identified in your groups, including any he or she referring to a named person. 
Now that you have noted these, you are going to put proper code around them.
Keep your browser window open. Every time you tag a person, place or idea, save your text file and refresh (F5) this page.  You should see your changes immediately and, if the code has an error, you will know exactly when it occurred! 
## RECEIVED AN ERROR?
If your text comes up only in black, with no paragraph divisions or headings, or doesn't come up at all, something has gone wrong. Open your .xml file (in Wordpad) and check that you have:
+ Placed ```<p>``` at the start of every paragraph, including the start of the page
+ Placed ```</p>``` at the end of every paragraph, including the end of the page
+ Made sure all your ```<persName>```, ```<placeName>``` and ```<interp>``` tags are properly enclosed in ```<>```s
+ Made sure you have both an open ```<>``` and close ```<\>``` tag for each tag you use
+ Made sure you attribute values are fully enclosed in ""s
+ Made sure you have a space between the " of one attribute and the start of the next
+ Made sure you do NOT have a space after the = of an attribute

If your text still does not appear formatted, you may need to remove the text one paragraph at a time, refreshing your browser window, until it appears. This will help you identify which paragraph (or sentence) has the error within it.
Once you have you a full formatted file, congratulations! If you choose to post your work online, please do place a link to the site (https://github.com/mhbeals/tei-ihr-workshop) and share these instructions freely
 
## ENCODING PEOPLE
For persons, SURROUND your original text with these
```<persName key="Last, First" from="YYYY" to="YYYY" role="Occupation" ref="http://www.website.com/webpage.html"> </persName>```

+ Inside the speech marks for key, include the full (canonical) name of the person mentioned
+ In from and to, include their birth and death years, using ? for unknown years
+ In role, put the occupation, role or relevant 'claim to fame' for this individual
+ In ref, put the stable URL (link) to the Dictionary of National Biography or academic journal website where you found this information
For example
```<persName key="Beals, M. H." from="1982" to="2282" role="Lady Historian" ref="http://www.mhbeals.com/teachingblog">```M. H. Beals```</persName>```
Did you notice how the original text, M. H. Beals, is still present, between the ```<persName>``` and ```</persName>``` tags? You must retain all of the original transcription, even if it seems repetitive in ‘the code’
Also remember that case (N rather than n) matters, so please be careful when typing.
If there is an ampersand (&) in your link, you will need to replace this with &amp;
## ENCODING PLACES
For places, SURROUND your original text with these

```<placeName key="City, Country" ref="http://www.geonames.org/########/location.html"> </placeName>```

+ In key, put the site (if there is one), city and country with best information you can find for the modern names for this location
+ In ref, put a link to the relevant coordinates on Geonames website
To obtain this, go to www.geonames.org and type in the location in as much detail as possible (villages rather than major cities). When the list appears, click on the small shield (usually a P, for place or A for area) to the left of the location name. This will take you to specific page for your location. 
For example
```<placeName key="Loughborough, United Kingdom" ref="http://www.geonames.org/2643567/loughborough.html">```the local university```</placeName>```

You should try to be as specific as possible (while still being accurate) when choosing a location, and your key should always reflect the modern political or geographic region, rather than the historical one. For example, Ontario rather than Upper Canada (although this is only roughly accurate) 

## ENCODING CLAIMS
Now that you’ve encoded your nouns (people and places), you will need to begin to interpret the statements or arguments made by the author. These are not always straightforward, and are sometimes barely implied by the choice of words being used, so you will have to read the article very carefully!
There are two ways to encode a claim (in this exercise). The first is ‘sourcing’, something you may be familiar with from secondary school. When ‘sourcing’, you will need to determine what is being asserted, and whether or not it is true or false, based on your secondary reading. The second is to ‘close read’ it for clues in the language and syntax.

### TO ‘SOURCE’ A CLAIM
Surround the original text (the entire statement but not necessarily the entire sentence) with these

```<interp key="reason" n="citation" cert="high" ref="http://www.website.com/webpage.html"> </interp>```

+ In key, explain why you believe this claim is true or not, using secondary evidence. Phrase this as you would in an essay, rather than personalised with “I believe”
+ In n, put a full citation (again, as you would in an essay) to the relevant SECONDARY source. You won't be able to italicise or underline the title, but this is fine
+ In cert (short for certainty), put: high, medium, low or unknown, depending on how much you trust the secondary source you have used. If you have used multiple sources, for example, and they all agree with your cited source, you can be fairly confident of your statement. If you can only find a single article from many decades ago, you may only have ‘med’ or ‘low’ confidence.
+ In ref, you can put the link to the website where you got the information to assess this claim.  Make sure to use the stable (short) url for websites such as JSTOR or Taylor and Francis. If you are using a hard-copy source, leave this attribute blank 

After you encode each claim, save your file and refresh your browser. If you hover over your claims (blue), you will see your interpretation and citation.

### TO ‘CLOSE READ’ A CLAIM

Surround the original text (the entire phrase but not necessarily the entire sentence) with the ```<interp>``````</interp>``` tags as above

+ In key, explain what you believe this phrase or sentence tells you about the author, event, period or documents. What is the ‘subtext’ or ‘context’ of what has been written (or left out) and how it was phrased. Citing additional evidence from other sources will support your claim
+ In n, put a full citation to any relevant  source you are using to support your claim
+ In cert (short for certainty), put: high, medium, low or unknown, depending on how likely your interpretation is correct.
+ In ref, put the link to the website where you got the information to assess this claim.  Make sure to use the stable (short) url for website such as JSTOR or Taylor and Francis. If you are using a hard-copy source, leave this attribute blank “”
After you encode each claim, save your file and refresh your browser. If you hover over your claims (blue), you will see your interpretation and citation.

