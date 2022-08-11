
# ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/core/images/project_color_16x16.png?raw=true "Project") lib_Exchange

This is the EWS (Exchange Web Service) Connector for Microsoft Exchange. This will work for Exchange On Line (Office365 Exchange Server) and for On Exchange On Prem installations.

The Connector needs an Authentication to work. For Exchange One Line , you must use OAuth. A Simple Test app is provided to Show how to establish an OAuth Auth and then call the CreateExchangeSession Sequence.

For On Prem Installations, you can use directly the  CreateExchangeSession Sequence by providing user and password.

## Symbols

| Symbol            | Usage                  |
|-------------------|----------------------|
| lib_exchange.EWSUrl  | The url to access EWS Api for On Prem Exchange servers. This should be in the form 'https://&lt;exchange.server.dns.name&gt;/ews/exchange.asmx'   |
| lib_exchange.ServiceAccount  | an Exchange Service account having the Impersonation privilege as an email address. See https://www.codetwo.com/kb/how-to-set-impersonation-rights-manually/ on how to configure impersonation for an account |
| lib_exchange.ServiceAccountPassword.secret  | The password for this service account |



<details><summary><span style="color:DarkGoldenRod"><i>References</i></span></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/references/images/ProjectSchemaReference_16x16.png?raw=true "ProjectSchemaReference") lib_OAuth


see [readme](https://github.com/convertigo/c8oprj-lib-oauth/tree/334a638363d83d83bfed756b025f96226751e50e#readme)
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Connectors</i></span></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/connectors/images/sqlconnector_color_16x16.png?raw=true "SqlConnector") void

void connector, replace or don't use it

<details><summary><span style="color:DarkGoldenRod"><i>Transactions</i></span></summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/transactions/images/sqltransaction_color_16x16.png?raw=true "SqlTransaction") void

does nothing
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Sequences</i></span></summary><blockquote><p>


<details><summary><b>CreateAppointment</b> : Creates an appointment in Calendar</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") CreateAppointment

Creates an appointment in Calendar

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Duration
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Location
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Start
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Subject
</td>
<td>

</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>CreateExchangeSession</b> : Creates a session with Exchange Server</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") CreateExchangeSession

Creates a session with Exchange Server. If Using user and password Authentication, provide them in the variables. If using OAuth, this will automatically use the EWS OAuth Token available in the current user session.

This sequence has to be called prior to any other sequences


<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;EWSUrl
</td>
<td>
The EWS Url. Automatically provided by the Symbol
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;password
</td>
<td>
The user password for Exchange On Prem installations. Automatically provided by the symbol but can be overrided

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;user
</td>
<td>
The user name as an email of a service account with Impersonation privileges for Exchange On prem installations. Automatically provided by the symbol but can be overrided
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>loginAzureAdWithAccessToken</b> : Perform the OAuth flow for AzureAD If the token is valid, it will be stored as a special EWS OAuth token in the user's session to be used when calling EWS APIs</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") loginAzureAdWithAccessToken

Perform the OAuth flow for AzureAD If the token is valid, it will be stored as a special EWS OAuth token in the user's session to be used when calling EWS APIs.


<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;access_token
</td>
<td>
The access Token generated by the OAuth Action
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>SendEmail</b> : Sends an email usinf EWS services</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") SendEmail

Sends an email usinf EWS services.

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Bcc
</td>
<td>
A stringified JSON array of Bcc recipients
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Body
</td>
<td>
The body as a String
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Cc
</td>
<td>
A stringified JSON array of cc recipients
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;From
</td>
<td>
The email of the user sending the mail
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Subject
</td>
<td>
The subject of the email as a string
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;To
</td>
<td>
A stringified JSON array of to recipients
</td>
</tr>
</table>

</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Mobile Application</i></span></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/core/images/mobileapplication_color_16x16.png?raw=true "MobileApplication") Application

This is a test app to perform OAuth and use the EWS Connector

<details><summary><span style="color:DarkGoldenRod"><i>Pages</i></span></summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/pagecomponent_color_16x16.png?raw=true "PageComponent") Page


</p></blockquote></details>
</p></blockquote></details>
