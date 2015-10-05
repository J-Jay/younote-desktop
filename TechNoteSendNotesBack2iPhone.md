# Introduction #

In this technote, we will explain how you can modify or create new note and send back to your iPhone

**Caution:** make a copy of your last archive before any change. YouNote could stop to work correctly if the data are corrupted.

**Rule to follow**: a backup archive is a folder with notes inside. The folder name must be like YouNote\_bck\_20121228\_131347 (yyyymmdd\_hhmmss). This constraint may change in the future.

The principle is the following:
  1. Make a copy of the selected archive just in case
  1. apply your modifications
  1. transfert your notes on your iPhone/iPod touch by choosing "Restore" on your iPhone

# How modifying the content of a note ? #
Each note is a folder. The folder name is just to help you to recognize the notes. It's composed of the ID and the title. The name of this folder doesn't matter.

What can you modify ?
  * modify the content of a note (TextNote, PictNote,...)
  * reorganize MultiNotes

## Content modification ##
First we will see how you can modify the content.

A folder (aka a note) contains at least 2 files:
  * metadata.xml
  * text.txt

The metadata.xml file contains:

  * unique ID of the note
  * type (AudioNote, TextNote, ...)
  * title of the note
  * creation date
  * modification date
  * list of tags
  * list of contacts (list of (id, firstname, lastname))
  * location (latitude, longitude, altitude)
  * color (RGB)
  * url (for a WebNote)

The different note types are:
  * 0 = MultiNote
  * 1 = TextNote
  * 2 = AudioNote
  * 3 = PictNote
  * 4 = DrawNote
  * 5 = WebNote
  * 6 = VideoNote

The available colors are:
  * red: (R=201 G=5 B=25)
  * orange: (R=246 G=173 B=1)
  * yellow: (R=255 G=230 B=0)
  * green: (R=119 G=185 B=19)
  * blue: (R=112 G=212 B=229)
  * purple: (R=115 G=77 B=149)
  * gray: (R=100 G=100 B=100)
  * black: (R=0 G=0 B=0)

The format of the creation and modification date follows the international standard for date and time representation ISO 8601. http://en.wikipedia.org/wiki/ISO_8601<br>
Example: 20121228T170635845+200 is 28 December 2012 5:06:35,845 +0200 pm<br>
<br>
The text.txt file contains the text you typed when you created a TextNote. It also contains the comment you may have in any other note (AudioNote, WebNote, PictNote, ..;)<br>
<br>
Which files can you modify?<br>
<ul><li>TextNote: text.txt (UTF-8 encoding)<br>
</li><li>PictNote: media.jpg<br>
</li><li>DrawNote: media.png<br>
</li><li>WebNote: media.jpg<br>
</li><li>AudioNote: media.caf</li></ul>

<b>Caution:</b> the jpg or png file size must be reasonnable, aka Apple recommends that the size of the picture doesn't exceed 600x600 pixels. YND doesn't make any control of the size of the picture.<br>
<br>
<b>Note:</b> if you change the tags (adding or removing tags), the list of tags will be rebuilt automatically when you import the modified backup into YouNote. Of course, don't forget to modify manually every note linked to the tags you modify.<br>
<br>
Moreover, don't put any other file in a folder/note. At least, il will be ignored or the restoration could fail.<br>
<br>
<h2>What about the MultiNotes?</h2>
A MultiNote is a bit more complex. As every note, there are:<br>
<ul><li>metadata.xml<br>
</li><li>text.txt<br>
plus some sub folders where each sub folder is a inner note. However, an inner note is exactly the same as a "normal" note.</li></ul>

<h3>Transform an inner note in a normal note</h3>
You can transform an inner note in a "normal" note. To do that you just need to drag and drop the folder/inner note to the highest level.<br>
Note that the reciprocal is true and easy as well.<br>
<br>
<h3>Move an inner note</h3>
You can move an inner note from one MultiNote to another one by just drag and drop it. Suppose you have:<br>
<br>
Folder MultiNote A<br>
<ul><li>inner note A1<br>
</li><li>inner note A2</li></ul>

Folder MultiNote B<br>
<ul><li>inner note B1</li></ul>

If you want to move A2 into B, just drag and drop the folder A2 into B<br>
<br>
<h1>How adding new note ?</h1>
This part is more tricky because you must create:<br>
<ul><li>a folder for the new note<br>
</li><li>a metadata.xml file<br>
</li><li>a text.txt file</li></ul>

For technical reasons, the folder title must begin with an ID, the note type then a title (whatever you want). The ID/type note <b>must be unique.</b>

It's easier with an example of the creation of a TextNote with a simple content: "Hello world" with the same title, a color red and a tag "example".<br>
<br>
Suppose we have a folder called <b>"YouNote_bck_20121107_124717"</b>. In this folder, create a sub folder called "6000_TextNote_MyFirstNewNote" where 6000 is the unique ID (if you have less than 6000 notes, it will be good ;-)), TextNote because it's a TextNote then a title (note that this title is ignored by the restore process).<br>
<br>
Then you must create a metadata.xml file.The best way is to create a template somewhere then make a copy. Set all attributes you want (title, creation date, modification date, …) but pay attention to the:<br>
<ul><li>ID<br>
</li><li>type of the note</li></ul>

In our example, we want to create a TextNote so the type is 1. Pretty simple.<br>
<br>
About the ID, you can type any value you want because YouNote recreates ID when it restores your notes. So you can set a very high ID, for example, 1000.<br>
<br>
Finally the metadata.xml file is:<br>
<pre><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;<br>
&lt;note id="99" type="1"&gt;<br>
  &lt;version&gt;1.0.2&lt;/version&gt;<br>
  &lt;title&gt;Hello world&lt;/title&gt;<br>
  &lt;creationDate&gt;20121130T084130874+0200&lt;/creationDate&gt;<br>
  &lt;modificationDate&gt;20121130T152929482+0200&lt;/modificationDate&gt;<br>
  &lt;tag&gt;example&lt;/tag&gt;<br>
  &lt;Contacts/&gt;<br>
  &lt;geolocalisation&gt;<br>
    &lt;latitude&gt;0&lt;/latitude&gt;<br>
    &lt;longitude&gt;0&lt;/longitude&gt;<br>
    &lt;altitude&gt;0&lt;/altitude&gt;<br>
  &lt;/geolocalisation&gt;<br>
  &lt;color&gt;<br>
    &lt;red&gt;201&lt;/red&gt;<br>
    &lt;green&gt;5&lt;/green&gt;<br>
    &lt;blue&gt;25&lt;/blue&gt;<br>
  &lt;/color&gt;<br>
  &lt;url&gt;&lt;/url&gt;<br>
&lt;/note&gt;<br>
</code></pre>
To create the text.txt, file, you can use any text editor like Notepad, TextEdit, ...<br>
<br>
The content of the file text.txt is simply: Hello world. Don't forget that the encoding must be UTF-8.<br>
<br>
That's it.<br>
<br>
<b>Tip:</b> the safer way is to create an empty note on your iPhone then backup your notes so you can apply the above method.