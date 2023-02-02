## Ubuntu VSCode Challenges with Changing GitHub User

<p>I had set up an Ubuntu development environment and was able to successfully login to a GitHub account.  I then needed to login to a different GitHub account and that is where my challenges began.</p>

### How to Change the GitHub Login

Update the ~/.gitconfig file with the new connection information.

 ```console
nano ~/.gitconfig
 ```

 ```console
[user]
   name = <GitHub UserName>
   email = <email addess associated with this this GitHub UserName:marcus@example.com>
 ```

<p>My expectation was that I would open VSCode and when I went to login to GitHub, it would login to the updated acount.  That is not what happened.  Instead I have spent several days trying everything recommended by the Internet. To no avail.  Doing everything I could to try to discover where the program was finding the original GitHub account information was ultimately unsuccessful. <p>

### The Behavior
<ol>
<li>Open VSCode</li>
<li>Select Accounts->Sign in to Sync Settings</li>
<li>Select "Sign in with GitHub"</li>
<li>My default browser opened, showing a connection to github.com/login/oauth/authorize... No password was requested. Just a blank page on the new tab.</li>
<li>Select Accounts and look at the top item.  This was showing my previous login, not the new one I wanted.
</ol>

### The Solution
<p>Because the authentication browser tab was never asking me for a password I began to suspect that that was where my problem was.  And it was. To solve this problem:</p>
<ol>
  <li> Open up your default browser (the one that the authentication attempt is happening in) go to www.github.com.</li>
  <li> My browser was automatically logging me into the first acount.  Logout. </li>
  <li> Now log the browser into the new GitHub account.</li>
  <li> Close VSCode and reopen.</li>
  <li>Select Accounts->Sign in to Sync Settings.</li>
  <li>Select "Sign in with GitHub".</li>
</ol>
<p></p>
<p>And you are now logged into the correct account</p>
