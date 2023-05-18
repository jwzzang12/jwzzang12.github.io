---
title: Git branch rules
date: 2023-05-18 22:00:00 +0100
categories: [Coding, Git]
tags: [github] # TAG names should always be lowercase
author: <author_id>
---

1. git checkout -b `<feature branch>`
2. git push origin `<feature branch>`
3. Github 가서 `<main branch>`랑 합친다 -> pull request
4. Pull request 끝나면 branch 지울건지 뜸
5. 지움!
6. 다시 vscode 가서 git checkout `<main branch>`
7. git pull origin `<main branch>`
8. git branch -D `<feature branch>`
9. git checkout -b `<feature branch>` (1번 반복)

\*원격으로 삭제하고 싶은 경우
git push origin --delete `<feature branch>`

> **another rule**
> Git Pull Request

1. git pull to make sure you're up to date
2. git checkout -b feature<feature>
3. git add
   git commit -m "message about comit"
   git pull origin development
4. git push
5. copy paste message (upstream message, paste and send that command)
6. make pull request on github
7. team merge and delete branch on github
8. git checkout development
9. git pull
10. git branch - d `feature<feature>` (This will delete the branch you were working on before checking out to the development branch)
