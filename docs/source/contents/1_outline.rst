Introduction to Collection Builder
==================================

What is CollectionBuilder?
--------------------------

`CollectionBuilder <https://collectionbuilder.github.io/>`_ is an n open source framework for creating digital collection
and exhibit websites that are driven by metadata and powered by modern static web technology. This allows you to create
a collection and host it on lightweight infrastructure, without the need for a database or server-side scripting language.

Why use CollectionBuilder?
--------------------------

The high cost and IT requirements of digital collection platforms are often a barrier to creating new collections for
sharing or teaching humanities research. CollectionBuilder is optimized for non-developers and simple hosting solutions,
allowing researchers and educators to take greater ownership over their digital projects and lowering barriers to
website customization.

Using well-structured metadata and a directory of digital files, CollectionBuilder employs a Jekyll static web generator
to create a website for visualizing, browsing, and accessing the collection.

The Original Lib-Static "Manifesto", 2018
-----------------------------------------

CollectionBuilder is very much built in the spirit of the `Lib-Static "Manifesto." <https://lib-static.github.io/community/manifesto/>`_

Lib-Static is a minimal computing-based approach to creating data-driven tools leveraging static-web technologies and
librarians’ specialized skills in metadata and classification to create engaging web publications via three components:

1. a spreadsheet with well-formed metadata
2. a directory of assets
3. and a configuration file.

Static-web technologies are a set of tools that allow for the creation of web pages without the need for a database. Examples
of static web technologies include Jekyll, Hugo, and Pelican as well as JavaScript JAM stack tools like Gatsby and Next.js.

The manifesto describes a methodology for creating web publications and applications that are:

1. Open: powered by open tools and open data.
2. Simple(ish): basic infrastructure requirements and less IT.
3. Librar* Optimized: Full control over the content and data (no 3rd parties) and leverage the skills of libraries (not coders)
4. User-focused: Engaging designs the encourage user interaction, visualization for discovery, and accessibility for all. Reusable and reshareable metadata.

Reasons for the Manifesto
-------------------------

In response to challenges and frustrations with library systems, LibStatic originators started to see that there were
ways to build these systems and tools that did not lock libraries into proprietary contracts nor lock themselves out of
the code and data driving the site’s presentation. These experiences led to a philosophy of development that leverages
the expertise of librarians and cultural heritage workers and the unique values of their institutions at the forefront
of project design decisions. This methodology differs greatly from the predominant model for platform and tool building
for academic libraries as it does not require complex infrastructure nor specialized developers to build, implement,
and maintain the systems put into use. The shift towards a focus on clean data and simple systems enables a more agile
and responsive approach, allowing the iterative development of features, gradual acquisition of developer skills, and
flexible migration between hosts without the need for deep investment.

Static Site Generators
----------------------

CollectionBuilder is built on the Jekyll static site generator.

Static Site Generators are software tools that bundle together a stack of web development packages used to transform a
directory of source code into a complete static website (i.e. a ready-to-serve folder of HTML, CSS, JSON, and JavaScript files).

These tools give you some of the power of a content management system, without all the infrastructure overhead. Static
site generators can be installed and used on your local computer, and typically feature:

* a command line interface (not GUI software).
* a builtin development server (test your site on your computer).
* simplified markup based content (e.g. write in Markdown).
* web templating language (build a site from modular components pulled together with basic logic, e.g. Liquid).
* CSS preprocessor (e.g. Sass).
* file-based data options (create content from CSVs or JSON).
* plugin extensibility (add new functionality).

What Static-Site Generators are Lack
------------------------------------

If you are familiar with using CMS such as WordPress or Drupal (or in the DH world Scalar, Omeka, Islandora, CONTENTdm),
one thing you may have noticed is missing from the static generator workflow is some sort of GUI web-based Admin
interface. There isn’t a content management system or digital asset management system or other type of dynamic web
application installed on a server that you might be used to seeing in the context of building websites.

Static generator projects are literally a folder of plaintext files. The generator is used via command line options on
your local computer or run via online build services to output a complete static site. These ready-to-serve files can be
hosted on a minimal server or free static hosting platform, yet provide high performance to users.

For Lib-Static, using static site generators allows users to create reusable, data-driven templates consisting of
modular chunks of HTML, CSS, and JavaScript. The tools bundled in the generator make it easier to write these
components, and to keep the data, content, and presentation layers cleanly separated. This organization helps ensure the
source code can be reused by others, and the investment in content and data can be preserved for the future and migrated
to other platforms.

Data and Static Site Generators
-------------------------------

Static web applications and frameworks depend on data structures and data transformations to enable their features and
utility.

Data can be structured via a variety of formats, including tabular data represented most often via CSV spreadsheets,
semi-structured data represented as JSON, and human readable key-value pairs listed in YAML files or frontmatter. These
formats are all plain text formats, and making sure that your content and files are in plain text is essential for
static sites and frameworks to operate.

Static web projects and frameworks depend on users following specific data requirements in order to make available,
via data transformation, the visualization and alternative data output features core to their use. They do so because
the features they’re building require data be ingested into their scripts or templates in specifically organized and
formatted ways in order for the visualizations to work.

Static web frameworks can enable a number of different types of visualizations and interactions, as well as a variety
of additional data outputs, by iterating over collection and configuration data. This enables a user to focus on their
collection or exhibit data as a whole rather than learning a series of specific ways of representing that data for
various scripts or presentations.

The important thing to remember in regards to a static context is that any static framework or model you might be
working on will require certain features of your data. These might include:

* specific field names
* specific ways of formatting that data (lowercase, delimiting, no spaces, specific technologies)


Data Transformation as Preservation Practice
--------------------------------------------

Many static projects and frameworks, especially those coming out of the library world, use this inherent data
transformation ability to provide project data in a variety of open formats. For instance, CollectionBuilder
(following the #collectionsasdata mantra) provides digital collection data in several different formats, including CSV
and JSON files that present the entirety of the collection to GEOJSON files of just those items that have latitude and
longitude to enable reuse in various mapping applications.

This transformational ability allows project/collection data:

* to be reused in a variety of contexts;
* to be preserved in open, reusable formats going forward;
* and to enable certain machine learning and indexing functions,
* such as providing structured data in the “<head>” of html files to allow for better discovery via Google and other search engines.)

CollectionBuilder Documentation
-------------------------------

Before we get started, I just want to give you a brief introduction to the CollectionBuilder documentation.

The CollectionBuilder team has excellent documentation on the project website that is very robust.

It's organized on the left-hand side in a number of sections and is curated in order to the steps you'd go through to build
a collection yourself.

While every step we're going to cover today is handled in the documentation packet I put forth for this workshop, we only
have one hour and are likely to not get to all your questions.  In the case where I don't cover something, that item
is likely covered here.

One thing in particular to note is that there are three versions of CollectionBuilder, and the version we are using is
**CollectionBuilder GH**. GH stands for GitHub pages which is the mechanism we will be using for hosting our collection.

In the documentation sections for both objects and metadata, there are separate sections for each version of CollectionBuilder
so make sure you are using GH.

There is a search function here for you to use as well as a glossary of terms in case there is anything I say that doesn't
quite make sense that you want to reference.
