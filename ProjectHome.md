### Introduction ###
This is a repackaging of HttpClient 4.3.1 for Android.
The version of HttpClient in the Android SDK is 4.0beta2.
There have been several updates to HttpClient and some
much-needed bugfixes like auth caching since the 4.0beta.
<br><br>
Since Google has deprecated HttpClient in favor of Java standard HttpURLConnection I created a script to convert<br>
a stock release of Apache's HttpClient into an Android<br>
library.<br><br>

<h3>Get official Android port from Apache</h3>
An official Android port from Apache was released here:<br>
<a href='https://hc.apache.org/httpcomponents-client-4.3.x/android-port.html'>https://hc.apache.org/httpcomponents-client-4.3.x/android-port.html</a><br>
It's also available on Maven Central<br>

<h3>Updates</h3>
<i>22nd February 2014</i><br>
<b>1.2.1</b>: Upgraded to HttpClient 4.3.2 and HttpCore 4.3.2<br>
Downloads:<br>
<a href='https://drive.google.com/file/d/0BzK7b0m5WJsfSktseFNvX09wVms/edit?usp=sharing'>https://drive.google.com/file/d/0BzK7b0m5WJsfSktseFNvX09wVms/edit?usp=sharing</a><br>
<a href='https://drive.google.com/file/d/0BzK7b0m5WJsfZDNOVnlhVmhzTFk/edit?usp=sharing'>https://drive.google.com/file/d/0BzK7b0m5WJsfZDNOVnlhVmhzTFk/edit?usp=sharing</a><br>
<br>
<i>16th January 2014</i><br>
<b>1.2.0</b>: Upgraded to HttpClient 4.3.1 and HttpCore 4.3.1<br>
Better late than never! :) Thanks go to Christian H. for updating the script.<br>
<br>
<i>1st March 2013</i><br>
<b>1.1.2</b>: Upgraded to HttpClient 4.2.3 and HttpCore 4.2.3<br>
<br>
<i>11th July 2012</i><br>
<b>1.1.1</b>: Upgraded to HttpClient 4.2.1 and HttpCore 4.2.1<br>
SPNego and Kerberos authentication were removed because of dependencies on org.ietf.jgss<br><br>
<i>9th May 2012</i><br>
<b>1.1.0</b>: Upgraded to HttpCore 4.2<br>
Be aware of incompatibilities to HttpCore 4.1.4, see <a href='http://www.apache.org/dist/httpcomponents/httpcore/RELEASE_NOTES.txt'>Release Notes</a><br><br>
<i>27th March 2012</i><br>
<b>1.0.4</b>: Added HttpMime<br>
Upgraded to HttpClient 4.1.3<br><br>
<i>14th February 2012</i><br>
<b>1.0.3</b>: Added internal checks into HttpClientAndroidLog (Thanks Federico)<br>         Added a copy of Base64.java to be compatible against Android 1.5<br>
Added a bugfix from <a href='https://android-review.googlesource.com/#/c/15755/1//COMMIT_MSG'>Android Source tree</a> (Thanks Louis)<br><br>
<i>2nd January 2012</i><br>
<b>1.0.2</b>: Updated to HttpCore 4.1.4 and added HttpClient-Cache<br><br>
<i>4th October 2011</i><br>
<b>1.0.1</b>: Bugfix for Basic Authentication<br>
Decided to use version numbering so users do not get confused in the future.<br>
<br>
<h3>Changes to stock HttpClient</h3>
<ul><li>Renamed all packages <i>org.apache.http</i> to <i>ch.boye.httpclientandroidlib</i>
</li><li>Deleted all classes dependent on <i>org.ietf.<code>*</code></i> (SPNEGO authentication)<br>
</li><li>Replaced <i>org.apache.commons.codec.binary.Base64</i> with a copy of Android's <i>Base64</i>
</li><li>Created a new class <i>HttpClientAndroidLog</i> to replace <i>org.apache.commons.logging</i></li></ul>

<h3>Logging debug/error/warn information</h3>
HttpClientAndroidLog is just a simple class which has the same interface as the commons.logging.Log class. Logging can be enabled for example with<br>
<pre><code>  DefaultHttpClient httpClient = new DefaultHttpClient();<br>
  httpClient.log.enableDebug(true);<br>
</code></pre>
Now all debug information will be output to Android LogCat. This is more or less a very simple hack which will perhaps be replaced in the future.<br>
<br>
<h3>How to use this library</h3>
There are 2 options:<br>
<ol><li>Use pre-compiled .jar file as external JAR library in your Android project<br>
</li><li>Use Android library project with all source files in Eclipse<br>
You can find both under Downloads. Current version includes HttpClient 4.2.1 and HttpCore 4.2.1<br>
<br><br>
You can also create your own .jar and library project by using my bash-script and any<br>
stock HttpClient 4.x. The script you can get by checking out the git repository.<br>
<br><br>
In your code import <b>ch.boye.httpclientandroidlib.<code>*</code></b> instead of org.apache.http.<code>*</code>