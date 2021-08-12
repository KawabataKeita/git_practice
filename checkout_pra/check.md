```
git_practice
├── README.md
└── checkout_pra
    └── check.md
```

## 1 checkoutを用いてbranchを作成
* checkout_branchを作成しcheckout_branchへ移動

```
% git checkout -b checkout_branch
Switched to a new branch 'checkout_branch'

% git_practice % git branch
* checkout_branch
  main
```

## 2 addしてcommit

```
% git add checkout_pra
% git commit -m 'checkoutコミット'
[checkout_branch bebb4d3] checkoutコミット
 1 file changed, 20 insertions(+)
 create mode 100644 checkout_pra/check.md

% git push origin checkout_branch
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 554 bytes | 554.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'checkout_branch' on GitHub by visiting:
remote:      https://github.com/KawabataKeita/git_practice/pull/new/checkout_branch
remote:
To github.com:KawabataKeita/git_practice.git
 * [new branch]      checkout_branch -> checkout_branch
```

2回目のpushがうまく行かない
上記と同じ手順をふんでもリモートに反映されていない

解決
chekout_branchのbranchでは反映されていた．mainのbranchは変わらない（mergeする必要がある）