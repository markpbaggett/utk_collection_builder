Adding Original Content to CollectionBuilder
============================================

Outcomes
--------

* Understand how CollectionBuilder reads in metadata and content
* Understand the types of content you can host with CollectionBuilder
* Understand expectations for metadata and file structure
* Understand how to replace the built-in content with your own

CollectionBuilder-GH Content
-------------------------

CollectionBuilder-GH is designed for small collections. A GitHub repository can only be 1GB in size, so this limits not only
how many items a collection may have, but also the types of files a collection may contain.

CollectionBuilder-GH supports a small set of object types including jpg, png, pdf, and mp3, plus externally hosted items
via YouTube, Vimeo, and external links. With the exception of YouTube, Vimeo, and external links, all object files are placed in the
:code:`objects` folder directly in your project repository and will be committed to GitHub. No access derivatives will be generated,
meaning the full sized objects you add to the project will be displayed on web pages through out the site. It also means
no thumbnails will be created for non-image items.

If you have needs for bigger collections or derivative generation, you can migrate your CollectionBuilder-GH site to
CollectionBuilder-CSV at a later date.

Guidelines for CollectionBuilder-GH Content
-------------------------------------------

* **Supported formats**: jpg, png, pdf, mp3 – plus YouTube, Vimeo, and external links, but you won’t have objects for those!
* **File size**: since there are no thumbnails generated, keep your object files at a reasonable size for access on the web. This means you will usually not be using your full resolution versions! For example, jpeg images of about 1200px wide and PDFs less than 1 MB will work well. Larger objects (especially images) will slow load times and make your users download unnecessarily large data–so keep them to a web friendly size!
* **Total size**: GitHub repositories have soft limits on total size, some where around 1 GB. A good rule of thumb is to keep your “objects” folder less than 500 MB.
* **Filenaming**: to avoid issues, please pay close attention to filenaming conventions! The filename should be an all lowercase unique string with no spaces or special characters. Underscores (_) are okay. You will use the exact filenames (including extension and same case) to populate the “filename” field of your collection metadata.

Adding Sample Objects to Our GitHub Repository
----------------------------------------------

To save time, I've pulled together some sample objects to use in our demo collection. You can download the zip file
`here <>`_.

Now, we're going to extract this zip file and add the contents to our GitHub repository.

To do this, we need to open the zip file and extract the contents. On a Mac, you can double click the zip file to open
and extract it.  On Windows, you can right click the zip file and select "Extract All".

Next, we're going to navigate to the :code:`objects` directory in our GitHub repository. This is the repository where
you can add the files you want to host in your project if you are not using external links, youtube, or vimeo.

Now, in our GitHub repository, we're going to click **Add File** and select **Upload Files**. Now drag each of the files
you just extracted to your repository.

You may notice that there are a few demo files, but let's leave them there for now. They won't show up in our collection
unless we add them to our metadata.

Finally, ccroll down to the “Commit changes” box, write a short commit message in the form (an appropriate message might
be “add collection objects to project”), then click the green “Commit changes” button to add them to your repository.

Adding Metadata about Our Objects
---------------------------------

CollectionBuilder-GH reads in metadata from a comma separated file (CSV). The CSV file can be named whatever you want,
but it must be a CSV file.

Once you've written your metadata, you can upload it to your GitHub repository to the :code:`_data` directory similarly
to how we added our objects.

Before we add our metadata, let's take a look at the prescribed metadata structure for CollectionBuilder-GH.

CollectionBuilder Metadata Application Profile
----------------------------------------------

CollectionBuilder is prescriptive when it comes metadata. Without extensive customization, each project must
have specific fields in order for the collection to work properly.

========
Required
========

For CollectionBuilder-GH, each row must have 4 fields.  All collections should have the following 3 fields:

* **objectid**: This is the field that CollectionBuilder uses to identify each object. This should be a unique string,
  all lowercase with no spaces or special characters as it will be used to form the item’s URL. Underscores (_) and
  dashes (-) are okay; slashes (/) should NOT be used in this field.
* **title**: The title field is used to indicate the name of an item. This should be a short, descriptive set of words
  that identify the item. Each item may only have one title.
* **format**: This field indicates the item’s media type. Since CollectionBuilder uses logic based on format to display
  objects, this is the most important field to ensure the interactive visualizations function correctly. If there are
  errors or anomalies, some pages will not work. The input for this field should be structured according to MIME type
  standards, consisting of a type and a subtype concatenated with a slash (/) between them.

