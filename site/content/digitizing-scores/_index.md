---
title: How to Digitize Musical Scores
image: /img/white-background.jpeg
sections:
  - text: >-
      As technology continues to progress it is incredibly important that we as
      humans do not lose the music of previous generations. Fires, rot,
      misplaced papers, faded memory; many things can sweep away our history.
      Countless guzheng creations were lost this way. Thankfully scanners and
      image editing software enable us to preserve our music for future
      generations.
  - heading: 'Scanning and Editing with GIMP, Photoshop, and others'
    text: >-
      Turn scans like this:


      ![Scanned sheet music.](/img/sheet-music-before-large_compressed.jpg "Low
      quality scanned sheet music.")


      Into this:


      ![Cleaned scan of sheet
      music.](/img/sheet-music-after-large_compressed.jpg "Scan of sheet music
      cleaned and edited.")


      GIMP is a powerful free image editing solution; Photoshop is the famous,
      expensive alternative. The general workflow goes something like this:


      1. Scan the sheet music. If it's in good condition you could use an
      Automatic Document Feeder (ADF) to scan a whole stack quickly. Otherwise,
      use a normal flatbed/plate scanner to scan each piece of music one at a
      time.
         1. As you are scanning, adjust the options to make the notation as clear as possible while picking up as little of the background of the paper as possible. Options vary system to system, but they might include brightness, contrast, and threshold.
         2. Pick a reasonable resolution in Dots per Inch, (DPI) for your scan. If I am scanning a document without changing its size, I'll scan at 300 DPI. If it is a small scan you want to make bigger, or there is fine detail you can't see, you may want a higher DPI - like 450 or in really sensitive cases, 600 DPI. Be careful though, as file sizes get much larger as you increase DPI. Big files take longer for your editing software to load. Waiting for your software to churn through huge files is tedious.
         3. Pick your file type. I recommend the "TIFF" file type, which most scanning software should know how to create. The files are bigger but they retain more of the original information. If you can't create tiff files, don't worry. PNG or even JPEG files are usable
         4. I highly recommend performing the scan in Grayscale or as some scanners call it, "Black and White". This will give you much smaller file sizes, which is super good, and will make document cleanup easier.
      2. Once you have good scans of your music make backup copies of your
      scans, then open the files in your editor. As GIMP is free and works on
      most computers, I'll write the steps for that software. Photoshop has
      similar functionality but the tools will have different names.
         1. With your file open, check to see if the scan is tilted. You can do this by enabling grid lines and comparing them to things that should be vertical or horizontal, like the lines at the ends of measures, or the bottom of every numeral or note.
            1. In GIMP, Turn on grids through View > Show Grid. Change the grid on this particular file through Image > Configure Grid. Change the way grids first appear on every image through File or GIMP > Preferences > Default Grid.
         2. If your scan is tilted, straighten it with an automatic tool (Photoshop has some) or manually by selecting the Rotate tool (Tools > Transform Tools > Rotate). Scans are typically less than 1 degree off, in my experience, but that's noticeable.
         3. Now that everything is straightened out, it's time to remove any background color that came through on your scan. This is the magic step that will make other people go "wow".
            1. Get the "Select By Color Tool" through Tools > Selection Tools > By Color Select.
            2. In the Tool Options panel, found on the right side by default or through Windows > Dockable Dialogs > Tool Options, change the threshold of this tool. The default seems to be 15; I found 30-60 proved the most effective.
            3. Click on the center of one of the notes, characters, or numerals of the music. In GIMP you'll see dotted outlines dancing around everything that's a similar color. Hopefully, that includes all the music on the page!
            4. The selection won't go all the way to the edge of the numbers/notes/characters, so expand the selection to include them. Do this through Select > Grow. I find between 1-3 pixels of growth typically grabs everything I need.
               1. Pro tip, if your previous selection picked up lots of specs in the background of the scan, and you don't want to change your selection threshold level to get rid of them, you can use Select > Shrink by 3 pixels to eliminate many of them. Then Select > Grow by 3 or more pixels and you're back in our flow!
            5. Almost done! Go to Select > Invert and press delete. Now all your document has on it are the notes/numerals/characters you selected!
               1. If your document turned black, your background color was set to black. Undo your delete (Edit > Undo Clear), then click Tools > Default Colors. Try your delete again. The page should show up white!
               2. If your document has a checkerboard pattern in the background, it means the background is transparent instead of white. To fix this go to Layer > New Layer and make sure the fill type is white. Everything whited out? Good. Select Layer > Stack > Layer to Bottom. Your music should now be visible.
            6. Save your document in whatever file format you wish. If you want to do more work on it, keep it in GIMP's default XCF file format. If you are happy with it, export it as whatever format you wish. GIMP also has a shortcut where you can overwrite the original file you opened. That is found in File > Overwrite.
      3. Success!
---

