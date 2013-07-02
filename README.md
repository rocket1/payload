payload
=======

payload -- cloud enabled content binding with dead simple setup

Sometimes a developer is tasked with making an existing static site CMS-enabled.

Often times the client wants to be able to update very simple data such as bios, menus, events, images, etc.

These examples are mostly simple text, tablular data, or lists.

Without the luxury of having built the site from the ground up, the options are pretty bleak.

Usually you are faced with:

  1. Manually updating the site yourself, or trusting the client with the raw files.
  2. Migrating the site to a framework, like Wordpress, then train the client in the ways of the CMS editor.
  3. Writing an ad hoc solution.
  4. Using one of the minimal CMS frameworks out there.  This is a good option to consider.

The goal of this project is:

  1. Allow the developer to easily create a custom CMS for the client that show *only* the exact fields to fill in.
  2. Require the utmost minimal additions to existing codebase.
  3. Complete history of all changes to all content fields.

Here is the basic flow:

  1. Customer requests that an area of the site needs to be periodically updated.
  2. The developer goes to payloadcms.com and creates an account.
  3. The developer creates a CMS instance (basically a project) for the target site.
  4. Using a form editor and other slick tools, they create a form for the client to fill in. This form has ONLY exactly what the customer needs to fill in.
  5. The developer select a theme for the CMS and a username/password for the client.
  6. The client can update the content in a choice of plain text, markdown, raw HTML.  
  7. The system will generate an id for you for *each* field, like PayloadAboutUsTextarea.
  8. Now, in each .html, .php, etc page that the client wants editable the developer must put a script tag that is also generated by the Payload sytem. Something like:

    &lt;script src='www.payload-cms.com/FHj64FnbcHJHjkfUHHgqlkaPO6icoBFj' type='text/javascript' &gt; &lt;/script&gt;

  9. The system will give a preview of the html for each field that the dev should copy paste in the client's code.. something like this:
  
     &lt;div data-payload-id='PayloadAboutUsTextarea'&gt;&lt;/div&gt;.



That's it! So now when the clients page is hit, the Payload javascript file is loaded that corresponds to this client's data.

The script will attempt to load the data first from local storage.

If it can't find it there, or it is expired, it will fetch the content from the payload servers.

When the script has the content, it will find the appropriate div and dynamically fill in the content.





