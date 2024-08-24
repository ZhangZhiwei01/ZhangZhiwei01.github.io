点击返回[🔗我的博客文章目录](https://percheung.github.io/#/toc)
* 目录
{:toc}
<div onclick="window.scrollTo({top:0,behavior:'smooth'});" style="background-color:white;position:fixed;bottom:20px;right:40px;padding:10px 10px 5px 10px;cursor:pointer;z-index:10;border-radius:13%;box-shadow:0.5px 3px 7px rgba(0,0,0,0.3);"><img src="https://percheung.github.io/blogImg/backTop.png" alt="TOP" style="background-color:white;width:30px;"></div>

# 从0搭建<img src="https://percheung.github.io/blogImg/github.png" width="60px" alt="" />github.io网页

## 1.成果展示

在我的理解里，`github.io`，不是博客，这是服务器，他是一个可以在路径`https://percheung.github.io/`下存放一切的增强版`nginx`服务器。这篇博客我会讲很多东西，从0讲到我搭建完成。

### 1.1 网址和源码

本项目用vue搭建。

我的博客网址为🔗[https://percheung.github.io](https://percheung.github.io/)

博客的源码仓库网址为[https://github.com/PerCheung/PerCheung.github.io](https://github.com/PerCheung/PerCheung.github.io)

搭建源码页面的仓库网址为[https://github.com/PerCheung/PerCheung.github.io.page](https://github.com/PerCheung/PerCheung.github.io.page)

### 1.2 页面展示

> 主页 index

![image-20240102224451211](https://percheung.github.io/blogImg/202401022244481.png)

> 从上到下有什么功能就不讲了，点击第二个蓝色文件夹图标，进入博客。搜索框支持查找博客内容。

![image-20240102224613654](https://percheung.github.io/blogImg/202401022246886.png)

> 点击即可进去查看文章，这个github.io最棒的地方就是它对markdown文档的在线阅读支持。

![image-20240102224754616](https://percheung.github.io/blogImg/202401022247770.png)

下面开始讲讲我如何搭建起这个主页的。

## 2.new对象

> 我就默认你已经有GitHub账户了。面向对象编程来说，第一步当然是创造对象，下面将github.io仓库的创建。

### 2.1 创建仓库

进入[https://github.com/new](https://github.com/new)，如图。新建仓库{你的GitHub账户名}.github.io，记得勾选public。

![image-20231226165946916](https://percheung.github.io/blogImg/202312261659154.png)

就这么简单，你已经获得了链接为{你的GitHub账户名}.github.io的主页，属于你！

## 3.github.io仓库的初始化

> 我不知道大家创建仓库后，仓库内容是什么样的，我一开始仓库里一无所有。然后在网上搜，网上还有很多教你用`Hexo`帮你搭建起`github.io`的教程，但是我一开始搭建它的时候没有选择这条路，因为太相似了，而且真的搭建成博客了。在我看来他不应该只是一个博客，只能放点文章？这太大材小用了。如果只是为了写博客，我为什么不用CSDN呢？


### 3.1 千里之行，始于足下
> 好了，下面我要从0开始了，这里什么都没有，是空的。

![image-20240102225942492](https://percheung.github.io/blogImg/202401022259651.png)

> 最开始，我只建了一个`README.md`

![image-20240102230045475](https://percheung.github.io/blogImg/202401022300597.png)

然后我跳转我自己的主页[https://percheung.github.io](https://percheung.github.io/)，我发现，页面上有两行字

```html
<h1>PerCheung.github.io</h1>
创建自己的GitHub博客
```

是的，`README.md`居然能被当作网页访问！但我们仅仅有.md文件可不够，md的语法不如html丰富，如果我想要页面更漂亮呢？想要页面能支持博客搜索呢？

### 3.2 _config.yml

我查找资料后知道，`_config.yml`无疑是这个项目最最重要的文件了。但仓库一开始并没有这个文件怎么办呢？答案：新建。（第一张图请忽略，因为我搭建完项目才开始写这篇博客，一开始这几乎里是空白，除了一开始我建了一个README.md）

![image-20240102230451550](https://percheung.github.io/blogImg/202401022304676.png)

![image-20231228171732435](https://percheung.github.io/blogImg/202401020949474.png)

加上这一句后，你再访问你自己的主页，你会发现页面变成蓝色风格了。现在官方具备如下主题。

```yaml
# 主题设置
theme: jekyll-theme-architect
theme: jekyll-theme-cayman
theme: jekyll-theme-dinky
theme: jekyll-theme-hacker
theme: jekyll-theme-leap-day
theme: jekyll-theme-merlot
theme: jekyll-theme-midnight
theme: minima
theme: jekyll-theme-minimal
theme: jekyll-theme-modernist
theme: jekyll-theme-slate
theme: jekyll-theme-tactile
theme: jekyll-theme-time-machine
```

最新的主题有什么具体可以参考[GitHub主题页面](https://pages.github.com/themes/)。

设置好后，你项目里的markdown文件就会随着主题的变化而变化。这里也可以什么主题都不选，那么会有一个默认的主题。

这是我目前`_config.yml`文件内容。

```yaml
# 标题
title: 鸿雁长飞光不度，鱼龙潜跃水成文
# 描述
description: This is my blog
# 主题风格
theme: jekyll-theme-primer
# markdown增强功能
markdown: kramdown
```

前三个很好理解了，看注释就知道是什么，`title`是主页的名字，`description`类似于每个人的qq签名。最后一句`markdown: kramdown`写上，会支持markdown目录功能等。

### 3.3 一点杂活

继续加文件。加`.gitignore`，加`LICENSE`。

## 4.PerCheung.github.io.page

> 下面开始用vue画页面，仓库地址在[PerCheung.github.io.page](https://github.com/PerCheung/PerCheung.github.io.page)

### 4.1 文件目录介绍

我将PerCheung.github.io里的文件都放在vue项目的public下了，比如各个建的`.gitignore`，`LICENSE`，`_config.yml`，`README.md`，然后我将我的博客文章放到了`public/blog`下，将博客文章引用的图片放到`public/blogImg`下。

![image-20240102231532720](https://percheung.github.io/blogImg/202401022315853.png)

### 4.2 打包替换PerCheung.github.io

用项目里的README.md文件中的打包指令会打一个dist文件夹。

![image-20240102231919992](https://percheung.github.io/blogImg/202401022319208.png)

![image-20240102232103882](https://percheung.github.io/blogImg/202401022321016.png)

> 用`dist`的内容替换掉`PerCheung.github.io`里所有的内容即可。

![image-20240102232247956](https://percheung.github.io/blogImg/202401022322101.png)

## 5.技术细节

`github.io`开源项目，是基于`jekyll`，绕不开。

### 5.1 markdown文件怎么支持目录？

#### 5.1.1 修改_config.yml

末尾加上

```yaml
markdown: kramdown
```

#### 5.1.2 修改markdown文件

开头加上

```markdown
* 目录
{:toc}
```

### 5.2 搜索功能的实现

> 这个项目我没用后端的，执意纯前端来实现。我的方法如下。

在文件夹public/blog下，写了一个go文件，文件名叫`toc.go`，代码如下

```go
package main

import (
	"encoding/json"
	"io/ioutil"
	"path/filepath"
	"strings"
)

func main() {
	files, err := ioutil.ReadDir(".")
	if err != nil {
		panic(err)
	}

	var fileNames []string
	for _, file := range files {
		if file.IsDir() {
			continue
		}
		name := strings.TrimSuffix(file.Name(), filepath.Ext(file.Name()))
		if name != "toc" {
			fileNames = append(fileNames, name)
		}
	}

	jsonData, err := json.Marshal(fileNames)
	if err != nil {
		panic(err)
	}

	err = ioutil.WriteFile("toc.json", jsonData, 0644)
	if err != nil {
		panic(err)
	}
}
```

这个代码会将同级目录的文件统计出来，去掉文件后缀，转成一个toc.json。我用命令

```bash
go build -o toc.exe toc.go
```

将go代码打成了exe文件，然后就把go代码删掉了，然后双击执行toc.exe会产生toc.json。

json内容如下。

```json
["HTML5学习记录","markdown各种语法测试","初步领悟C指针","卓别林的演讲","如何搭建github.io网页","搭建多人聊天室（保姆级教学，从0开始）","正则表达式笔记"]
```

这个json是一个字符串数组，内容就是markdown文件名。

然后把他放到vue项目的src/views/TOC.vue里，内容在

```js
data() {
    return {
      search: '',
      toc: ["HTML5学习记录", "markdown各种语法测试", "初步领悟C指针", "卓别林的演讲", "如何搭建github.io网页", "搭建多人聊天室（保姆级教学，从0开始）", "正则表达式笔记"]
    };
  }
```

然后借助搜索框，用search对toc循环出的item做筛选，就实现了搜索功能。

```html
<el-input
            size="small"
            v-model="search"
            prefix-icon="el-icon-search"
            placeholder="搜索文章">
</el-input>
```

```html
<div class="custom_card" v-for="item in filteredToc" :key="item">
          <el-link :href="getLink(item)"
                   :underline="false"
                   target="_blank">
            <i class="el-icon-paperclip"></i>
            {{ item }}
          </el-link>
</div>
```

```js
filteredToc() {
      return this.toc.filter(item =>
          !this.search || item.toLowerCase().includes(this.search.toLowerCase())
      );
    }
```

> 至此，不讲了。博客的搭建是需要自己钻研学习的，更加细枝末节的地方我想不到还有什么好讲的，只能在实际操作中，自己掌握吧。

## 6.限制

### [使用限制](https://docs.github.com/zh/pages/getting-started-with-github-pages/about-github-pages#usage-limits)

GitHub Pages 站点受到以下使用限制的约束：

- GitHub Pages 源存储库的建议限制为 1 GB。有关详细信息，请参阅“[关于 GitHub 上的大文件](https://docs.github.com/zh/repositories/working-with-files/managing-large-files/about-large-files-on-github#file-and-repository-size-limitations)”
  
- 发布的 GitHub Pages 站点不得超过 1 GB。
  
- 如果花费的时间超过 10 分钟，GitHub Pages 部署将超时。
  
- GitHub Pages 站点的软带宽限制为每月 100 GB。
  
- GitHub Pages 站点的软限制为每小时 10 次生成。 如果使用自定义 GitHub Actions 工作流生成和发布站点，则此限制不适用。
  
- 为了为所有 GitHub Pages 站点提供一致的服务质量，可能会实施速率限制。 这些速率限制无意干扰 GitHub Pages 的合法使用。 如果你的请求触发了速率限制，你将收到相应响应，其中包含 HTTP 状态代码 `429` 以及信息性 HTML 正文。

如果你的站点超出这些使用配额，我们可能无法为你的站点提供服务；或者你可能收到来自 GitHub 支持的礼貌电子邮件，建议降低站点对服务器影响的策略，包括将第三方内容分发网络 (CDN) 置于你的站点前，利用GitHub 功能（如发行版）或转用可能更符合需求的其他托管服务。