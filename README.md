<h1>Tableau OAuth Plugin:</h1>
<p> The Tableau OAuth plugin was written to accompany the Tableau Sample App 
but is also useful as a stand-alone class. 
For more information about the class, visit this project's wiki. 
As a plugin, it preforms three authentication related tasks that can be used in Cordova and Ionic projects: 
<ol>
    <li> Check if user is signed in. This function should always be called before trying to load Tableau content. <pre>TableauOAuth.checkSignInStatus()</pre></li>
    <li> Manage OAuth tokens for a session. OAuth tokens must be enabled on your server. <pre>TableauOAuth.requestOAuthTokens()</pre></li>
    <li> Sign out the user. <pre>TableauOAuth.signOut()</pre></li>
</ol>

<h2> Check Sign In Flow: </h2>
<pre>
                     checkSignInStatus
                            |
                  Is the session expired?
                            |
                __________________________
                |                           |
               NO                          YES
            User is signed in.              |
                                    Does the app have tokens?
                                            |
                                __________________________
                                |                         |
                               YES                        NO
                                |                   User is NOT signed in.     
                        Can they be refreshed?
                                |
                        ___________________
                       |                   |
                      YES                  NO
                User is signed in.      User is NOT signed in.
                    
</pre>

<h2> OAuth tokens: </h2>
<p> For more information about OAuth tokens visit this project's wiki. The plugin completes four main tasks in order to handle the OAuth tokens. </p>
<ul>
    <li>Get initial access/refresh tokens</li>
    <li>Store in iOS Keychain</li>
    <li>Refresh access token if expired</li>
    <li>Revoke refresh and access token on sign out </li>
</ul>
<h2> Support </h2>
<p> This collection is not officially 'blessed' by Tableau Engineering or Support. What does that mean? We didn't have a qa team test it. It's a tool for learning how to embed vizzes inside a mobile application. You should not expect that there are 0 bugs.
If you have problems getting it to work, feel free to email us with questions, but we won't promise quick responses.
A standard disclaimer: TableauSampleApp is made available AS-IS with no support and no warranty whatsoever. Despite efforts to write good and useful code there may be bugs that cause unexpected and undesirable behavior. The software is strictly “use at your own risk.”
The good news: This is intended to be a self-service tool. You are free to modify it in any way to meet your needs. </p>

