# OAuth

## What is OAuth ?

__* OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential. *__

## Give an example of what using OAuth would look like.

__* OAuth scenario could be a user sending cloud-stored files to another user via email, when the cloud storage and email systems are otherwise unrelated other than supporting the OAuth framework. *__

## How does OAuth work? What are the steps that it takes to authenticate the user ?

__* Let’s assume a user has already signed into one website or service (OAuth only works using HTTPS). The user then initiates a feature/transaction that needs to access another unrelated site or service. *__

* The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

* The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.
* The first site gives this token and secret to the initiating user’s client software.


* The client’s software presents the request token and secret to their authorization provider.
* If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

## What is OpenID ?

__* penID began life in 2005 as a means for logging into the then-popular LiveJournal blogging site but quickly spread to other sites. The idea, in the early days of Web 2.0, was that rather than having multiple logins for multiple websites, OpenID would serve as a single sign-in, vouching for the identities of users. But in practice OpenID was" and never really became that appealing to users, especially as there was competition in that space. By 2011, OpenID had become an also-ran, and, Wired declared that "The main reason no one uses OpenID is because Facebook Connect does the same thing and does it better. Everyone knows what Facebook is and it's much easier to understand that Facebook is handling your identity than some vague, unrecognized thing called OpenID." *__

## What is the difference between authorization and authentication?

|Authentication	|Authorization|
|----|-----|
| Determines whether users are who they claim to be |  Determines what users can and cannot access  |
| Challenges the user to validate credentials (for example, through passwords, answers to security questions, or facial recognition) |  Verifies whether access is allowed through policies and rules  |
| Usually done before authorization |  Generally, transmits info through an Access Token  |
| Generally governed by the OpenID Connect (OIDC) protocol |  Generally governed by the OAuth 2.0 framework  |
| Example: Employees in a company are required to authenticate through the network before accessing their company email |  Example: After an employee successfully authenticates, the system determines what information the employees are allowed to access  |

## What is Authorization Code Flow?

__* Because regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow (defined in OAuth 2.0 RFC 6749, section 4.1), which exchanges an Authorization Code for a token. Your app must be server-side because during this exchange, you must also pass along your application's Client Secret, which must always be kept secure, and you will have to store it in your client.*__ 

## What is Authorization Code Flow with Proof Key for Code Exchange (PKCE) ?

__* When public clients request Access Tokens, some additional security concerns are posed that are not mitigated by the Authorization Code Flow alone.*__

## What is Implicit Flow with Form Post ?

__* As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets.*__

## What is Client Credentials Flow ?

__* With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user.*__

## What is Device Authorization Flow ?

__* With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. *__

## What is Resource Owner Password Flow ?

__* highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. The Resource Owner Password Flow should only be used when redirect-based flows cannot be used.*__



