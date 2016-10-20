---
title: User Actions
review:
    comment: ''
    date: ''
    status: ok
labels:
    - user-action
    - content-review-6-0
toc: true
confluence:
    ajs-parent-page-id: '12911806'
    ajs-parent-page-title: Automation
    ajs-space-key: Studio
    ajs-space-name: Nuxeo Online Services
    canonical: User+Actions
    canonical_source: 'https://doc.nuxeo.com/display/Studio/User+Actions'
    page_id: '14256432'
    shortlink: MInZ
    shortlink_source: 'https://doc.nuxeo.com/x/MInZ'
    source_link: /display/Studio/User+Actions
tree_item_index: 100
history:
    -
        author: Solen Guitter
        date: '2016-08-30 13:31'
        message: ''
        version: '13'
    -
        author: Manon Lumeau
        date: '2016-04-28 13:16'
        message: 'Fix Studio menu label     '
        version: '12'
    -
        author: Manon Lumeau
        date: '2015-03-12 09:50'
        message: ''
        version: '11'
    -
        author: Solen Guitter
        date: '2015-01-26 17:20'
        message: ''
        version: '10'
    -
        author: Solen Guitter
        date: '2014-03-10 17:50'
        message: ''
        version: '9'
    -
        author: Solen Guitter
        date: '2014-01-13 10:36'
        message: ''
        version: '8'
    -
        author: Solen Guitter
        date: '2013-07-17 14:42'
        message: ''
        version: '7'
    -
        author: Bertrand Chauvin
        date: '2013-07-11 19:44'
        message: ''
        version: '6'
    -
        author: Bertrand Chauvin
        date: '2013-07-11 19:42'
        message: ''
        version: '5'
    -
        author: Bertrand Chauvin
        date: '2013-07-11 19:42'
        message: ''
        version: '4'
    -
        author: Bertrand Chauvin
        date: '2013-07-11 19:38'
        message: ''
        version: '3'
    -
        author: Bertrand Chauvin
        date: '2013-07-11 19:38'
        message: ''
        version: '2'
    -
        author: Bertrand Chauvin
        date: '2013-07-11 19:36'
        message: ''
        version: '1'

---
## Concept

User actions are meant to execute a predefined action or list of actions (namely an operation chain) when clicking on a link or button. You can read more about them in the [developers section]({{page space='nxdoc' page='actions-links-buttons-icons-tabs-and-more'}}).

## Creating a User Action

![]({{file name='creating-user-action-form.png'}} ?w=300,h=293,border=true)

&nbsp;

*   **`Feature ID`** : the unique id of the user action.
*   `**Label**` : the name that will be displayed on screen.
*   `**Category**` : defines where the action will be placed on screen. Note that certain categories only appear in specific screens; for instance the "Document creation form" category will only be visible on document creation.

## Editing a User Action

### Action Definition

![]({{file name='action-definition.png'}} ?w=300,h=147,border=true)

*   `**Order**` : set a higher value to move the action further to the right. Default actions order starts at 10.
*   **`Immediate`** : checking this box will cause the action to be executed without prior validation. It is usually preferable to leave it unchecked.

### Action Activation

![]({{file name='action-enablement.png'}} ?w=350,border=true)

See the&nbsp;[Filtering Options Reference Page]({{page page='filtering-options-reference-page'}}).

### Action Execution

*   `**Select an existing operation**` : the selected automation chain will be executed when the user clicks on the action defined in the User Action definition section. The "Edit" button can be used in order to edit an existing automation chain, and the "Create" button to create a new automation chain that will be associated to this user action.

&nbsp;

* * *

<div class="row" data-equalizer data-equalize-on="medium"><div class="column medium-6">{{#> panel heading='Related pages in Studio documentation'}}

*   [User actions categories]({{page page='user-actions-categories'}})

{{/panel}}</div><div class="column medium-6">{{#> panel heading='Related pages'}}

*   [Actions Overview]({{page space='nxdoc' page='actions-overview'}})
*   [Action How-To Index]({{page space='nxdoc' page='action-how-to-index'}})

{{/panel}}</div></div>