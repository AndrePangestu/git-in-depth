# git-in-depth

Course 1 - Learn Git in Depth

<h2>What's git?</h2>

`Distributed version control system`

Git is the most commonly used version control system. Git tracks the changes you make to files, so you have a record of what has been done, and you can revert to specific versions should you ever need to. Git also makes collaboration easier, allowing changes by multiple people to all be merged into one source. 

<br/>
<img src="./images/git-branches-merge.png">
<br/>

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
tree — A tree object contains references to other blobs or subtrees. <br/>

<b>example git Blob</b>
```% git cat-file -t 581ca         
tree
% git cat-file -p 581ca
100644 blob 980a0d5f19a64b4b30a87d4206aade58726b60e3 hello.txt
```

<b>example git tree</b>
```
% tree .git/objects
.git/objects
├── 58
│   └── 1caa0fe56cf01dc028cc0b089d364993e046b6
├── 98
│   └── 0a0d5f19a64b4b30a87d4206aade58726b60e3
├── 99
│   └── b2172e47a9367ff4cb3fc9c093090087688807
├── info
└── pack
```

<h3>> Git Commit</h3>
In Git, a commit is a snapshot of your repo at a specific point in time.

To help further understand what a Git commit is, we need to review your `Working Directory` vs your `Staging Directory` and how files changes are reflected in your Git repository.

Think of your working directory as your “in progress” working area; here, created or modified files are not yet reflected in your Git repo. Changes made to files in your working directly only exist locally on your machine.


