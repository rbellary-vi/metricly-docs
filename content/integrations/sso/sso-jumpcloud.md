---
title: "JumpCloud SSO"
#date: 2018-12-11
draft: false
tags: ["#sso", "#integrations", "#authentication", "#jumpcloud"]
author: Lawrence Lane
weight: 2
---

{{% alert success %}}
Single Sign-On (SSO) is a feature available only to users with a CloudWisdom subscription. Contact your [Sales Representative](mailto:dl-sales-metricly@virtualinstruments.com) for pricing options.
{{% /alert %}}

## 1. Generate a Certificate in CloudWisdom

1. Navigate to **Account Profile** > **SSO**.
2. Select **Generate**.
![generate](/images/_index/generate.png)
3. Copy the generated certificate and use it to create a `.cert` file.
4. Select **Continue**.

Keep this tab open and open a new tab; you must now login to JumpCloud and upload the certificate.

## 2. Create New Application in JumpCloud
1. Log into **JumpCloud** as an administrator.
{{% notice tip %}}
 Login page _must_ say **JumpCloud Administrator Login** and _not_  **JumpCloud User Login**.
{{% /notice %}}
2. Navigate to **Applications** > **+** (New Application). A slide-out panel appears.
![jc-new-application](/images/sso-jumpcloud/jc-new-application.png)
3. Search for `SAML` and select **Custom SAML App** > **Configure**.
4. Input the following values:
  - **DISPLAY LABEL**: `Your SSO Label` ("A name of your choosing to identify this configuration.)
  - **IDP ENTITY ID**: `jumpcloud-cloudwisdom`
  - **SP ENTITY ID**: `netuitive-api`
  - **ACS URL**: `https://app.metricly.com/saml/SSO`
  - **SP CERTIFICATE**:  Upload the .`cert` file from section 1.
  - **SAMLSUBJECT NAMEID**: `email`
  - **SAMLSUBJECT NAMEID FORMAT**: `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
5. Create **USER ATTRIBUTES** for the following:
  - **email**: `email`
  - **firstName**: `firstname`
  - **lastName**: `lastname`
  - **role**: `Read Only`
6. Add your tenant name to the **Default Relay State** field if you do not want to enter it when logging into CloudWisdom from JumpCloud. Your tenant name is the company name you used when you signed up for a CloudWisdom account. You can find it on the [SSO page] (https://us.cloudwisdom.virtana.com/#/profile/sso) in CloudWisdom.
![jc-relay-state](/images/sso-jumpcloud/jc-relay-state.png)
7. **Save** your new SSO application.

  {{% notice tip %}}
Be careful not to accidentally create your **USER ATTRIBUTES** (green) under **CONSTANT ATTRIBUTES** (red).
![jc-user-attributes-tip](/images/sso-jumpcloud/jc-user-attributes-tip.png)
{{% /notice %}}

Now you are ready to download your certificate and metadata to be uploaded to CloudWisdom.

### Download IDP Certificate & Export Metadata
1. Expand the **IDP Certificate Valid** menu on the left of the app.
2. Select **Download certificate**
![jumpcloud-download-certificate](/images/sso-jumpcloud/jumpcloud-download-certificate.png)
3. Scroll to the bottom of the app's settings and select **export metadata**.
![jumpcloud-export-metadata](/images/sso-jumpcloud/jumpcloud-export-metadata.png)

You are now ready to import your JumpCloud certificate and metadata to CloudWisdom.

## 3. Finish SSO Set-up in CloudWisdom

1. Navigate to **Account Profile** > **SSO**.
2. Upload the **IDP Certificate** file from JumpCloud.
2. Upload the **Metadata.xml** file from JumpCloud.
![upload-metadata-xml](/images/_index/upload-metadata-xml.png)
2. When finished, it should look like this:
![cloudwisdom-sso-complete](/images/sso-jumpcloud/cloudwisdom-sso-complete.png)

## Log In to CloudWisdom using SSO

Now that you have SSO configured, you can log in to CloudWisdom a couple different ways. 

The first way is to visit the main SSO login page and provide your tenant name; your tenant name can be found on the [SSO page] (https://us.cloudwisdom.virtana.com/#/profile/sso) in CloudWisdom. You can also append your tenant name to the end of the main SSO login page URL to have it pre-populated on the page. 

The second way is to visit a link that automatically re-directs you to your SSO provider; if you're signed into your SSO provider, you will be logged in to CloudWisdom automatically, otherwise you will be prompted by your SSO provider to sign in before getting logged in to CloudWisdom.

- **Main SSO Login Page:** `https://us.cloudwisdom.virtana.com/#/login?sso=true`
- **Main SSO Login Page with Tenant Name Pre-Populated:** `https://us.cloudwisdom.virtana.com/#/login?sso=true&tenantName=Your+Tenant+Name`
- **Automatic Re-Direct to Your SSO Provider:** `https://us.cloudwisdom.virtana.com/saml/login?tenantName=Your+Tenant+Name`

Note: You'll need to replace `Your+Tenant+Name` with your tenant name where `+` indicates a space e.g. `Dales+Donut+Shop`.
