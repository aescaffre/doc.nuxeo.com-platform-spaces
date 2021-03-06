---
title: How to Translate a Vocabulary
review:
    comment: ''
    date: '2015-12-01'
    status: ok
details:
    howto:
        excerpt: Learn how to translate an existing vocabulary.
        level: Beginner
        tool: Studio
        topics: Vocabulary
labels:
    - content-review-lts2016
    - vocabulary
    - howto
    - excerpt
confluence:
    ajs-parent-page-id: '4688939'
    ajs-parent-page-title: Data Lists and Directories
    ajs-space-key: NXDOC
    ajs-space-name: Nuxeo Platform Developer Documentation
    canonical: How+to+Translate+a+Vocabulary
    canonical_source: 'https://doc.nuxeo.com/display/NXDOC/How+to+Translate+a+Vocabulary'
    page_id: '19793019'
    shortlink: ewQuAQ
    shortlink_source: 'https://doc.nuxeo.com/x/ewQuAQ'
    source_link: /display/NXDOC/How+to+Translate+a+Vocabulary
tree_item_index: 200
history:
    -
        author: Solen Guitter
        date: '2016-08-31 15:06'
        message: ''
        version: '12'
    -
        author: Solen Guitter
        date: '2014-12-01 21:51'
        message: ''
        version: '11'
    -
        author: Manon Lumeau
        date: '2014-09-10 14:54'
        message: ''
        version: '10'
    -
        author: Manon Lumeau
        date: '2014-09-10 14:04'
        message: ''
        version: '9'
    -
        author: Manon Lumeau
        date: '2014-09-10 12:17'
        message: ''
        version: '8'
    -
        author: Solen Guitter
        date: '2014-06-30 11:47'
        message: ''
        version: '7'
    -
        author: Solen Guitter
        date: '2014-06-30 11:43'
        message: Added save step
        version: '6'
    -
        author: Manon Lumeau
        date: '2014-06-26 18:00'
        message: ''
        version: '5'
    -
        author: Manon Lumeau
        date: '2014-06-26 17:59'
        message: ''
        version: '4'
    -
        author: Manon Lumeau
        date: '2014-06-26 17:54'
        message: ''
        version: '3'
    -
        author: Manon Lumeau
        date: '2014-06-26 17:33'
        message: ''
        version: '2'
    -
        author: Manon Lumeau
        date: '2014-06-26 16:48'
        message: ''
        version: '1'

---
{{! excerpt}}

Nuxeo Studio enables you to translate the vocabulary values of your application.

{{! /excerpt}}

By default, vocabularies are not translated. This means that if your application is available in several languages, the vocabulary's values will only be displayed in the language in which you create them in the steps above. If you filled in English values, you'll be displayed English values in the lists even if the Nuxeo Platform UI is in French or any other language. However, you can make them available in several languages.

In order to translate a vocabulary, you must:

1.  Put the labels translation in a "message_LANGUAGE.properties" file as explained on the page [Uploading Labels Translations in Studio (i18n)](/pages/viewpage.action?pageId=3867532) and upload the properties file in the **Resources** menu of Studio.
2.  Go on the layout on which the vocabulary should be used.
3.  Assign the vocabulary to a document field (see the&nbsp;[Define a Document Type]({{page space='NXDOC' page='Define a+Document+Type'}})&nbsp;how-to).
4.  On the widget's edition form, select **Yes** for Localize.
    ![]({{file name='STUDIO-layout-widget.png'}} ?w=350,h=349,border=true)

    {{#> callout type='tip' }}

    Tick **Translated** if you want to translate the label and the Help label of the field.

    {{/callout}}
5.  Save your modifications on the widget and on the layout.
    The labels displayed in the widget are now taken from the properties file. You now have different labels depending on the language the Nuxeo Platform UI is displayed in.

* * *

&nbsp;

<div class="row" data-equalizer data-equalize-on="medium"><div class="column medium-6">{{#> panel heading='Related Howtos'}}

- [How to Add a New Vocabulary]({{page page='how-to-add-a-new-vocabulary'}})
- [How to Add a New Virtual Navigation Entry]({{page page='how-to-add-a-new-virtual-navigation-entry'}})
- [How to Translate the Nuxeo Platform]({{page page='how-to-translate-the-nuxeo-platform'}})

{{/panel}}</div><div class="column medium-6">

&nbsp;

&nbsp;

</div></div>