Collections should also have at least 1 of the following fields but can have all 3 if you're using mixed content:

* **filename**: The digital object’s filename including the file extension, or a full URL to a file hosted external to
  your project. The value must exactly match the actual filename of the file in your “objects” directory, including the
  case of the filename and file extension. Most web servers are case sensitive, so make sure everything matches! If you
  are using an external link instead of a file in the :code:`objects` directory, the URL must be a full URL including
  the protocol (http:// or https://). **Important note on external items**: URLs to external media should always be
  secure HTTPS links. Media at HTTP links are likely to be blocked by browser security defaults as mixed content.
* **youtubeid**: This is the unique string assigned to a video when it is uploaded to YouTube. An easy way to find this is
  to look at the url for your YouTube video. The ID will be the string attached to the end of the url. For example, in
  “https://www.youtube.com/watch?v=sHhk1eAgopU” the youtubeid is :code:`sHhk1eAgopU`.
* **vimeoid**: This is the unique string assigned to a video when it is uploaded to Vimeo. An easy way to find this is
  to look at the url for your Vimeo video. The ID will be the string attached to the end of the url. For example, in
  “https://vimeo.com/464555587” the vimeoid is :code:`464555587`.

===========================
Required for Visualizations
===========================

CollectionBuilder uses these fields to generate contextual visualizations, including a map, timeline, and word clouds
reflecting the frequency of subjects and locations in a collection.

* **latitude**:  A geographic coordinate specifying the north-south position of an item.
* **longitude**: A geographic coordinate specifying the east-west position of an item.
* **date**: This field indicates a point in time associated with the item. This date field will be used for sorting and
  displaying on a timeline, so may often be an estimated / approximate date, rather than one more precisely formatted to
  archival description standards. We suggest adding more complex descriptions of date (date ranges, uncertainties, etc)
  in a separate field such as “date_created”. Dates should be represented in the format :code:`yyyy-mm-dd`, which will enable
  our various timeline visualizations. See the Timeline section for more details. For less exact dates, :code:`yyyy-mm`
  or :code:`yyyy` may be used.
* **subject**: The subject field contains topic(s) related to the item. This field allows for multiple subjects to be
  input for a single record. Each should be separated with a semicolon (:code:`;`).
* **location**: This field designates a geographic location(s) to which the item is tied. Much like the subject field,
  this field will build a tag cloud of the most used locations in your collection. See the Locations section for more
  information. Be sure to separate multiple location entries for a single record with a semicolon (:code:`;`).


==========================================
Optional Fields that Work "Out of the Box"
==========================================

The rest of the fields in the CollectionBuilder metadata template are not required for CollectionBuilder or its
visualizations to work, but their use is encouraged to ensure a richly informative collection. Also, while you can add
any field you want to your metadata it will require you to customize some things in order to get that value to show.

These optional values will appear without any extra work:

* **creator**: The creator property designates an entity primarily responsible for making the resource.
  Multiple creators may be input, as long as each is separated by a semicolon (:code:`;`).
* **description**: The description should be a brief account of the object. Each object should only have one description.
* **source**: The source field designates a related source collection or resource from which the object is derived.
  This field is especially relevant for digitized archival collections. In such a situation, the name of the physical
  archival collection would be the input for this field. The input should be expressed as the collection name followed
  by a comma, then followed by the holding library.
* **identifier**: The identifier field is used to preserve the unique identifier assigned to the object by the object’s
  (usually physical) source collection.
* **type**: An object’s type distinguishes between types of image, sound, text, etc. using a one- or two-value input.
  At minimum, the input should contain a value chosen from the DCMI Type Vocabulary. If using a second value, the second
  value does not need to relate to a controlled vocabulary, but should give further specification of the object type.
  The two values in a pair should be separated by a semicolon (;).
* **language**: This field indicates the language associated with the object. Recommended best practice is to use a
  controlled vocabulary such as the ISO 639-2 Codes for the Representation of Names and Languages to designate language
  tags.
* **rights**: The rights field should include a free-text rights statement describing information about rights held in and over the object.
* **rightsstatement**: This field is a standardized rights statement, designated in the form of a URI. It should be
  presented as a creativecommons.org URI or a rightsstatements.org URI.

Editing Metadata
----------------

