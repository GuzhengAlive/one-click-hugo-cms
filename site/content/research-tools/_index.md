---
title: Research Tools
image: /img/white-background.jpeg
sections:
  - text: >-
      Here are technical solutions and techniques I needed to create this work.
      They aren’t specifically Guzheng related but were invaluable. Hopefully
      they will help you too. Research is better with friends!
  - heading: Document Organization
    text: >-
      Organizing documents can be a prodigious pain. I use the Mendeley
      reference management software. It is free. It monitors my download folder,
      imports citation information, and renames files when I change the
      metadata. It has its pros and cons; I have heard good things about
      alternatives such as Zotero and EndNote.
  - heading: Entering Pīnyīn
    text: >-
      The accent marks or "diacritics" shown over Chinese words written in
      Pīnyīn can be entered in three ways.


      1) Google Translate will generate pinyin for any characters you enter. You
      can copy and paste the text where you need it.


      2) Mac computers allow you to enter letters with diacritics by holding the
      letter's key. Holding down a vowel makes a menu pop up where you can
      choose several diacritics. It's pretty fast but doesn’t have all of the
      combinations.


      3) Windows computers need extra work to accomplish the same task. You'll
      need to install a custom keyboard. Rob Rohan produced one you can download
      from here. If his installer doesn't work, you can create your own
      installer in 5 minutes by doing the following.


      1. Download Microsoft's Keyboard Layout Creator (MKLC) here.

      2. Download Rob Rohan's source file here.

      3. Install the MKLC to your C drive. Installing to a different drive can
      cause errors.

      4. Run the MKLC and have it open the source file (File > Load Source
      File).

      5. Recreate the installer package. (Project > Build DLL and Setup
      Package).

      6. If a windows pops up saying it has completed but there are warnings,
      hit cancel. The warning is just the fact that you are using nonstandard
      characters.

      7. When a window pops up to say it has completed and would you like to go
      to the directory, hit "okay".

      8. Double click on the "setup" file in that directory to install the
      keyboard!

      9. Set the newly installed keyboard to be your default. For help on that,
      see Microsoft's help page.
  - heading: Chinese Character Identification
    text: >-
      So you want to type a character on the computer but you don’t know its
      pinyin. What do you do? If you are 2016-era me you spend 15 minutes
      searching a character genealogy like this one. if you are 2017-era me you
      use Google Translate.




      Google Translate’s smartphone app has an optical recognition feature. Open
      the Translate app, set your “from” language to Chinese and select the
      camera icon. This opens a camera function. Point your smartphone at what
      you want to analyze and tap the capture button at the bottom of the
      screen. The picture will be taken, uploaded to Google, google will analyze
      it for Chinese characters, and put boxes around what it thinks is Chinese.
      Select the characters you want and google will enter the characters into
      the app. There you will see not only a translation but the pinyin -
      meaning you can now type those characters into a computer or phone.




      I cannot stress this enough - without this Google Translate feature this
      project would never have gotten this far.
  - heading: Automatic Character Recognition
    text: >-
      Picture this: you have pages and pages of text you want to add to your
      document but it is too much to type by hand. What can you do? Use OCR of
      course!




      OCR stands for Optical Character Recognition. It is a type of software
      that scans image and pdf files for characters and creates a text document
      with what it found. There are many options out there. I am happy to say
      that the best free one currently out there is ocr.space which is produced
      by the company a9t9. It is incredibly fast, free, and supports Chinese and
      English recognition. The only downside is it can't do both at the same
      time - you have to run your document twice. But that only takes a second!




      Any OCR software will have different levels of success with different
      documents. There will be errors so it's important to check your new
      document thoroughly. Even with that requirement, though, you'll end up
      saving a huge amount of time.
  - heading: Extracting Chinese Characters from Roman text
    text: >-
      When collecting lists of songs and glossary terms I ended up with
      spreadsheets full of jumbled English and Chinese characters.  I could copy
      and paste every chunk of text into two pieces but boy does that take a
      while. Spreadsheet functions came to my rescue.




      ### Removing English Entirely


      So you’ve used OCR software to copy some text but the resulting output is
      a mess. How do you separate out the Chinese characters? Answer: Regular
      Expressions. Think of them as the “Find and Replace” software feature
      hidden inside a formula.




      In Google Sheets: =REGEXREPLACE(A2,"\[A-z0-9”“'/()，&.‰》@-丫）*-;／口\\$\\．]",)
      will look in cell A2 for any alphanumeric character or any of the special
      characters listed and delete them. Many word processors understand Regular
      Expressions but since I typically work with columns of data Google Sheets
      is best for me.




      Notice near then end I have the Chinese character 口.  Regular Expressions
      are so powerful you can list specific Characters you want to remove as
      well. My OCR software frequently inserted 口 in place of “O” so I put that
      in the expression as well.




      If long formulas unnerve you you can pull the regular expression into a
      separate cell and work on it. You can put the text you want to change in
      Column A, a short formula in Column B, and the Regular Expression in
      Column C. That would look something like this:




      (Column A) Text with 汉字 (Column B) =REGEXREPLACE(A2,$C$2,)  (Column C)
      \[A-z0-9”“'/()，&.‰》@-丫）*-;／口\\$\\．]




      Note: some special characters are actually commands to Regex. To include
      them in your find and replace scheme put \\ in front of them, like \\$ and
      \\. Learn more at RegularExpressions.info 




      ### Splitting based on a specific character, Automatic


      Google Sheets has a function Data > Split Text to Columns… Select the text
      you want to split, select or enter the character you want to split on, and
      voilà!




      Microsoft Excel has Data > Text to Columns. This function has a few steps
      but accomplishes the same feat. You can see a video of this at Microsoft’s
      Support website.




      Note: These functions typically overwite any text in columns to the right.
      Insert enough blank columns so you don’t lose anything.




      ### Splitting, Manual


      If for some reason you don’t want to run an automatic option Microsoft
      Excel or Google Sheets can again both do manual separations. For my use, I
      had a column in a spreadsheet where each cell had the Chinese characters
      for the name, a space, and then the translated name. I put this function
      into the cell next to it: 




      \=LEFT(B2,FIND(" ",B2))




      This function goes to cell B2, searches for the first space, counts the
      number of characters before that space (to the left of it), and then
      copies those characters into a new cell. A similar function netted me the
      translated names:




      \=RIGHT(B2,LEN(B2)-LEN(C2))




      This one counts the number of Chinese characters copied by the previous
      equation into cell C2, subtracts that number from the total number of
      characters in the combined Chinese-English name, and copies that many
      characters into a new cell starting from the right. Since the Chinese
      characters were always on the left I ended up with only the English name
      on the right. Follow that up with Copy -> Past Special -> Values Only and
      you have what you need, clean as can be.
  - heading: Language Switching / Translation
    text: >-
      It's important to remember that translations are an approximation. Every
      source is going to give a slightly different answer depending on how you
      word the question, who wrote the reference, and how they chose what to
      include. Mandarin is a huge language that has changed over time. While a
      fluent speaker can recognize tens of thousands of words constructed out
      of, oh, 3,000 characters, there have been tens of thousands of characters
      used across history. I've seen estimates that put it as high as 90,000+
      characters. You wouldn't encounter most of those in your day-to-day but
      there is no telling what you may find if you are digging into ancient
      records. You may need to visit multiple references if you are dealing with
      obscure characters.




      ### Web Resources


      Yellowbridge.com: For quick lookup of an unknown character, especially
      when I don't know if it's in simplified or traditional. Provides the other
      version if there is one. It also offers definitions but they often lack
      specialized meanings.




      Google Translate: quick sanity check on pinyin of a character and provides
      tone marks for easy copying and pasting.




      The website MandarinTools.com has a whole host of tools designed to make
      interacting with Chinese characters easier. The dictionary lookup tools
      are exceptional.




      ### Smartphone


      Google Translate app. INVALUABLE. This has fantastic optical character
      recognition, meaning from a picture or a live scan I can digitize written
      or printed Chinese, or get the pinyin so that I can type it in myself.
      It's even able to read some handwritten and stylized characters.




      ### Books


      A large two-way dictionary. I use the hilariously mis-named "Pocket"
      Oxford Chinese Dictionary (1100 pages aren't about to fit in anybody's
      pocket) ISBN 978-0-19-800594-0. It takes care of most of my lookup needs,
      especially thanks to having traditional characters called out next to its
      simplified entries. It doesn't cover the same set of words in both
      directions. It does not have an entry for “Phoenix” but does have 风/鳳 -
      which is Chinese for “Phoenix”.




      A large, one way Chinese -> English dictionary. The thought here is the
      focus on translating in only one direction allows for greater depth,
      breadth, and related words. I use "A Chinese-English Dictionary (Revised
      Edition)" ISBN 978-7-5600-1325-1, from the Foreign Language Teaching and
      Research Press, fltrp.com.cn I don't know anything about them, it just
      happened to be a dictionary I picked up somewhere and it's met my needs.
      the 1700+ pages give it a feel of authority.




      A character lookup system. For when your optical character recognition
      isn't working, and you don't know how the character is pronounced. The one
      I use is "Chinese Characters, A Genealogy and  Dictionary" from
      zhongwen.com. Time consuming to use, but is an excellent tool when you've
      encountered something entirely new. ISBN: 978-0-9660750-0-7. This book
      contains 360 pages of character trees covering 4,000 characters. The
      printing is small.
  - heading: Romanization Conversions
    text: >-
      Romanization is the representation of Chinese words in the Latin alphabet.
      When digging through research from across the years and regions it is
      common to see the same Chinese character represented with different
      combinations of latin letters. To help you negotiate those differences
      here is a table of romanization equivalences from UNESCO.




      A bit about the systems: The most prevalent system today was created in
      China in the 1950s and is called Pīnyīn (拼音) (Formal name 汉语拼音方案, Hànyǔ
      pīnyīn fāng'àn). Before that Foreigner missionaries created various system
      with different levels of use from the 1500s onward. In the last 200 years
      major systems have included the Wade and later Wade-Giles system of
      1859/1892, the 1902 French-created  École française d'Extrême-Orient or
      EFEO, the French-created Postal Romanization of 1906, the Lessing-Othmer
      German system of 1912,  the Yale System of 1943. These are the big ones
      you might find in your search; they'll certainly help explain why the
      various sources I quote have four different ways to spell "zheng". There
      were other systems created for various other purposes but not as widely
      used; you can see more on the Wikipedia page.




      The UNESCO table contains Pinyin, Wade Giles, EFEO, and Yale, the four
      most common you'll see in English-language sources. It's missing those
      used for other languages and the earlier missionary systems. There are
      other partial comparisons and coverage of the French, German, and various
      other systems on this French article on Biblioweb. Perhaps an enterprising
      individual would be up for making a full table of equivalences? I'd
      recommend keying off of IPA tables and programmatically generating the
      table. Get in touch if you want to commiserate!
  - heading: Other Tools
    text: >-
      I found use of various other utilities that seem worth recommending. These
      aren't specific to Chinese or musical instruments, but I found them
      valuable nonetheless.


      * Pdf Compressor: https://smallpdf.com/compress-pdf\
        Useful for when I turned a series of images into a pdf file. Shrank one file from almost 1GB to just 50MB.
      * Website Backup: https://www.httrack.com/ creates a complete copy of my
      website on my computer. Having a local copy of all my work gives me great
      peace of mind. If running on a mac, requires Macports
      https://www.macports.org/.

      * Image conversion software: JPG image files perform better on web pages
      than PNG files, often because they can be smaller. There are many options
      out there; I happen to use http://png2jpg.com/

      * Image compression software: Helps keep images reasonable. I use
      https://imageoptim.com/mac; there are others out there.

      * Image editor such as GIMP.
---

