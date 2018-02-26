mkdir learngit
cd learngit
git init


初始化一个Git仓库，使用git init命令
git add readme.txt

添加文件到Git仓库，分两步：

第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；
第二步，使用命令git commit，完成。
git add file1.txt
git add file2.txt file3.txt
git commit -m "add 3 files."

如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
修改后提交
git add file1.txt
git commit -m "something."

在Git中，用HEAD表示当前版本，也就是最新的提交3628164...882e1e0（注意我的提交ID和你的肯定不一样），
上一个版本就是HEAD^，上上一个版本就是HEAD^^，
当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。

在Git中，总是有后悔药可以吃的。
当你用$ git reset --hard HEAD^回退到add distributed版本时，
再想恢复到append GPL，就必须找到append GPL的commit id。
Git提供了一个命令git reflog用来记录你的每一次命令：

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，
用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，
想丢弃修改，分两步，第一步用命令git reset HEAD file，
就回到了场景1，第二步按场景1操作。