## 1 git init ローカルリポ作成

```
% git init

hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /Users/username/Desktop/git_practice/.git/
```
## 2 README.md 作成
```
git_practice
   └── README.md
```


## 3 git status -状態確認-
* git addしないと**Untracked files**として扱われる
```
% git status

On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store
	README.md
```

## 4 git add --ステージングエリアに上げる--
```
% git add README.md
```

## 5 git status --再びgit statusで確認--
```
% git status

On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   README.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store

```

## 6 git commit -m 'first commit'
```
% git commit -m 'first commit'

[master (root-commit) 7984ac9] first commit
 1 file changed, 43 insertions(+)
 create mode 100644 README.md
```

## 7 git status --再びgit statusで確認--

```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store
nothing added to commit but untracked files present (use "git add" to track)
```


## 8 .gitignoreファイルの作成
* git操作に影響しないファイルを決める
* .DS_Storeが毎回出るので無視したい


### .gitignoreに.DS_Storeに追加する前
```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store

nothing added to commit but untracked files present (use "git add" to track)
```

### .gitignoreに.DS_Storeに追加
* ファイルの内容を変えたので再びadd,commitする
```
On branch master
nothing to commit, working tree clean
```

## 9 ローカルからリモートへあげたい
* **commit**しておく必要がある
* git remote add