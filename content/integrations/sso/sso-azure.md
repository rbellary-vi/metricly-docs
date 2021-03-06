---
title: "Azure SSO"
#date: 2018-12-11
draft: false
tags: ["#sso", "#integrations", "#authentication", "#azure"]
author: Lawrence Lane
weight: 1
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

Keep this tab open and open a new tab; you must now login to Azure and upload the certificate.

## 2. Create New Application in Azure

1. Log into **Azure** as an administrator.
2. Navigate to **Azure Active Directory** > **Enterprise Applications**.
![azure-enterprise-applications](/images/sso-azure/azure-enterprise-applications.png)
3. Select **+ New Application**.
![azure-new-application](/images/sso-azure/azure-new-application.png)
4. Select **Non-Gallery Application** and name your SSO application.
![azure-non-gallery-application](/images/sso-azure/azure-non-gallery-application.png)
5. `Name` your SSO application and select **Add**.
![azure-name-add-application](/images/sso-azure/azure-name-add-application.png)
6. Select **Configure single sign-on (required)**.
![azure-configure-sso-required](/images/sso-azure/azure-configure-sso-required.png)
7. Select **SAML** for the single sign-on method.
![azure-saml-method](/images/sso-azure/azure-saml-method.png)

You are now ready to define your new SSO application's SAML and user settings. If you need to return to these settings in the future, follow this path: **Azure Active Directory** > **Enterprise applications** > `Your Application Name` > **Single sign-on** > **SAML-based Sign-on**.

### Upload Certificate From CloudWisdom To Azure SAML SSO Application

1. Select **Upload metadata file**.
![azure-upload-cert](/images/sso-azure/azure-upload-cert.png)
2. Upload the `.cert` file created in CloudWisdom from the first step.

### Define Azure SAML SSO Configuration

1. Select **Edit** on the Basic SAML Configuration card. A slide-out panel appears.
![azure-edit-basic-saml](/images/sso-azure/azure-edit-basic-saml.png)
2. Input the following values:
  - **Identifier (Entity ID)**: `netuitive-api`
  - **Reply URL (Assertion Consumer Service URL)**: `https://app.metricly.com/saml/SSO`
  - **Sign on URL**: `https://app.metricly.com/saml/SSO`
  - **Relay State**: `Your Tenant Name` (optional)

  {{% notice tip %}}
  Add your tenant name to the **Relay State** field if you do not want to enter it when logging into CloudWisdom from Azure. Your tenant name is the company name you used when you signed up for a CloudWisdom account. You can find it on the [SSO page] (https://us.cloudwisdom.virtana.com/#/profile/sso) in CloudWisdom.
  {{% /notice %}}

### Define User Attributes & Claims
1. Select **Edit** on the User Attributes & Claims card.
2. Select **+ Add new claim**.
![azure-add-new-claims](/images/sso-azure/azure-add-new-claims.png)
3. Add the following claims:
  - **email**: `user.mail`
  - **firstName**: `user.givenname`
  - **lastName**: `user.surname`
  - **role**:  `"Read Only"`

  {{% notice tip %}}
  The **role** claim attribute can also be set to `"Administrator"`, however this makes all SSO users administrators in Metrcly. We recommend updating your administrator accounts individually and leaving the default role to `Read Only`.
  {{% /notice %}}

### Define & Download SAML Signing Certificate

1. Select **Edit** on the SAML Signing Certificate card.
2. Select the following dropdowns:
  - **Signing Option**: `Sign SAML Assertion`
  - **Signing Algorithm**: `SHA-256`
3. Download the **Certificate (Base64)**.
4. Download the **Federation Metadata XML**.
![azure-download-cert](/images/sso-azure/azure-download-cert.png)

These files must be uploaded to CloudWisdom.

## 3. Finish SSO Set-up in CloudWisdom

1. Navigate to **Account Profile** > **SSO**.
2. Upload the **Certificate (Base64)** file from Azure.
2. Upload the **Federation Metadata XML** file from Azure.
![upload-metadata-xml](/images/_index/upload-metadata-xml.png)
2. When finished, it should look like this:
![cloudwisdom-sso-complete](/images/sso-azure/cloudwisdom-sso-complete.png)

## Log In to CloudWisdom using SSO

Now that you have SSO configured, you can log in to CloudWisdom a couple different ways. 

The first way is to visit the main SSO login page and provide your tenant name; your tenant name can be found on the [SSO page] (https://us.cloudwisdom.virtana.com/#/profile/sso) in CloudWisdom. You can also append your tenant name to the end of the main SSO login page URL to have it pre-populated on the page. 

The second way is to visit a link that automatically re-directs you to your SSO provider; if you're signed into your SSO provider, you will be logged in to CloudWisdom automatically, otherwise you will be prompted by your SSO provider to sign in before getting logged in to CloudWisdom.

- **Main SSO Login Page:** `https://us.cloudwisdom.virtana.com/#/login?sso=true`
- **Main SSO Login Page with Tenant Name Pre-Populated:** `https://us.cloudwisdom.virtana.com/#/login?sso=true&tenantName=Your+Tenant+Name`
- **Automatic Re-Direct to Your SSO Provider:** `https://us.cloudwisdom.virtana.com/saml/login?tenantName=Your+Tenant+Name`

Note: You'll need to replace `Your+Tenant+Name` with your tenant name where `+` indicates a space e.g. `Dales+Donut+Shop`.
