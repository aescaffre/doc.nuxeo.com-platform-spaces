---
title: Nuxeo Media Publishing
review:
    comment: ''
    date: '2015-12-01'
    status: ok
labels:
    - media-publishing-component
    - excerpt
toc: true
confluence:
    ajs-parent-page-id: '16089349'
    ajs-parent-page-title: Marketplace Add-Ons
    ajs-space-key: NXDOC
    ajs-space-name: Nuxeo Platform Developer Documentation
    canonical: Nuxeo+Media+Publishing
    canonical_source: 'https://doc.nuxeo.com/display/NXDOC/Nuxeo+Media+Publishing'
    page_id: '25691068'
    shortlink: vAOIAQ
    shortlink_source: 'https://doc.nuxeo.com/x/vAOIAQ'
    source_link: /display/NXDOC/Nuxeo+Media+Publishing
history:
    - 
        author: Manon Lumeau
        date: '2016-08-16 10:02'
        message: ''
        version: '19'
    - 
        author: Vincent Dutat
        date: '2016-02-10 18:28'
        message: ''
        version: '18'
    - 
        author: Vincent Dutat
        date: '2016-02-10 18:25'
        message: ''
        version: '17'
    - 
        author: Vincent Dutat
        date: '2016-02-10 18:20'
        message: ''
        version: '16'
    - 
        author: Manon Lumeau
        date: '2015-10-15 12:42'
        message: ''
        version: '15'
    - 
        author: Andre Justo
        date: '2015-10-13 11:51'
        message: ''
        version: '14'
    - 
        author: Andre Justo
        date: '2015-10-13 10:49'
        message: ''
        version: '13'
    - 
        author: Solen Guitter
        date: '2015-07-06 12:27'
        message: ''
        version: '12'
    - 
        author: Solen Guitter
        date: '2015-07-06 12:23'
        message: add link
        version: '11'
    - 
        author: Manon Lumeau
        date: '2015-07-01 08:53'
        message: ''
        version: '10'
    - 
        author: Manon Lumeau
        date: '2015-07-01 08:53'
        message: ''
        version: '9'
    - 
        author: Manon Lumeau
        date: '2015-06-30 16:51'
        message: ''
        version: '8'
    - 
        author: Manon Lumeau
        date: '2015-06-30 16:48'
        message: ''
        version: '7'
    - 
        author: Manon Lumeau
        date: '2015-06-30 16:19'
        message: ''
        version: '6'
    - 
        author: Manon Lumeau
        date: '2015-06-29 16:28'
        message: ''
        version: '5'
    - 
        author: Manon Lumeau
        date: '2015-06-29 16:27'
        message: ''
        version: '4'
    - 
        author: Andre Justo
        date: '2015-06-24 10:19'
        message: ''
        version: '3'
    - 
        author: Andre Justo
        date: '2015-06-24 10:18'
        message: ''
        version: '2'
    - 
        author: Andre Justo
        date: '2015-06-24 10:16'
        message: ''
        version: '1'

---
{{! excerpt}}

Nuxeo Media Publishing is an addon that enables users to publish video documents stored in the Nuxeo repository to external video hosting websites, without leaving the Nuxeo Platform UI.

{{! /excerpt}}

This addon is designed to allow many implementations. Default implemented providers are:

