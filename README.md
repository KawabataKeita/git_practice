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