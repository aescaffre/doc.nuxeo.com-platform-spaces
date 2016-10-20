---
title: Node General tab
review:
    comment: ''
    date: ''
    status: ok
labels:
    - 5-7-2
    - node
    - content-review-6-0
confluence:
    ajs-parent-page-id: '11534824'
    ajs-parent-page-title: Node popup
    ajs-space-key: Studio
    ajs-space-name: Nuxeo Online Services
    canonical: Node+General+tab
    canonical_source: 'https://doc.nuxeo.com/display/Studio/Node+General+tab'
    page_id: '11534830'
    shortlink: 7gGw
    shortlink_source: 'https://doc.nuxeo.com/x/7gGw'
    source_link: /display/Studio/Node+General+tab
tree_item_index: 100
history:
    -
        author: Solen Guitter
        date: '2013-10-21 14:56'
        message: ''
        version: '24'
    -
        author: Alain Escaffre
        date: '2013-10-20 00:31'
        message: ''
        version: '23'
    -
        author: Alain Escaffre
        date: '2013-10-20 00:26'
        message: ''
        version: '22'
    -
        author: Solen Guitter
        date: '2013-07-24 16:51'
        message: ''
        version: '21'
    -
        author: Solen Guitter
        date: '2013-07-24 16:47'
        message: Fixed screenshots
        version: '20'
    -
        author: Frédéric Vadon
        date: '2013-07-23 00:31'
        message: Exclusive Node Added
        version: '19'
    -
        author: Alain Escaffre
        date: '2013-07-11 01:34'
        message: ''
        version: '18'
    -
        author: Karl Harris
        date: '2013-07-03 14:40'
        message: ''
        version: '17'
    -
        author: Solen Guitter
        date: '2013-07-01 11:07'
        message: Added links and fixed typos
        version: '16'
    -
        author: Alain Escaffre
        date: '2013-06-30 22:15'
        message: ''
        version: '15'
    -
        author: Alain Escaffre
        date: '2013-06-30 21:58'
        message: ''
        version: '14'
    -
        author: Alain Escaffre
        date: '2013-06-30 21:58'
        message: ''
        version: '13'
    -
        author: Solen Guitter
        date: '2013-05-23 10:05'
        message: ''
        version: '12'
    -
        author: Solen Guitter
        date: '2013-05-23 10:05'
        message: ''
        version: '11'
    -
        author: Solen Guitter
        date: '2013-05-23 10:01'
        message: ''
        version: '10'
    -
        author: Solen Guitter
        date: '2013-05-22 18:48'
        message: ''
        version: '9'
    -
        author: Solen Guitter
        date: '2013-05-22 18:47'
        message: Resized screenshots
        version: '8'
    -
        author: Alain Escaffre
        date: '2013-04-22 11:43'
        message: ''
        version: '7'
    -
        author: Mariana Cedica
        date: '2013-03-28 11:09'
        message: ''
        version: '6'
    -
        author: Alain Escaffre
        date: '2013-03-15 17:33'
        message: ''
        version: '5'
    -
        author: Alain Escaffre
        date: '2013-01-21 00:27'
        message: ''
        version: '4'
    -
        author: Alain Escaffre
        date: '2013-01-21 00:25'
        message: ''
        version: '3'
    -
        author: Alain Escaffre
        date: '2012-09-28 09:06'
        message: Migrated to Confluence 4.0
        version: '2'
    -
        author: Alain Escaffre
        date: '2012-09-28 09:06'
        message: ''
        version: '1'

---
*   **Title**: The title of the task, displayed in tasks lists in the user interface as well as directly on top of the task form, where user processes the task. Supports i18n.
*   **NodeId**: The node id is useful when you want to configure queues of tasks. This is currently limited to advanced users.
*   **Exclusive Node**: If checked, transitions can be ordered and only the first transition for which conditions are true will be followed. If not checked and if several transitions are true, then they will all be followed corresponding to a fork in the workflow. (available from 5.7.2)
*   **Directive**: The directive is displayed on top of the submission form when the user processes the tasks. Supports i18n.
*   **Due date expression**: This is where you express what should the due date be on the task that is created by this node. It is usually set relatively to the current date (the time when the task is created), but it can also be expressed leveraging the date at which the workflow was started.
*   **Assignees**: You can add&nbsp; static assignees here, either users or groups, one per input field (click on "**Add**" to add more than one). You need to prefix users by "`user:`" like `user:jack` and groups by "`group:`" like `group:validators`.
*   **Compute additional assignees**: You can set a scripted expression ([MVEL syntax]({{page space='nxdoc' page='understand-expression-and-scripting-languages-used-in-nuxeo'}}))&nbsp;here so as to determine where to lookup the assignees of the task. You have access to some useful variables in the context, like the `NodeVariables` and `WorkflowVariables` (see [Variables Available in the Automation Context]({{page space='nxdoc' page='variables-available-in-the-automation-context'}}) for more information). A frequent pattern is to set a node variable from the input chain of the node and reference it here.
*   <span style="color: rgb(67,67,67);">**Create one task per assignee**: If checked, there will be as many tasks created as there are assignees. This property is displayed only for the multi-task node.</span>
*   <span style="color: rgb(67,67,67);">**Allow task reassignment**: If set to true, the Reassign user action will be displayed on the task resolution screen and assignee will be able to reassign the task to someone else.</span>
*   <span style="color: rgb(67,67,67);">**Grand permission to task assignee**: Specifies the permission that will be assigned to each of the assignees on the bound document(s).</span>
*   **Mail notification**: Specifies the mail template that is going to be used to generate the mail to be sent to the task assignee. If for some reasons you want to send the email to some other users, you can do it from the input chain or output chain of the node, using the `Send E-Mail` operation.
*   **Task Document type**: This is only for advanced users. It is useful to change the type of the task that is created, so as to [be able to do some tasks queues]({{page space='nxdoc' page='how-to-set-up-a-tasks-dashboard'}}) that display additional metadata coming directly from the document.
*   **Input operation chain**: The automation chain you specify here will be executed when the workflow engine enters the node. If the node is of type Task, that means it's executed right before the task is created. The list of documents bound to the workflow instance will be the input of the chain. If there is one document, it will still be a list, with one element only.
*   **Output operation chain**: The automation chain you specify here will be executed just before the workflow engine leaves the node. If the node is of type Task, that means it's executed after the task created at this step is ended. The list of documents bound to the workflow instance will be the input of the chain.&nbsp;If there is one document, it will still be a list, with one element only.
*   **Allows incoming connections**: Used only by the graph editor. Check this if you want to be able to draw loops back to this node.

&nbsp;

{{#> callout type='info' heading='Getting the first document of the document list in the automation chains ran from a workflow node'}}

As we mentioned above, the workflow engine injects a document list in the automation chain, even when there is only one document. You may have sometime a "Cannot find any valid path in operation chain" exception, because the operation you put in the chain expects **one document** in input and the previous operation gives a list.

You can avoid this situation, when you know you have only one document, by fetching this document first. To do so, you can use:

```
Execution Context > Restore input document from a script
script: This[0]
```

<span style="color: rgb(34,34,34);font-size: 10.0pt;line-height: 13.0pt;">Then, for the rest of the chain, you will have only one document in input transiting from one operation to the other.</span>

{{/callout}}