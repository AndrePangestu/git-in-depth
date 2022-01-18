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
tree — A tree object contains references to other blobs or subtrees.


<h3>> Git Commit</h3>
In Git, a commit is a snapshot of your repo at a specific point in time.

To help further understand what a Git commit is, we need to review your `Working Directory` vs your `Staging Directory` and how files changes are reflected in your Git repository.

Think of your working directory as your “in progress” working area; here, created or modified files are not yet reflected in your Git repo. Changes made to files in your working directly only exist locally on your machine.

<b>! EXAMPLE EXERCISE !</b>
```
$ git commit -m "Initial Commit"
[main 88f0de9] Initial Commit
 1 file changed, 1 insertion(+)
 create mode 100644 exercise-sample/hello.txt
 ```

```
$ tree .git/objects
.git/objects
├── 01
│   └── e455918b8e70fb7a524b073f568c08d1ec98a2
├── 07
│   └── 3daee87afe04aefeb85e31ae2eef248fb5ef7d
├── 2e
│   └── 65b71e0be4702f11808abe37bfcd6cd37ea754
├── 3e
│   └── 4c27b5540dba6d1c3b10476b2e860c02a3b9f3
├── 45
│   └── cbcf6173870795dcd54dc619a9cc834a4165da
├── 4c
│   └── 8d4f1928c72cc75e2e2a124426b90662250edb
├── 6d
│   └── 1f2b675ff47f2bd1dee2614850c7b305dfa59e
├── 85
│   └── 476333e5428cc59f63425bf4eb7ac52fe1129d
├── 88
│   └── f0de9378d7aed2ccf775d6fdffcd23b6425a2b
├── 98
│   └── ca26292c8c5aa67a1bb7d9d94c4149d3f9f404
├── a7
│   └── 699ac9279005679e90a1d4f514239ea7554fac
├── bd
│   └── 2f174b867d2d31d666e0be42bd01b56cf8d041
├── d9
│   └── 733d44d14f824beb4e71a4e96a79bae7111f57
├── eb
│   └── d0fe5025450d0b72f5d69bfcade8f89a6edf58
├── ff
│   └── d30ed70a055b5f08dad008bd142cf488f6e520
├── info
└── pack
    ├── pack-56ee8b27414b92f0cf64a5f219850eeffa44c078.idx
    └── pack-56ee8b27414b92f0cf64a5f219850eeffa44c078.pack

17 directories, 17 files
```

```
$ ls .git/objects
01   2e   45   6d   88   a7   d9   ff   pack
07   3e   4c   85   98   bd   eb   info
```

```
$ git cat-file -t 01e455
blob

$ git cat-file -p 01e455
Hello, Wordl

$ git cat-file -t 2e65b7
commit
```

<h2>Git Areas and Stashing</h2>
<h3>> The Working Area</h3>
<ul>
  <li>The files in your working area that are also in the staging are not handle by git.</li>
  <li>Also Called `untracked files`</li>
</ul>

<h3>> The Staging Area</h3>
<ul>
  <li>What files are going to be the next commit</li>
  <li>The staging area is how git knows what will change between the current commit and the next commit</li>
</ul>

<h3>> The Repository</h3>
<ul>
  <li>The files git knows about</li>
  <li>Contains all of your commit</li>
</ul>


<h3>> Git Stashing</h3>
<ul>
  <li>Save un-committed work</li>
  <li>The stash is safe from destructive operation</li>
</ul>

<b>Git Stash - Basic Use</b>
```
> Stash Changes
  $ git stash

> List changes
  $ git stash list

> Show the content
  $ git stash show stash@{0}

> Apply the last stash
  $ git stash apply

> Apply a specific stash
  $ git stash apply stash@{0}
```
