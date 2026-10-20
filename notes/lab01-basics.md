# Lab01
<img width="742" height="306" alt="截屏2026-10-20 13 33 59" src="https://github.com/user-attachments/assets/635e5d90-8c68-4527-957c-c1c449662c98" />
<rd>
整个流程是：
修改文件 → Stage → Commit → Push
而 Pull 是反方向：把 GitHub 上的更新同步回本地。
指令	作用
pwd	查看当前所在文件夹
git status	查看哪些文件被修改、暂存或提交
git branch	查看当前分支
git branch -vv	查看分支及其远程追踪状态
git remote -v	查看连接的 GitHub 仓库地址
git log --oneline -5	查看最近 5 次 Commit

git add solution.R  只暂存 solution.R
git add .  暂存当前目录下所有新增、修改及删除的文件。
注意：git add . 不会上传文件到 GitHub，只是把改动放入暂存区。

git commit -m "Complete Figure 1"
-m 后面是本次提交的说明。

git push origin main 上传到 GitHub
git push：上传提交。
origin：远程仓库的默认名称。
main：要推送的分支名称。

git pull origin main 同步 GitHub 的更新
