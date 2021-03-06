---
title: Nuxeo Adobe CC Connector
review:
    comment: ''
    date: '2015-12-01'
    status: ok
toc: true
labels:
    - content-review-lts2016
confluence:
    ajs-parent-page-id: '16089349'
    ajs-parent-page-title: Nuxeo Add-Ons
    ajs-space-key: NXDOC
    ajs-space-name: Nuxeo Platform Developer Documentation
    canonical: Nuxeo+Adobe+CC+Connector
    canonical_source: 'https://doc.nuxeo.com/display/NXDOC/Nuxeo+Adobe+CC+Connector'
    page_id: '31686663'
    shortlink: B4DjAQ
    shortlink_source: 'https://doc.nuxeo.com/x/B4DjAQ'
    source_link: /display/NXDOC/Nuxeo+Adobe+CC+Connector
tree_item_index: 900
history:
    -
        author: Anne Jubert
        date: '2016-09-05 14:35'
        message: ''
        version: '20'
    -
        author: Solen Guitter
        date: '2016-09-05 10:24'
        message: ''
        version: '19'
    -
        author: Solen Guitter
        date: '2016-09-05 10:23'
        message: ''
        version: '18'
    -
        author: Solen Guitter
        date: '2016-09-05 10:23'
        message: ''
        version: '17'
    -
        author: Solen Guitter
        date: '2016-09-05 10:22'
        message: ''
        version: '16'
    -
        author: Solen Guitter
        date: '2016-09-05 10:21'
        message: ''
        version: '15'
    -
        author: Solen Guitter
        date: '2016-09-05 09:07'
        message: ''
        version: '14'
    -
        author: Anne Jubert
        date: '2016-09-02 13:32'
        message: ''
        version: '13'
    -
        author: Andrei Nechaev
        date: '2016-09-02 13:25'
        message: ''
        version: '12'
    -
        author: Anne Jubert
        date: '2016-09-02 12:43'
        message: ''
        version: '11'
    -
        author: Anne Jubert
        date: '2016-09-02 12:42'
        message: ''
        version: '10'
    -
        author: Anne Jubert
        date: '2016-09-02 12:39'
        message: ''
        version: '9'
    -
        author: Anne Jubert
        date: '2016-09-02 12:29'
        message: ''
        version: '8'
    -
        author: Anne Jubert
        date: '2016-09-02 12:24'
        message: ''
        version: '7'
    -
        author: Anne Jubert
        date: '2016-09-02 12:13'
        message: ''
        version: '6'
    -
        author: Anne Jubert
        date: '2016-09-02 10:14'
        message: ''
        version: '5'
    -
        author: Anne Jubert
        date: '2016-09-02 09:56'
        message: ''
        version: '4'
    -
        author: Anne Jubert
        date: '2016-06-30 11:31'
        message: ''
        version: '3'
    -
        author: Anne Jubert
        date: '2016-06-30 11:29'
        message: ''
        version: '2'
    -
        author: Anne Jubert
        date: '2016-06-30 10:39'
        message: ''
        version: '1'

---
![]({{file name='NuxeoCCConnector.png'}} ?w=200,h=303,border=true,align=center)

The [Nuxeo Adobe CC Connector addon](https://connect.nuxeo.com/nuxeo/site/marketplace/package/nuxeo-cc-connector-marketplace) enables designers to import assets into an InDesign, Photoshop or Illustrator document directly from the Nuxeo repository. Link to the repository is maintained so as to facilitate updates of the referenced assets.

## Installation

Installation is made of two steps:

1.  Install the [Nuxeo Package](https://connect.nuxeo.com/nuxeo/site/marketplace/package/nuxeo-cc-connector-marketplace) available from the marketplace.
2.  Install the client side plugin. It is available as a zip on the marketplace page. Unzip the client side plugin in the following location:&nbsp;
    *   On OS X, into `~/Library/Application\ Support/Adobe/CEP/extensions`. We recommend you remove the previous client-side extensions/files. Be sure to close, then open the applications if you had them opened before installing the update.
    *   In your Window/extensions view in the Creative suite, you will now see a "Nuxeo CC" option.

A new extension "Nuxeo CC Connector" is now available on your Photoshop, InDesign or Illustrator Application.

## Configuration

A connection to your Nuxeo server must be implemented. Go to the settings part of the connect and fill the following information:&nbsp;

*   Choose between HTTP and HTTPS
*   Type your Nuxeo server address: [http://localhost:8080/nuxeo](http://localhost:8080/nuxeo)&nbsp;for example
*   Type your login and password

## Functional Overview

### Assets Listing View

By default, all assets with the facet "Picture" will be displayed, with a maximum of 35 by default.

Each displayed asset comes with a **card view** containing:

*   The thumbnail of the asset
*   Customized information: filename, format and modification date.
*   For Photoshop so far: a green checkbox added when the document is already placed on the current project

You can **search** for assets, using one of the following options:

*   &nbsp;On document title: only documents with the keyword in their title are returned.
*   On folder title: Search results show all the assets located in folders whose title matches the keyword.

![]({{file name='NuxeoCCConnector_search.png'}} ?w=600,h=506,border=true)

### Asset View

When selecting an asset, you are redirected to the asset view, that shows the following information:&nbsp;

*   The asset thumbnail
*   The asset filename with a link: It enables the user to directly open the asset on the Nuxeo instance
*   The same customized fields as on the document listing view: Format and modification date

![]({{file name='NuxeoCCConnector_assetView.png'}} ?w=400,border=true)

### Update / Place / Synchronization

Depending on the Adobe application some actions are available on the asset view:

*   On **Photoshop**: "Open", "Update" or "Delete" pictures/PSD projects
*   On **InDesign** and **Illustrator**: "Place" pictures.&nbsp;

Updated documents in the Nuxeo instance or in an Adobe application will be replicated everywhere. A red icon indicates that synchronization to the server has to be done.

![]({{file name='NuxeoCCConnector_sync_required.png'}} ?w=400,h=376,border=true)

&nbsp;

{{! Don't put anything here. }}

* * *

<div class="row" data-equalizer data-equalize-on="medium"><div class="column medium-6">{{#> panel heading='Related Documentation'}}

*   [Digital Asset Management (DAM)]({{page page='digital-asset-management-dam'}})

{{/panel}}</div><div class="column medium-6">

&nbsp;

</div></div>
