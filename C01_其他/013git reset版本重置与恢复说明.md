> Tags: #git #版本控制

- [1 013git reset版本重置与恢复说明](#1%20013git%20reset%E7%89%88%E6%9C%AC%E9%87%8D%E7%BD%AE%E4%B8%8E%E6%81%A2%E5%A4%8D%E8%AF%B4%E6%98%8E)
	- [1.1 git reset 的操作方式](#1.1%20git%20reset%20%E7%9A%84%E6%93%8D%E4%BD%9C%E6%96%B9%E5%BC%8F)
	- [1.2 git reset 的三种模式区别](#1.2%20git%20reset%20%E7%9A%84%E4%B8%89%E7%A7%8D%E6%A8%A1%E5%BC%8F%E5%8C%BA%E5%88%AB)
	- [1.3 git 本地提交流程](#1.3%20git%20%E6%9C%AC%E5%9C%B0%E6%8F%90%E4%BA%A4%E6%B5%81%E7%A8%8B)
	- [1.4 git reset 的机制简要说明](#1.4%20git%20reset%20%E7%9A%84%E6%9C%BA%E5%88%B6%E7%AE%80%E8%A6%81%E8%AF%B4%E6%98%8E)
- [2 git Reset 操作后恢复方式](#2%20git%20Reset%20%E6%93%8D%E4%BD%9C%E5%90%8E%E6%81%A2%E5%A4%8D%E6%96%B9%E5%BC%8F)
- [3 更新日志](#3%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 013git reset版本重置与恢复说明

- 我们使用 Git 做版本控制的时候有可能 commit 提交代码后，发现这一次 commit 的内容是有错误的或者是无效的，那么有两种处理方法：
    - 1、修改错误内容，再次 commit 一次
        - 比较直接，但会多次一次 commit 记录。
    - 2、使用**git reset** 命令撤销这一次错误的 commit
        - 错误的 commit 不会保留下来。

## 1.1 git reset 的操作方式

- ![](FILES/013git%20reset版本重置与恢复说明/image-20240218152245768.png)

## 1.2 git reset 的三种模式区别

- ⭐ 若不想了解细节，就选择 Hard 模式，硬重置，直接跳版本，直接强制回退，所有修改全清。
- git reset 总共有三种模式 soft,mixed,hard，主要的区别为回退时保留的内容
- ![](FILES/013git%20reset版本重置与恢复说明/image-20240219104042844.png)
- **--hard**：重置位置的同时，直接将 **working Tree 工作目录**、 **index 暂存区**及 **repository** 都重置成目标**Reset**节点的內容,所以效果看起来等同于**清空暂存区和工作区**
    - 一般建议直接使用此方式，硬重置。
    - (1) **要放弃目前本地的所有改变時**，即去掉所有 add 到暂存区的文件和工作区的文件，可以执行 **git reset -hard HEAD** 来强制恢复 git 管理的文件夹的內容及状态；
    - (2) **真的想抛弃目标节点后的所有 commit**（可能觉得目标节点到原节点之间的 commit 提交都是错了，之前所有的 commit 有问题）。
- **--soft**：重置位置的同时，保留**working Tree 工作目录**和**index 暂存区**的内容，只让**repository**中的内容和 **reset** 目标节点保持一致，因此原节点和**reset**节点之间的【差异变更集】会放入**index 暂存区**中(**Staged files**)。所以效果看起来就是工作目录的内容不变，暂存区原有的内容也不变，只是原节点和**Reset**节点之间的所有差异都会放到暂存区中。
    - 原节点和**reset**节点之间的【差异变更集】会放入**index 暂存区**中(**Staged files**)，所以假如我们之前工作目录没有改过任何文件，也没 add 到暂存区，那么使用**reset --soft**后，我们可以直接执行 **git commit** 將 index 暂存区中的內容提交至 **repository** 中。
    - **可以使用--soft 合并 commit 节点**。
        - 这样做的使用场景是：假如我们想合并「当前节点」与「**reset**目标节点」之间不具太大意义的 **commit** 记录(可能是阶段性地频繁提交,就是开发一个功能的时候，改或者增加一个文件的时候就**commit**，这样做导致一个完整的功能可能会好多个**commit**点，这时假如你需要把这些**commit**整合成一个**commit**的时候)時，可以考虑使用**reset --soft**来让 **commit** 演进线图较为清晰。
- **--mixed（默认）**：重置位置的同时，只保留**Working Tree 工作目录**的內容，但会将 **Index 暂存区** 和 **Repository** 中的內容更改和 reset 目标节点一致，因此原节点和**Reset**节点之间的【差异变更集】会放入**Working Tree 工作目录**中。所以效果看起来就是原节点和**Reset**节点之间的所有差异都会放到工作目录中
    - (1)使用完**reset --mixed**后，我們可以直接执行 **git add** 将這些改变果的文件內容加入 **index 暂存区**中，再执行 **git commit** 将 **Index 暂存区** 中的內容提交至**Repository**中，这样一样可以达到合并**commit**节点的效果（与上面--soft 合并 commit 节点差不多，只是多了 git add 添加到暂存区的操作）；
    - (2)移除所有 Index 暂存区中准备要提交的文件(Staged files)，我们可以执行 **git reset HEAD** 来 **Unstage** 所有已列入 **Index 暂存区** 的待提交的文件。(有时候发现 add 错文件到暂存区，就可以使用命令)。
    - (3)**commit**提交某些错误代码，或者没有必要的文件也被**commit**上去，不想再修改错误再**commit**（因为会留下一个错误**commit**点），可以回退到正确的**commit**点上，然后所有原节点和**reset**节点之间差异会返回工作目录，假如有个没必要的文件的话就可以直接删除了，再**commit**上去就 OK 了

## 1.3 git 本地提交流程

- ![](FILES/013git%20reset版本重置与恢复说明/image-20240218163654236.png)

## 1.4 git reset 的机制简要说明

- **git reset** 的机制是可以让 HEAD 这个指针指向其他的地方。（← 此处信息大致了解即可）
    - 例如我们有一次 commit 不是不是很满意，需要回到上一次的 Commit 里面。那么这个时候就需要通过 reset，把 HEAD 指针指向上一次的 commit 的点。
- 机制说明
    - 在 HEAD 指针进行移动后，原先的 4 以及当前工作区与暂存区的版本变更记录应该怎么操作，就分为三种模式。
    - ![](FILES/013git%20reset版本重置与恢复说明/4428238-75ef41dc9eec6f8e.webp)

# 2 git Reset 操作后恢复方式

- 前提说明
    - hard 模式会重置工作目录到某一次提交，从而可能导致代码的丢失。
    - 误操作后，不要慌，因为 git 在内部保存了一个引用日志，可以帮助我们找回丢失的提交。
- 操作思路
    - 通过命令行，通过 git reflog 命令找到想回复的那条版本提交记录的 hash 值，使用 git checkout 恢复内容，使用 git branch 修改 master 指向。
    - ![](FILES/013git%20reset版本重置与恢复说明/image-20240218165456394.png)
- 第<span style="background:#F0A7D8"> 1 </span>步：
    - 点击 Sourcetree 中的 Terminal 按钮
    - ![](FILES/013git%20reset版本重置与恢复说明/image-20240205180450608.png)
- 第<span style="background:#F0A7D8"> 2 </span>步：
    - 在命令行中输入 `git reflog`
    - 查看注释信息，记下需要恢复的版本对应的 hash 值 `9a654ef`
    - ![](FILES/013git%20reset版本重置与恢复说明/image-20240218154220587.png)
- 第<span style="background:#F0A7D8"> 3 </span>步：
    - 使用需要恢复版本的 hash 值
    - 输入 `git checkout 91654ef`
    - ![](FILES/013git%20reset版本重置与恢复说明/image-20240218154351824.png)
    - 输入完成后，刷新 Sourcetree，发现原本记录已经出现了，但名称是 HEAD
    - ![](FILES/013git%20reset版本重置与恢复说明/image-20240218154441880.png)
- 第<span style="background:#F0A7D8"> 4 </span>步：
    - 使用 `git branch -f master HEAD` 强制将当前分支的 master 指向 HEAD
    - ![](FILES/013git%20reset版本重置与恢复说明/image-20240218155154165.png)
    - 强制修改分支位置说明
        - 可以直接使用 `-f` 选项让分支指向另一个提交。例如:
            - `git branch -f master HEAD`
            - 上面的命令会将 master 分支强制指向 HEAD 的提交。
            - ![](FILES/013git%20reset版本重置与恢复说明/image-20240218155209149.png)

# 3 更新日志

| 日期     | 修改人     | 修改内容     |
|:-----|:-----|:-----|
| 2024-02-19     | YuanZhiyi     | 初次创建     |
