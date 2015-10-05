YouNote Desktop is the tool for backuping your notes but can also help you to get the content of your notes.

All your notes are contained in folders stored in your backup folder. To open a archive (aka the folder), you can navigate in your system or more easily, you can use the contextual menu in YouNote Desktop. To do that, select an archive in the list then use the contextual menu and select the item "Open".

This function will open the associated folder.

But before analyzing the content of an archive, some words about your backup folder.

**Organisation of a backup folder**

The top level is the name of the folder you set up in your preferences, for example YouNoteBackup. In this folder, if you have a single iPhone/iPod Touch, you'll find a folder like cc8684e94cbe6abbf13d1b74f532e296748e0af6. It's the ID of your iPhone called UDID (unique device identifier)  If you have 2 or more devices, you'll find 2 or more folders. And finally, you'll find the list of your archives.

In summary, you have:
  * the main folder
  * one folder per device
  * the list of archives

**Content of an archive**
An archive is a folder with the same name as the archive (it's the folder name actually). In this folder, you see a list sub folders (a sub folder is a note).

A note folder contains:
  * metadata.xml file (always)
  * text.txt if there is a note description
  * media.jpg if it's a PictNote or a WebNote
  * media.caf if it's an AudioNote
  * media.png if it's a DrawNote
  * inner folders if it's a MultiNote

Now, with this informations, you can easily grab the content of your notes.

**Content of the metadata.xml file**

Some of you are maybe more curious. So let me explain what you can find in this file.

You can open it with any text editor. It contains all the useful informations that YouNote needs. This informations are:
  * ID
  * type (AudioNote, TextNote, ...)
  * title
  * creation date
  * modification date
  * list of tags
  * list of contacts
  * location
  * color
  * url (for a WebNote)

Example:
```
<?xml version="1.0" encoding="UTF-8"?>
<note id="8" type="3">
  <version>1.0.2</version>
  <title>Spanish white wine - Marina Alta</title>
  <creationDate>20120816T151305055+0200</creationDate>
  <modificationDate>20120917T153653455+0200</modificationDate>
  <tags/>
  <Contacts/>
  <geolocalisation>
    <latitude>39.471892</latitude>
    <longitude>-0.368772</longitude>
    <altitude>70.000000</altitude>
  </geolocalisation>
  <color>
    <red>0</red>
    <green>0</green>
    <blue>0</blue>
  </color>
  <url></url>
</note>
```