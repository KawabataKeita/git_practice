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

### .gitignoreに.DS_Storeに追加した後
* ファイルの内容を変えたので再びadd,commitする
```
On branch master
nothing to commit, working tree clean
```

## 9 ローカルからリモートへあげたい
* **commit**しておく必要がある
* git remote add

```
% git remote add origin https://github.com/KawabataKeita/git_practice.git
% git remote -v

origin	https://github.com/KawabataKeita/git_practice.git (fetch)
origin	https://github.com/KawabataKeita/git_practice.git (push)

```

* git push origin masterでユーザ名とパスワード入力したがうまくいかない
* httpsがよくないっぽい

```
git remote set-url origin git@github.com/KawabataKeita/git_practice.git
```

```
% git remote -v
origin	git@github.com/KawabataKeita/git_practice.git (fetch)
origin	git@github.com/KawabataKeita/git_practice.git (push)
```

* 上記のことをするためにgithubの方でレポジトリを作成しておく必要があった．
* やり直すため**git remote add**したものを取り消す
```
% git remote remove origin
```

```
% git remote add origin git@github.com:KawabataKeita/git_practice.git
% git push -u origin main

Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 12 threads
Compressing objects: 100% (15/15), done.
Writing objects: 100% (19/19), 2.84 KiB | 1.42 MiB/s, done.
Total 19 (delta 4), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (4/4), done.
To github.com:KawabataKeita/git_practice.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```