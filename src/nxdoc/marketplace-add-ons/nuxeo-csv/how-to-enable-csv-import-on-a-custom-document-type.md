---
title: How to Enable CSV Import on a Custom Document Type
review:
    comment: ''
    date: ''
    status: ok
details:
    howto:
        excerpt: >-
            If you installed the Nuxeo CSV add-on from the Nuxeo Marketplace,
            you'll probably want to enable CSV import on the document types you
            defined. Here is how to do that. 
        level: Beginner
        tool: Studio
        topics: 'Document type, Nuxeo CSV'
labels:
    - nuxeo-csv
    - howto
confluence:
    ajs-parent-page-id: '22380737'
    ajs-parent-page-title: Nuxeo CSV
    ajs-space-key: NXDOC60
    ajs-space-name: Nuxeo Platform Developer Documentation — 6.0
    canonical: How+to+Enable+CSV+Import+on+a+Custom+Document+Type
    canonical_source: >-
        https://doc.nuxeo.com/display/NXDOC60/How+to+Enable+CSV+Import+on+a+Custom+Document+Type
    page_id: '22380837'
    shortlink: JYFVAQ
    shortlink_source: 'https://doc.nuxeo.com/x/JYFVAQ'
    source_link: /display/NXDOC60/How+to+Enable+CSV+Import+on+a+Custom+Document+Type
history:
    - 
        author: Solen Guitter
        date: '2014-12-01 22:30'
        message: ''
        version: '13'
    - 
        author: Solen Guitter
        date: '2014-11-28 18:05'
        message: ''
        version: '12'
    - 
        author: Solen Guitter
        date: '2014-11-28 00:57'
        message: ''
        version: '11'
    - 
        author: Solen Guitter
        date: '2014-11-28 00:56'
        message: ''
        version: '10'
    - 
        author: Solen Guitter
        date: '2014-09-16 16:18'
        message: ''
        version: '9'
    - 
        author: Solen Guitter
        date: '2014-06-12 15:03'
        message: ''
        version: '8'
    - 
        author: Solen Guitter
        date: '2013-12-13 18:09'
        message: ''
        version: '7'
    - 
        author: Solen Guitter
        date: '2013-12-13 18:08'
        message: ''
        version: '6'
    - 
        author: Solen Guitter
        date: '2013-12-13 18:02'
        message: ''
        version: '5'
    - 
        author: Solen Guitter
        date: '2013-12-13 17:48'
        message: Added related content
        version: '4'
    - 
        author: Solen Guitter
        date: '2013-12-13 17:46'
        message: ''
        version: '3'
    - 
        author: Solen Guitter
        date: '2013-12-12 11:32'
        message: >-
            Use several <type> tags instead of <rule> to enable CSV import on
            several doc types 
        version: '2'
    - 
        author: Solen Guitter
        date: '2013-12-12 11:02'
        message: ''
        version: '1'

---
{{{excerpt 'NXDOC:Nuxeo CSV'}}}

{{! excerpt}}

If you installed the Nuxeo CSV add-on from the Nuxeo Marketplace, you'll probably want to enable CSV import on the document types you defined, either in Studio or with some code. Here is how to do that.

{{! /excerpt}}

1.  In [Studio]({{page space='studio'}}), in the **Advanced Settings** menu, click on **XML Extensions**.
2.  Click on **New** to create a new extension.
3.  Give it an ID and click on **Next**.

    {{#> callout type='tip' }}

    You may want to check the [Studio naming conventions]({{page space='studio' page='naming-conventions'}}).

    {{/callout}}
4.  Paste the following content in the text area and fill in the&nbsp;`<type>` tag with the ID of the document type on which you want to enable CSV import.

    ```xml
    <require>org.nuxeo.ecm.platform.actions</require>
    <extension target="org.nuxeo.ecm.platform.actions.ActionService"
      point="filters">
      <filter id="importFile" append="true">
        <rule grant="true">
          <permission>AddChildren</permission>
          <type>YourCustomTypeID</type>
        </rule>
      </filter>
    </extension>
    ```

5.  In the XML extension, put as many&nbsp;`<type>` tags as documents types on which CSV import should be enabled.
6.  Click on **Save**.
    After you update your Nuxeo Platform instance, your document type(s) will have the **Import a CSV file** button.

{{#> callout type='tip' }}

If you don't want to use Studio and prefer using your IDE, you can just [add a contribution]({{page page='contributing-to-an-extension-using-nuxeo-ide'}}) with the XML above.

{{/callout}}

&nbsp;

* * *