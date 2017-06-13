---
title: Image uploads
author: Matthew Routley
date: '2005-04-14'
slug: image-uploads
categories:
  - code
tags: []
---

<p>A particular challenge with maintaining a weblog is the uploading and resizing of images. The process involves choosing the correct images, creating large &amp; thumbnail sized versions, uploading these images to the webserver, and posting the appropriate code into the weblog post. In the spirit of my last few posts, <a href="http://public.me.com/mroutley">image2web</a> is an <a href="http://www.apple.com/applescript">applescript</a> I use to automate this process:</p>

<pre>
<code>
  --user-specific variables
  property theAlbum : "Marked"
      --contains the images to be uploaded
  property theBasePath : "the:path:to:the:local:images:" as alias
      --the local path to the weblog
  property tagBaseUrl : "http://www.your.website.org/path/to//blog/images/"
      --the url to the weblog images
  ---declare globals
  property htmlText : ""
      --stores the image tags &amp; is copied to the clipboard
  
  tell application "Finder"
      set theList to name of every folder of theBasePath
  end tell
  
  --choose which weblog category the images belong to
  set theCategoryList to choose from list theList
      with prompt "Choose the post's category:"
  set theCategory to first item of theCategoryList
  
  tell application "Finder"
      set theCategoryFolder to folder theCategory of theBasePath
  end tell
  
  --I use a smart album that collects photos with the checkmark tag
  tell application "iPhoto"
      activate
      select album theAlbum --so we can see which images are involved
      set theImages to every photo of album theAlbum --collect the images
      repeat with thisImage in theImages
          set thisImage to get image path of thisImage
          my processImage(thisImage, theCategoryFolder)
      --resize &amp; generate the thumbnail
      set theResult to the result --avoid declaring more globals
      set thePhotoName to item 1 of theResult
      set theMainImagePath to item 2 of theResult
      set theThumbnailImagePath to item 3 of theResult
      my uploadImage(theMainImagePath, theThumbnailImagePath) --upload the image
      my makeTag(theCategory, thePhotoName) --create the appropriate html
      end repeat
      set the clipboard to htmlText --pass the html code to the clipboard
  end tell
  
  on processImage(thisImage, theCategoryFolder)
  
      set theResult to display dialog "Enter the name for " &amp; thisImage &amp; ":" default answer ""
      set thePhotoName to text returned of theResult
  
      tell application "Finder"
          set theDestinationPath to POSIX path of (theCategoryFolder as string)
          set theMainImagePath to (theDestinationPath &amp; thePhotoName &amp; ".jpg")
          set theThumbnailImagePath to (theDestinationPath &amp; thePhotoName &amp; "-thumb.jpg")
          do shell script "/usr/local/bin/convert -resize 640x480 +profile \" * \" " &amp; "\""
      &amp; thisImage &amp; "\"" &amp; " " &amp; theMainImagePath
      ---use extra quotes to protect against spaces in path names
          do shell script "/usr/local/bin/convert -resize 240x240 +profile \" * \" " &amp; "\""
      &amp; thisImage &amp; "\"" &amp; " " &amp; theThumbnailImagePath
      end tell
      return {thePhotoName, theMainImagePath, theThumbnailImagePath}
  
  end processImage
  
  on uploadImage(theMainImagePath, theThumbnailImagePath)
  
      set theMainImage to POSIX file theMainImagePath
      set theThumbnailImage to POSIX file theThumbnailImagePath
  
      tell application "Transmit"
          open theMainImage
          open theThumbnailImage
      end tell
  
  end uploadImage
  
  on makeTag(theCategory, thePhotoName)
  
      set htmlText to htmlText &amp; "<a href="http://%5C%22%22" tagbaseurl thecategory thephotoname><img src="%5C%22%22" tagbaseurl thecategory thephotoname/></a>"
      --show the thumbnail &amp; link to the full-size image
  
  end makeTag
</code>
</pre>

<p>The workflow is as follows:</p>

<ol>
<li>Mark photos with the check-mark tag</li>
<li>Run the <a href="http://public.me.com/mroutley">image2web</a> script</li>
<li>Past the clipboard to <a href="http://blapp.sourceforge.net/">Blapp</a>
</li>
<li>Publish the weblog</li>
</ol>
<p>This script requires both <a href="http://www.imagemagick.org/">ImageMagick</a> and <a href="http://www.panic.com/transmit/">Transmit</a> and is inspired by a script from <a href="http://waferbaby.com/archives/2005/02/17/transmit3">waferbaby</a>.</p>