*   [Youtube](http://youtube.com)
*   [Wistia](http://wistia.com)

<div>

## Functional Overview

Installing this addon enriches the Publish tab of a video document with a set of external providers to where videos can be published. When publishing a video, users must select a publishing account and each provider can require additional fields to be filled (e.g tags, privacy of the video).

![]({{file name='publish_video.png'}} ?w=600,border=true)

This addon also adds a new section in the **Summary** page which lists all the providers available and the respective status of the video (either &ldquo;Published&rdquo; or &ldquo;Not published&rdquo;). Once a video is published, additional informations are displayed, such as:

*   The URL to the video in the external video host
*   An embeddable HTML snippet
*   Statistics

![]({{file name='summary_video.png'}} ?w=600,border=true)

Published videos can also be republished or unpublished from the external provider.

![]({{file name='republish_unpublish.png'}} ?w=600,h=325,border=true)

## Installation and Configuration

<div>This addon requires no specific installation steps. It can be installed like any other package [from the Marketplace or from the Admin tab]({{page page='installing-a-new-package-on-your-instance'}}). However, it requires the installation of the&nbsp;[Digital Asset Management (DAM) addon]({{page page='digital-asset-management-dam'}}) which provides multimedia files (picture, audio and video).</div>

<div>After the package is installed, two new OAuth2 service providers are added to Nuxeo (Admin > Cloud Services > Service providers). These providers must be properly configured before users can use them to publish their videos.</div>

<div>

<div>![]({{file name='oauth2-providers.png'}} ?w=600,border=true)</div>

</div>

</div>

### YouTube Configuration

**Step 1: Preparing your application accounts on the Google Developers Console**

1.  Go to&nbsp;[https://console.developers.google.com/project](https://console.developers.google.com/project).

2.  Create a new project.
3.  Enable YouTube API:&nbsp;In**&nbsp;APIs & auth**&nbsp;**>**&nbsp;**APIs**, click on&nbsp;**YouTube Data API**&nbsp;and then on the&nbsp;**Enable API**&nbsp;button.
4.  Edit your consent screen: In&nbsp;**APIs & auth > Consent Screen**, fill the product name (the name of your application). Optionally, you may fill the other fields.&nbsp;
5.  Create a new OAuth Client ID:**In APIs & auth > Credentials**, click on&nbsp;**Create a new Client ID**.
    1.  Choose&nbsp;**Web Application.**
    2.  For&nbsp;**Authorized JavaScript origins**&nbsp;set the URL of your server. Ex [http://localhost:8080/](http://localhost:8080/)
    3.  For&nbsp;**Authorized redirect URIs**&nbsp;set the following URL, adapting the hostname and port to your case:&nbsp;[http://localhost:8080/nuxeo/site/oauth2/YouTube/callback](http://localhost:8080/nuxeo/site/oauth2/googledrive/callback).
        The console redirects you to a page where you can see the Client ID and Client Secret values. You will need them in the next steps.

**Step 2: Configuring the Nuxeo Platform**

1.  In the **Admin** tab, go to&nbsp;**Cloud Services >**&nbsp;**Service providers**.
2.  In the&nbsp;**OAuth2 Service providers**&nbsp;section, update the service whose name is &ldquo;YouTube&rdquo; by clicking on the&nbsp;**Modify**&nbsp;button.
3.  Set the Client ID and Client Secret values with the one you got on the previous step.
4.  Make sure the&nbsp;**Enabled**&nbsp;box is checked.
5.  Save.

### Wistia Configuration

{{#> callout type='info' }}

OAuth2 is not yet available for all Wistia accounts. Until it is, [contact Wistia support](http://wistia.com/support/contact) to get it enabled.

{{/callout}}

**Step 1: Preparing your Wistia OAuth application**

1.  Go to [Wistia website](http://wistia.com/) > **Account** > **Settings** > **OAuth applications**.
2.  Create a new application.
3.  Fill in the required fields.
    1.  For&nbsp;**Callback URL**&nbsp;set the following URL, adapting the hostname and port to your case: [http://localhost:8080/nuxeo/site/oauth2/Wistia/callback](http://localhost:8080/nuxeo/site/oauth2/googledrive/callback).
    2.  Set permissions to&nbsp;**all:all.**
4.  Open the details of the application to get the Client ID and Client Secret values. You will need them in the next steps.

**Step 2: Configuring the Nuxeo Platform**

1.  In the **Admin** tab, go to&nbsp;**Cloud Services >**&nbsp;**Service providers**.
2.  In the&nbsp;**OAuth2 Service providers** section, update the service whose name is &ldquo;Wistia&rdquo; by clicking on the&nbsp;**Modify** button.
3.  Set the Client ID and Client Secret values with the one you got on the previous step.
4.  Make sure the&nbsp;**Enabled** box is checked.
5.  Save.

### How to Add Publishing Accounts

After setting up the OAuth service providers, users must add new accounts that are used to publish and retrieve video&rsquo;s informations from the external providers. To do so, users must go to **Home > Cloud Services** and use the available buttons to add their service accounts.

## Technical Overview

This section explains what is included in the Nuxeo Media Publishing addon.

### Schemas

Nuxeo Media Publishing defines the following schema:

*   `publishable_media`: used to store a list of providers where the video is published.

### Facets

This addon defines the `PublishableMedia`&nbsp;facet. This facet is added to the `Video` document type and contains the `publishable_media` schema.

### Extension Points

The `MediaPublishingService` exposes the `providers` extension point to contribute new publishing services.

```xml
<extension-point name="providers" target="org.nuxeo.ecm.media.publishing.MediaPublishingService">
  <provider id="MyMediaPublishingProvider"
      enabled="true"
      service="org.nuxeo.ecm.media.publishing.MyMediaPublishingProviderService">
  </provider>
</extension-point>
```

### How to Contribute New Providers

If you want to define other media publishing providers, you need to contribute a new publishing service to the Nuxeo Media Publishing addon.

#### Step 1: Contribute a media publishing service

Nested in the component tag of your XML contribution file, set the implementation class and use the extension point&nbsp;`providers` to register your media publishing service.

```xml
<component name="org.nuxeo.ecm.media.publishing.MyMediaPublishingProviderService">
  <implementation class="org.nuxeo.ecm.media.publishing.MyMediaPublishingProviderService" />

  <service>
    <provide interface="org.nuxeo.ecm.media.publishing.MyMediaPublishingProviderService" />
  </service>

  <extension target="org.nuxeo.ecm.media.publishing.MediaPublishingService"point="providers">
    <provider id="my-publishing-provider" 
		enabled="true" 
		service="org.nuxeo.ecm.media.publishing.MyMediaPublishingProviderService"/>
  </extension>
</component>
```

Your service implementation must implement the&nbsp;`MediaPublishingProvider` interface or extend any other class that implements this interface.

#### Step 2: Contribute an OAuth provider

1.  Nested in the component tag of your XML contribution file, add a `require`&nbsp;tag the&nbsp;`OAuth2ServiceProviderRegistry`.
2.  Then, use the extension point&nbsp; [`providers`](http://explorer.nuxeo.com/nuxeo/site/distribution/current/viewExtensionPoint/org.nuxeo.ecm.platform.oauth2.providers.OAuth2ServiceProviderRegistry--providers) &nbsp;of the `OAuth2ServiceProviderRegistry`&nbsp;service to register the OAuth provider.

    ```xml
    <component name="org.nuxeo.ecm.media.publishing.MyOAuthServiceProvider">
      <require>org.nuxeo.ecm.platform.oauth2.providers.OAuth2ServiceProviderRegistry</require>

      <extension target="org.nuxeo.ecm.platform.oauth2.providers.OAuth2ServiceProviderRegistry" point="providers">
        <provider>
          <name>my-publishing-provider</name>
          <description>MyOAuthServiceProvider</description>
          <class>org.nuxeo.ecm.media.publishing.MyOAuthServiceProvider</class>
          <tokenServerURL></tokenServerURL>
          <authorizationServerURL></authorizationServerURL>
          <scope></scope>
        </provider>
      </extension>
    </component>
    ```

    **Note:** The&nbsp;`name` field of your OAuth provider must match the&nbsp;`id` of your media publishing service defined in Step 1\. The `description`&nbsp;field is used as a label in the UI.

#### Step 3: Contribute options widgets&nbsp;(optional)

By default, when publishing a video, the only required field to fill in is the publishing account. However, since different services allow different metadata (e.g. privacy status of a video, channels, projects, tags) it is possible to contribute more options widgets to the publishing panel in the UI.

```xml
<extension target="org.nuxeo.ecm.platform.actions.ActionService" point="actions">
  <action id="myprovider_options" type="widget">
    <category>MEDIA_PUBLISHING_OPTIONS_CATEGORY</category>
    <properties>
      <property name="widgetName">myprovider_options_widget</property>
    </properties>
    <filter id="isMyProvider">
      <rule grant="true">
        <condition>#{provider == "my-publishing-provider"}</condition>
      </rule>
    </filter>
  </action>
</extension>
```

&nbsp;

* * *