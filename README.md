# git-in-depth

Course 1 - Learn Git in Depth

<h2>What's git?</h2>
```
Distributed version control system
```
<br/>
Git is the most commonly used version control system. Git tracks the changes you make to files, so you have a record of what has been done, and you can revert to specific versions should you ever need to. Git also makes collaboration easier, allowing changes by multiple people to all be merged into one source. 

<br/>
<img src="./images/git-branches-merge.png">
<br/><br/>

Git is software that runs locally. Your files and their history are stored on your computer. You can also use online hosts (such as GitHub or Bitbucket) to store a copy of the files and their revision history. Having a centrally located place where you can upload your changes and download changes from others, enable you to collaborate more easily with other developers. Git can automatically merge the changes, so two people can even work on different parts of the same file and later merge those changes without losing each other’s work!
<br/><br/>

<h2>Git Foundation</h2>
<h3>> Data Storage</h3>
Git is kind of like a key value store, The value is the data, and the key is hash of the data, you can use the key to retrive the content.
<br/><br/>

<b>THE KEY - SHA1</b>
<ul>
  <li>Is a cryptographic hash function</li>
  <li>Given a piece of data, it produce a 40-digit hexadecimal number</li>
  <li>THis value should always be the same if the given input is the same</li>
</ul>


<h3>> Git Blobs & Trees</h3>
blob — A blob object is used for storing the contents of a single file.<br/>
tree — A tree object contains references to other blobs or subtrees.


<h3>> Git Commit</h3>

