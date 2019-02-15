# The Minimal theme

[![Build Status](https://travis-ci.org/pages-themes/minimal.svg?branch=master)](https://travis-ci.org/pages-themes/minimal) [![Gem Version](https://badge.fury.io/rb/jekyll-theme-minimal.svg)](https://badge.fury.io/rb/jekyll-theme-minimal)

*Minimal is a Jekyll theme for GitHub Pages. 你可以 [瞅瞅它长啥样](http://pages-themes.github.io/minimal), 或 [立即使用](#usage).*

![Thumbnail of minimal](thumbnail.png)

## 用法

使用 Minimal 主题:

1. 添加下面的代码到文件 `_config.yml`中，用来设置主题:

    ```yml
    theme: jekyll-theme-minimal
    ```
2. __Optionally, if you'd like to preview your site on your computer, add the following to your site's Gemfile:__

    ```ruby
    gem "github-pages", group: :jekyll_plugins
    ```
    
## 自定义

### 配置变量

把下面代码添加到你的网站的 `_config.yml`文件中，来设置标题和描述:

```yml
title: "The title of your site"
description: "A short description of your site's purpose"
```

此外你也可做其它的设定(logo路径，下载按钮和谷歌分析)，还可自定义变量 "配置信息" 在模板中使用:

```yml
logo: [Location of the logo]
show_downloads: ["true" or "false" to indicate whether to provide a download URL]
google_analytics: [Your Google Analytics tracking ID]
```

### 样式

如果喜欢的话，可以自定义样式:

1. 在指定文件`/assets/css/style.scss`夹下创建文件(与`_config.yml`同根目录)
2. 在文件style.scss中添加以下内容
    ```scss
    ---
    ---

    @import "{{ site.theme }}";
    ```
3. 自定义css内容追加在 @import "{{ site.theme }}"; 后面

### Layouts布局

如果喜欢的话，可以改变主题提供的HTML布局:

```html
<!DOCTYPE html>
<html lang="{{ site.lang | default: "en-US" }}">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">

{% seo %}
    <link rel="stylesheet" href="{{ "/assets/css/style.css?v=" | append: site.github.build_revision | relative_url }}">
    <!--[if lt IE 9]>
    <script src="//cdnjs.cloudflare.com/ajax/libs/html5shiv/3.7.3/html5shiv.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <div class="wrapper">
      <header>
        <h1><a href="{{ "/" | absolute_url }}">{{ site.title | default: site.github.repository_name }}</a></h1>
        
        {% if site.logo %}
          <img src="{{site.logo | relative_url}}" alt="Logo" />
        {% endif %}

        <p>{{ site.description | default: site.github.project_tagline }}</p>

        {% if site.github.is_project_page %}
        <p class="view"><a href="{{ site.github.repository_url }}">View the Project on GitHub <small>{{ site.github.repository_nwo }}</small></a></p>
        {% endif %}

        {% if site.github.is_user_page %}
        <p class="view"><a href="{{ site.github.owner_url }}">View My GitHub Profile</a></p>
        {% endif %}

        {% if site.show_downloads %}
        <ul class="downloads">
          <li><a href="{{ site.github.zip_url }}">Download <strong>ZIP File</strong></a></li>
          <li><a href="{{ site.github.tar_url }}">Download <strong>TAR Ball</strong></a></li>
          <li><a href="{{ site.github.repository_url }}">View On <strong>GitHub</strong></a></li>
        </ul>
        {% endif %}
      </header>
      <section>

      {{ content }}

      </section>
      <footer>
        {% if site.github.is_project_page %}
        <p>This project is maintained by <a href="{{ site.github.owner_url }}">{{ site.github.owner_name }}</a></p>
        {% endif %}
        <p><small>Hosted on GitHub Pages &mdash; Theme by <a href="https://github.com/orderedlist">orderedlist</a></small></p>
      </footer>
    </div>
    <script src="{{ "/assets/js/scale.fix.js" | relative_url }}"></script>
    {% if site.google_analytics %}
    <script>
      (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
      (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
      m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
      })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
      ga('create', '{{ site.google_analytics }}', 'auto');
      ga('send', 'pageview');
    </script>
    {% endif %}
  </body>
</html>
```

1. [从该链接复制模板内容（即上代码）](https://github.com/pages-themes/minimal/blob/master/_layouts/default.html) 
2. 还是在指定文件夹下创建文件`/_layouts/default.html`
3. 粘贴上面的模板内容
4. 自己看着修改

## 路线图

有关建议功能[已知问题](https://github.com/pages-themes/minimal/issues)的列表，请参阅未解决的问题。

## 项目理念

Minimal主题旨在让GitHub Pages用户快速轻松地创建他们的第一个（或第100个）网站。该主题应该满足绝大多数用户的开箱即用需求，在简单性而不是灵活性方面犯错，并且如果用户有特定需求或希望进一步定制他们的体验，则为用户提供选择加入其他复杂性的机会。 （例如添加自定义CSS或修改默认布局）。它应该看起来很棒，但不言而喻。

## 特约

有兴趣为Minimal做贡献吗？我们热爱你的帮助。Minimal是一个开源项目，由像您这样的用户一次构建一个贡献。有关如何贡献的说明，请参阅[CONTRIBUTING](https://github.com/ljyeso/ljyeso.github.io/blob/master/docs/CONTRIBUTING.md)文件。

### 在本地预览主题

如果您想在本地预览主题（例如，在提议更改的过程中）：

1. 克隆主题的存储库（git clone https://github.com/pages-themes/minimal）
2. cd 进入主题的目录
3. 运行script/bootstrap以安装必要的依赖项
4. 运行bundle exec jekyll serve以启动预览服务器
5. 访问localhost:4000您的浏览器以预览主题

### 运行测试

该主题包含一个最小的测试套件，以确保主题成功构建的网站。要运行测试，只需运行即可script/cibuild。script/bootstrap在测试脚本运行之前，您需要运行一个。
