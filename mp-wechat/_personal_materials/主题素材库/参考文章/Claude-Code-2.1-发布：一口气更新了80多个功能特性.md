最近这一周我几乎都是每天10小时+的在疯狂用Claude Code，又找到了一些做产品的乐趣。尤其是昨天「小猫相册」app在AppStore上线后，我又收到不少反馈，已经在继续疯狂🤪改bug、修体验了。

![图片](https://mmbiz.qpic.cn/mmbiz_png/HRdaeEmxNHaibOvrlZGUEwEUia5AvRgYdP9myAqkaibCyyEibxUIL6KCngZCt9LJVaYlgCYm1pbZTrYNSJa40icAY9A/640?wx_fmt=png&from=appmsg&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=0)

然后，用着用着，突然发现Claude Code 已经跳到2.1版本了。

![图片](https://mmbiz.qpic.cn/mmbiz_png/HRdaeEmxNHaibOvrlZGUEwEUia5AvRgYdPgEEoyonyrRdIVUZ6PoNedCTt6YicRicicF1LCvsc3hoNicghicMO0znMSMg/640?wx_fmt=png&from=appmsg&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=1)

我去查了下，他们是昨天（1月7日）发布的2.1.0，今天又跟了个2.1.1小修复。2026年第一个大版本，这次更新的内容多得离谱，changelog里列了80多条改动，包括：

-   30+项新功能（Skills热重载、语言设置、Vim操作扩展、MCP动态更新等）
    
-   40+项bug修复（安全漏洞、中文输入、终端兼容性等）
    
-   10+项性能和体验优化
    

![图片](https://mmbiz.qpic.cn/mmbiz_png/HRdaeEmxNHaibOvrlZGUEwEUia5AvRgYdPr0BE3pcDS8X2QHENAWreQWicibP8kSKMJDQT88Nk8DysrqwfLxy9sjfw/640?wx_fmt=png&from=appmsg&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=2)

我帮你筛了一遍，挑出最值得关注的。

## 最值得关注的3个新功能

### 1\. Skills自动热重载

这个功能我等了挺久的。

之前的痛点是：你改了`~/.claude/skills`或`.claude/skills`里的skill文件，必须重启Claude Code才能生效。调试一个skill可能要重启十几次，体验很差。

现在不用了。改完skill，立刻生效，不用重启。

这对于正在搭建自己工作流的人来说是个大提升。举个例子，你在写一个代码审查的skill，想调整审查规则的措辞，以前的流程是：改文件→退出Claude Code→重新启动→测试→发现不对→再改→再重启……现在直接改完就能测，迭代速度快了不是一点半点。

另外这次还新增了几个skill相关的功能：

-   context: fork：让skill在隔离的上下文中运行，不会污染主对话
    
-   hooks支持：skill现在可以配置PreToolUse、PostToolUse、Stop这些hooks
    
-   YAML列表格式：allowed-tools字段支持更清晰的YAML列表写法
    

如果你还没开始用Skills，我建议趁这次更新试试。官方的skills仓库有不少现成的例子可以参考：https://github.com/anthropics/skills

### 2\. 可以设置Claude的回复语言了

新增了`language`配置项，比如设置成`"japanese"`，Claude就会用日语回复你。

这个功能看起来简单，但对于非英语母语的开发者挺实用的。之前想让Claude用中文回复，得经常在prompt里提醒"请用中文回复"，或者在CLAUDE.md里写上语言要求。现在直接配置一次就行，一劳永逸。

配置方法：在`settings.json`里加上`language`字段即可，比如：

```
{
  "language": "chinese"
}
```

设置后，Claude的回复会用中文。对于需要写中文注释或者给中文团队用的项目，这个配置很方便。

### 3\. 自动续写，不再报token limit错误

以前Claude写到一半，如果触发了output token limit，就会直接报错停下来。你得手动输入"继续"或者"请接着写"让它继续。

现在改成了自动续写。触发limit后，Claude会自己接着写，不需要你干预。

这个改动看起来很小，但体验提升明显。尤其是这几个场景：

-   让Claude写长文档（比如README、技术设计文档）
    
-   做大范围代码重构
    
-   生成大量测试用例
    
-   批量处理文件
    

以前这些场景经常写到一半断掉，你得盯着屏幕等。现在可以放心让它跑，回来看结果就行。

顺带一提，subagent（子任务）也有类似的改进：权限被拒绝后会自动尝试其他方案，而不是直接停下来报错。这让长时间运行的任务更可靠了。

## 小改进，但很实用

### Shift+Enter多终端开箱即用

之前想在输入框里换行，不同终端的支持情况不一样，有的要配置。

现在iTerm2、WezTerm、Ghostty、Kitty这几个终端都开箱即用了。按Shift+Enter就能换行，不用折腾配置。

### 斜杠命令任意位置触发

以前斜杠命令只有在行首输入`/`才会触发自动补全。

现在任意位置输入`/`都能触发。比如你打字打到一半，想插入一个命令，直接打`/`就能补全，不用删掉前面的内容。这个太实用了

### 新增/plan快捷命令

想进入plan模式？直接在prompt里加`/plan`就行，不用再去菜单里找了（不过我咋记得这特么早就有了）

### 通配符Bash权限

现在可以用通配符来配置Bash权限了，比如：

-   Bash(npm \*) - 允许所有npm命令
    
-   Bash(git \* main) - 允许所有针对main分支的git命令
    

比之前一个个配置方便多了。

## MCP动态更新

这个功能偏进阶，但如果你在用MCP服务器，值得了解一下。

之前MCP服务器的工具列表是启动时加载的，运行过程中不能变。现在支持了`list_changed`通知，MCP服务器可以动态添加、删除、修改工具。

实际用处：

-   你可以写一个MCP服务器，根据当前项目类型动态暴露不同的工具
    
-   或者根据用户权限动态调整可用工具
    
-   甚至可以实现"插件热插拔"的效果
    

这个改动让MCP的玩法更灵活了。如果你在做自定义工具链，可以研究一下。

## 安全提醒：敏感信息泄露修复

这个要单独说一下，因为涉及安全问题。

之前的版本有个bug：OAuth tokens、API keys、密码这些敏感信息会出现在debug日志里。

如果你之前开启过debug模式，或者把debug日志分享给别人帮忙排查问题，建议检查一下有没有泄露风险。

这个版本已经修复了，敏感信息会被过滤掉。但历史日志如果还留着，建议清理一下。

## Vim用户的福音

> 什么是Vim模式？Vim是一款经典的文本编辑器，特点是纯键盘操作，不用鼠标。很多程序员习惯了Vim的快捷键（比如用`h/j/k/l`移动光标，用`dd`删除整行），在其他工具里也想用同样的操作方式。Claude Code支持Vim模式，让这些用户可以用熟悉的方式编辑输入内容。
> 
> 如果你不用Vim，这部分可以跳过。

这次Vim模式的更新挺多的，Anthropic显然是听到了社区的反馈。

新增的操作：

|快捷键|功能|
|---|---|
|; 和 ,|重复f/F/t/T跳转|
|y操作符|复制，支持yy整行、Y到行尾|
|p / P|粘贴（光标后/光标前）|
|\>> / <<|缩进/取消缩进|
|J|合并当前行和下一行|

新增的文本对象：

终于支持`iw`（inner word）、`aw`（a word）这些了。完整列表：

-   iw, aw, iW, aW - 单词
    
-   i", a", i', a' - 引号内容
    
-   i(, a(, i\[, a\[, i{, a{ - 括号内容
    

现在可以`ciw`（删除单词并进入插入模式）、`yi"`（复制引号内的内容）这些操作了。

几个实用场景：

-   想快速改掉一个变量名？ciw删除当前单词并进入插入模式，直接打新名字
    
-   想复制引号里的字符串？yi"搞定
    
-   想把两行合并成一行？J
    
-   想批量缩进代码块？>>或者visual模式选中后>
    

之前这些操作在Claude Code里都做不了，只能用基础的hjkl移动。现在终于补上了。

## 还有一些bug修复

挑几个比较影响体验的：

中文用户相关：

-   修复了中日韩字符输入时多余空行的问题——之前在多行输入框里打中文，经常会莫名其妙多出空行，现在好了
    

稳定性相关：

-   修复了LSP启动时的竞争条件——之前偶尔会报"no server available"，尤其是刚启动的时候
    
-   修复了大文件粘贴失败的问题——之前粘贴大图片会报"Image was too large"错误
    
-   修复了git diff解析的内存泄漏——长对话不再越来越卡，这个改进对于跑长任务的用户很重要
    

终端兼容性：

-   修复了Ghostty、iTerm2、Kitty、WezTerm的键盘模式问题——退出Claude Code后终端不会出现奇怪的输入问题了
    
-   修复了这些终端下Alt+B和Alt+F不工作的问题——现在可以正常用Alt键做单词跳转了
    

## 我的升级建议

建议升级。这个版本的改动都是正向的，没有什么breaking change会影响你的工作流。

有个小变化：进入plan模式不再需要权限确认了，可以直接进入。

升级命令：

```
npm update -g @anthropic-ai/claude-code
```

升完可以用`claude --version`确认版本号，应该显示2.1.1。

特别推荐升级的人：

-   正在搭建Skills工作流的——热重载太香了，开发效率翻倍
    
-   Vim重度用户——操作更完整了，不用再忍受残缺的vim模式
    
-   中文用户——输入bug修复了，体验会好很多
    
-   跑长任务的用户——内存泄漏修复+自动续写，稳定性提升明显
    

## 写在最后

从这次更新能看出Anthropic的产品思路：Claude Code要做的是一个完整的开发环境，而不只是一个AI助手。

Vim模式越来越完整、终端兼容性越做越好、Skills和MCP生态在持续建设……这些都指向同一个方向：让开发者可以把Claude Code当作主力开发工具，而不是偶尔调用的辅助工具。

和Cursor、Windsurf这些走"IDE插件"路线的产品相比，Claude Code选择了更重的路线。好不好用，还得看后续迭代。

___

以上就是Claude Code 2.1的核心更新。完整changelog可以到GitHub仓库查看：https://github.com/anthropics/claude-code/blob/main/CHANGELOG.md

以及，如果你想试试我的小猫相册的话，欢迎到AppStore搜索体验，然后给我反馈～

虽然1.0版本还不够完美，但...我相信你会获得些「哇哦，还能这么干么」的小惊喜！

已经下载的朋友也可以期待下我这周末会更新的1.2版本，真的挺nb的。

![图片](https://mmbiz.qpic.cn/mmbiz_png/HRdaeEmxNHaibOvrlZGUEwEUia5AvRgYdPFgHpPDnNsxuDvOR2OJqUIUVW9ib6Q8MyiarfE11ibo7r7E0fVdvwWOVmg/640?wx_fmt=png&from=appmsg&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=3)