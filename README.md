# TutorialsXixi

# <b>Redis</b>
<li>if the key is not existed: </li>
<pre><code> HSETNX myhash PartitionKey "2013-05-06" Val "12344" </code></pre>
<pre>1</pre> (returns 1, succesfully inserted and not duplicate)
<li>else if the key and value is already there</li>
<pre>0</pre> (returns 0, is duplicate and the value is not been overwritted)


