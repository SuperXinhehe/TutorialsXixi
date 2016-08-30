# TutorialsXixi

# <b>Redis</b>
if the key is not existed: 
<pre><code> >>> HSETNX myhash PartitionKey "2013-05-06" Val "12344" </code></pre>
<pre>1</pre> (returns 1, succesfully inserted and not duplicate)
else if the key and value is already there
<pre>0</pre> (returns 0, is duplicate and the previous value for "Val" is not been overwritted)

mark it as duplicate and save it with another uuid name append in the same partitionKey 
<pre> >>> HMSET myhash PartitionKey "2019-05-06" Val(uuid) "12344" </pre>
<pre>OK</pre>



