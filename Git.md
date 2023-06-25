# Git Summary

|                    功能                     |            命令             |                             说明                             |
| :-----------------------------------------: | :-------------------------: | :----------------------------------------------------------: |
|                    提交                     |         git commit          |                                                              |
|                 创建新分支                  |         git branch          | **git branch -f main head~3将main分支指向head的第三级父提交** |
|              切换到指定的分支               |     git checkout 分支名     | checkout包含多个独立功能占用较大的性能，使用 **git switch 分支名** |
|         创建新分支并切换到该分支上          |   git checkout -b 分支名    |                                                              |
|           当前分支合并到指定分支            |      git merge 分支名       |             相比rebase，merge将当前的commit合并              |
|         当前分支线性合并到指定分支          |    **git rebase 分支名**    | 相比merge，rebase做出了原来commit包括所有父节点的副本并合并，原来的commit仍然存在 |
|        从分支上分离出HEAD到指定提交         |   **git checkout 提交号**   | 实为操作哈希，实际中的哈希有40位，但是git很智能的只需要传入前几位就可以识别 |
|                 查看git日志                 |           git log           |                                                              |
|                   操作符^                   |    git checkout 提交号^     | main^是main的父节点main^^是main的第二个父节点；使用HEAD^向上移动 |
|                   操作符~                   |   **git checkout HEAD~4**   |      后跟数字代表一次上移多少位，不带数字作用同操作符^       |
|                  撤销变更                   |     git reset 分支记录      | git reset HEAD~1回退到上一次提交并改写历史，撤销前的提交不再存在（远程失效） |
|                  撤销变更                   |     git revert 分支记录     | git revert HEAD创建上一个提交的副本作为当前需要撤销的提交的唯一子节点（远程可用） |
|        将一些提交复制到当前位置下面         |   git cherry-pick 提交号    | git cherry-pick c2 c4复制c2c4到HEAD上作为父节点，HEAD按顺序依次指向并最终指向c4的副本 |
|              交互式rebase复制               |   **git rebase -i 操作**    | git rebase -i HEAD~4分离HEAD上移4位后打开可视化界面pick结点实现复制到位移后的HEAD之下 |
|                本地栈式提交                 |  交互式rebase、cherry-pick  | 调试bug时做出的git调试操作，提交时避免提交这些操作，使用rebase和cherry-pick可以实现该效果 |
|                 为提交命名                  |  git tag 标签名 节点提交号  |    git tag v1 c1为提交c1命名v1，标签在树中起到锚点的作用     |
|                    描述                     | git description 任意引用ref | <tag\>\_<numCommits\>\_g<hash\>：<离ref最近的标签\>\_<ref与tag相差多少个提交记录\>\_g<ref的提交哈希\>： |
|      在本地仓库创建远程仓库的一个拷贝       |        **git clone**        |                                                              |
|                  远程分支                   |        origin/分支名        |   <remote name\>/<branch name\>，通常远程仓库名就是origin    |
| 从远程仓库中获取缺失的数据/更新远程分支指针 |          git fetch          | 将远程仓库中本地仓库没有的提交下载到本地仓库，同时origin/main分支与main分支分离（单纯的下载操作） |
|          抓取更新再合并到本地分支           |        **git pull**         |                 git fetch + git merge 的效果                 |
|         将本地的变更上传到远程分支          |          git push           |                                                              |

> ```bash
> $ git config --global user.name "John Doe"
> $ git config --global user.email johndoe@example.com
> ```
