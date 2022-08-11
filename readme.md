


# lib_Exchange

This is the EWS (Exchange Web Service) Connector for Microsoft Exchange. This will work for Exchange On Line (Office365 Exchange Server) and for On Exchange On Prem installations.

The Connector needs an Authentication to work. For Exchange One Line , you must use OAuth. A Simple Test app is provided to Show how to establish an OAuth Auth and then call the CreateExchangeSession Sequence.

For On Prem Installations, you can use directly the  CreateExchangeSession Sequence by providing user and password.

## Symbols

| Symbol            | Usage                  |
|-------------------|----------------------|
| lib_exchange.EWSUrl  | The url to access EWS Api for On Prem Exchnage servers. This should be in the form 'https://<sever dns name>/ews/exchange.asmx'   |






For more technical informations : [documentation](./project.md)

- [Installation](#installation)
- [Sequences](#sequences)
    - [CreateExchangeSession](#createexchangesession)
    - [loginAzureAdWithAccessToken](#loginazureadwithaccesstoken)
    - [SendEmail](#sendemail)
- [Mobile Library](#mobile-library)


## Installation

1. In your Convertigo Studio use `File->Import->Convertigo->Convertigo Project` and hit the `Next` button
2. In the dialog `Project remote URL` field, paste the text below:
   <table>
     <tr><td>Usage</td><td>Click the copy button</td></tr>
     <tr><td>To contribute</td><td>

     ```
     lib_Exchange=https://github.com/convertigo/c8oprj-lib-exchange.git:branch=master
     ```
     </td></tr>
     <tr><td>To simply use</td><td>

     ```
     lib_Exchange=https://github.com/convertigo/c8oprj-lib-exchange/archive/master.zip
     ```
     </td></tr>
    </table>
3. Click the `Finish` button. This will automatically import the __lib_Exchange__ project


## Sequences

### CreateExchangeSession

Creates a session with Exchange Server. If Using user and password Authentication, provide them in the variables. If using OAuth, this will automatically use the EWS OAuth Token available in the current user session.

This sequence has to be called prior to any other sequences


**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>EWSUrl</td><td></td>
</tr>
<tr>
<td>password</td><td>The user password for Exchange On Prem installations</td>
</tr>
<tr>
<td>user</td><td>The user name as an email address for Exchange On prem installations</td>
</tr>
</table>

### loginAzureAdWithAccessToken

Perform the OAuth flow for AzureAD If the token is valid, it will be stored as a special EWS OAuth token in the user's session to be used when calling EWS APIs.


**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>access_token</td><td></td>
</tr>
</table>

### SendEmail

Sends an email usinf EWS services.

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>Bcc</td><td>A stringified JSON array of Bcc recipients</td>
</tr>
<tr>
<td>Body</td><td>The body as a String</td>
</tr>
<tr>
<td>Cc</td><td>A stringified JSON array of cc recipients</td>
</tr>
<tr>
<td>From</td><td>The email of the user sending the mail</td>
</tr>
<tr>
<td>Subject</td><td>The subject of the email as a string</td>
</tr>
<tr>
<td>To</td><td>A stringified JSON array of to recipients</td>
</tr>
</table>

## Mobile Library

This is a test app to perform OAuth and use the EWS Connector



