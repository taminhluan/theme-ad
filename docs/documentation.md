# Theme Art Design Theme Chinese Document

## 0. Some instructions

The document is long. If you are a hixo old player or have used `theme-bmw`, you can consider opening the right directory directly and reading the required chapters.

Putting the contact information at the beginning, I am really afraid that everyone will not be patient. (There are a lot of fun features, don't miss it).

- Email:yuanxin.me@gmail.com
- QQ group: 534018786
- Website message

## 1. Install Art Design

### Download theme

Under the terminal window, navigate to the Hexo site directory. Use the `Git` checkout code:

```ba
Cd your-blog
Git clone https://github.com/dongyuanxin/theme-ad.git themes/ad
```

### Enable theme

When the clone/download is complete, open the **Site Profile** and you need to complete the following 2 things:

1. **Must do **: Find the `theme` field and change its value to `ad`.
2. **Recommended**: Find the `permalink` field and change it to `passages/:title/`.

```yml
#位置: probably located at 18 lines
Permalink: passages/:title/ # If you need to turn on comments and article statistics, please edit this configuration

#位置: probably at line 76
Theme: ad # Enable "Art Design" theme
```

Now, run `hexo s` to see what the theme looks like!

## 2. Article release

### file name

In order to better identify the article and prevent duplication, the naming of the markdown file corresponding to the article should follow the format: `YYYY-MM-DD-title`.

For example, today is March 3, 2019, and the content of the article is related to ES6. Then the file name is `2019-03-03-es6.md`.

### Front-matter

The theme automatically generates the corresponding page and rendering UI through the information in the article Front-matter.

Below is a qualifying Front-matter:

```yml
---
Title: "Article title"
Date: 2018-11-28
Categories: Article Category # Category can only have 1
Tags: # tags can have multiple
- Tag 1
- Tag 2
- More tags
Cover: "https://text.com/demo.png" #Article cover image URL
---
```

### Summary and text

The `AD` theme recommends separately writing the abstract and body of the article, showing that the page renders the abstract part of the article, and the article page renders the body of the article.

**Method 1**: It is recommended to use `<!-- more -->`, in addition to the precise control of the excerpts that need to be displayed, this method can also make the plug-ins in Hexo better recognized.

```yml
The article abstract is written in front and supports the markdown syntax.

<!-- more -->

The body of the article is written here.
```

**Method 2**: Set the `description` field in Front-matter. This approach overrides the summary of Method 1 and only supports native text.

```yml
---
Title: "Article title"
Date: 2018-11-28
Description: "Article summary..."
Categories: 
Tags: 
---
```

### Password Blocking

Today, as data privacy becomes more important, the topic provides **password blocking** functionality for articles.

The theme uses the `sha256` irreversible encryption algorithm. For example, the password is `godbmw`, then the password field placed in the configuration file should be: `efe07af7441da2b69c4a41e42e73be4db47f66010a569007884458354a7373ec`

**Method 1**: Modify the `passwords` field in the theme configuration file, for example:

```yml
Passwords: 
  - efe07af7441da2b69c4a41e42e73be4db47f66010a56900788a458354a7373ec 
```

**Method 2**: Set the `passwords` field in the Front-matter of the specified article, for example:

```yml
---
Title: "Article title"
Date: 2018-11-28
Categories: 
Tags: 
Passwords: 
  - efe07af7441da2b69c4a41e42e73be4db47f66010a56900788a458354a7373ec
---
```

**note**:

1. The `passwords` added by Method 1 has read access to all locked articles. Can be used to save passwords that only you know, easy to read.
2. The `passwords` added by method 2 only has the read permission of the corresponding article. You can open a corresponding permission to a specific person, such as him/her.
3. The password has a 72-hour expiration date. Once it has exceeded 72 hours, the next reading needs to be re-entered.
4. ** Only with interception and alerting, not completely secure**.

## 3. Theme configuration

**Note**: Please modify the following configuration in the **Subject Profile**. And the priority of the configuration information is: Subject Profile > Site Profile > Theme Default Profile.

### Setting the navigation bar

Change the `nav_name` and `motto` fields and modify the text logo and subtitle/motto on the left side of the navigation bar, for example:

```yml
Nav_name: GODBMW # navigation bar header name

Motto: "Quiet to write something" # Navigation bar motto
```

Change the `nav` field to modify the quick jump link for the navigation bar.

**Note**: Do not modify this field if you have not read the documentation in detail.

### Open the Tag Cloud page

The "Tag Cloud" page shows all the tags for the site, and the theme is that you have designed the relevant UI.

1. Create a tab page: `hexo new page tags`

2. Configuration tab: Modify the Front-matter of the md file (`your-blog/source/tags/index.md`) corresponding to the tab page, and add the `type` attribute to it.

   ```yml
   ---
   Title: tags
   Date: 2019-02-15 14:51:22
   Type: "tags" # must be explicitly set to "tags"
   ---
   ```

### Open the Category page

The Categories page shows all the categories of the site, and the theme is that you have designed the relevant UI.

1. Create a category page: `hexo new page categories`

2. Configure the classification page: modify the Front-matter of the md file (`your-blog/source/categories/index.md`) corresponding to the classification page, and add the `type` attribute to it.

   ```yml
   ---
   Title: categories
   Date: 2019-02-15 14:51:22
   Type: "categories" # must be explicitly set to "categories"
   ---
   ```

### Open the "Friend Chain" page

The friend chain interface is designed for the friend chain and uses a card-style UI.

1. Create a friend page: `hexo new page friends`

2. Configure the friend chain page: modify the Front-matter of the md file (`your-blog/source/friends/index.md`) corresponding to the friend page, and add the `type` attribute to it.

   ```yml
   ---
   Title: friends
   Date: 2019-02-15 21:52:40
   Type: "friends" # must be explicitly set to "friends"
   ---
   ```

3. Write the contents of the friend page: Write the content directly in the md file (`your-blog/source/friends/index.md`) corresponding to the friend page, and the related content will be automatically rendered to the friend page. It is recommended to place the information and requirements for the friend chain; of course, you can also not write anything.

### Open the "Introduction" page

The introduction page is designed for individual presentations, where you can place site information, resumes, and more.

1. Create an introduction page: `hexo new page about`

2. Configuration introduction page: Modify the Front-matter of the md file (`your-blog/source/about/index.md`) corresponding to the introduction page, and add the `type` attribute to it.

   ```yml
   ---
   Title: about
   Date: 2019-02-15 21:34:33
   Type: "about" # must be explicitly set to "about"
   ---
   ```

3. Write the introduction page: Write the content directly in the md file (`your-blog/source/about/index.md`) corresponding to the introduction field, and the related content will be automatically rendered to the introduction page.

### Setting "code highlighting theme"

`AD` Use [Tomorrow Theme] (https://github.com/chriskempson/tomorrow-theme) as the code highlight, there are 5 themes for you to choose. `AD` defaults to the white `night eighties` theme. The optional values ​​are `normal`, `night`, `night blue`, `night bright`, `night eighties`

Change the `highlight_theme` field and select the corresponding topic, for example:

```yml
Highlight_theme: night eighties
```

### Setting up "mathematical formula rendering"

In order to facilitate the display and writing of articles in the fields of mathematics, deep learning, physical engineering, etc., the theme provides comprehensive support for the `Latex` mathematical formula.

Change the `mathjax` field to enable math formula rendering:

```yml
Mathjax: true
```

### Setting up a friendship link

Change the `friends` field and add friendchain information, for example:

```yml
Friends:
  -
    Nickname: GodBMW # 友chain name
    Avatar: /images/friends/godbmw.jpeg # 友链头像
    Site: https://godbmw.com/ #友链地址
    Meta: Theme Author # 友链介绍
    Show: true # Whether to show this friend chain
```

If your friend avatars are saved on other servers, you can configure the prefix address by changing the `friends_avatar_cdn` field, for example:

```yml
Friends_avatar_cdn: "https://godbmw.com/blog-static"
```

**Note**: This feature requires the "Friend Chain" page to be opened correctly.

### Open the sidebar to share links

The sidebar share supports fast sharing of a total of 5 popular social platforms for twitter, facebook, weibo, qq and wechat, which can be used to allow viewers to quickly share any **pages.

Change the `share` field and select the social platform, for example:

```yml
Share:
  Twitter: true # true is on
  Facebook: false # false is off
  Weibo: true
  Qq: true
  Wechat: true
```

### Open the reward function

With the advent of the paid reading era, the reward function with "two-dimensional code" as the payment method has been added, and the QR code information of an unlimited number of payment platforms can be added.

Change the `reward` field and add a bonus QR code, for example:

```yml
Reward:
  -
    Src: /images/wechat.png # QR code image address
    Alt: "WeChat" # QR code information
  -
    Src: /images/alipay.png
    Alt: "AliPay"
```

### Open copyright protection

The theme globally listens to all the copy operations of the viewer on the website, and automatically adds the copyright information of the website to the content.

However, for robots that automatically crawl websites, such as search engine**, you need to add copyright information at the bottom of the article to achieve the purpose of copyright claim.

Change the `copyright` field to turn on copyright protection, for example:

```yml
Copyright:
  Enable: true # whether to enable
  Author: "董沅鑫" #作者信息
  Show_link: true # Whether to show article links
  More: 'Copyright Notice: All articles in this blog use the CC BY-NC-SA 4.0 license agreement unless otherwise stated. Please indicate the source!' #Custom field, support HTML rendering
```

### Github Fast Track

The theme provides a Github quick jump button in the upper right corner of the page. You can place a personal github address, a blog post repository address, and more.

Change the `github` field, for example:

```yml
Github: "https://github.com/dongyuanxin/"
```

## 4. Advanced settings

**Note**: In addition to the "Configure Static Image CDN" modification **`package.json`**, the other is to modify the ** theme configuration file**.

### Leancloud

The comment function, PV statistics and reminder functions of the theme are all based on the `Leancloud` platform. With the help of `ServerLess`, no background service and unified data management are realized.

Change the `leancloud` field, for example:

```yml
Leancloud:
  Appid: Hyq9wkH495DgNHWhDQCOfQSp-gzGzoHsz # Fill in your appid
  Appkey: WaR7nrzhliHj9aVwdQzkdlGd # Fill in your appkey
```

**Note**: Please replace the example in the theme configuration file with `appid` and `appkey` of your account application.

### Comment function

The comment data is in the `Comment` table of your `Leancloud` account.

Change the `leancloud.comment` field, for example:

```yml
Leancloud:
  Appid: Hyq9wkH495DgNHWhDQCOfQSp-gzGzoHsz # Fill in your appid
  Appkey: WaR7nrzhliHj9aVwdQzkdlGd # Fill in your appkey
  Comment: true # Open comment function
```

### PV Statistics

The PV data is in the `Counter` table of your `Leancloud` account. At the same time, the PV data will be displayed in the footer.

Change the `leancloud.count` field, for example:

```yml
Leancloud:
  Appid: Hyq9wkH495DgNHWhDQCOfQSp-gzGzoHsz # Fill in your appid
  Appkey: WaR7nrzhliHj9aVwdQzkdlGd # Fill in your appkey
  Count: true # Whether to open article statistics
```

### Access reminder function

Turning on this feature will remind you when the viewer first enters the website; if the viewer has not logged in to the website for more than a certain period of time (default 30 days), the theme will automatically remind you.

Change the `leancloud.welcome` field, for example:

```yml
Welcome: 
  Enable: true # Whether to enable the reminder function
  Interval: 30 # How long does it take to remind again, unit: day
```

**Note**: The reminder function needs to enable `Leancloud`.

### SEO Optimization

In order to make the website more easily indexed by search engines and get higher SEO, the theme provides automatic push services for Baidu, Google and 360.

Change the `analytics` field, for example:

```yml
Analytics:
  Baidu:
    Enable: true # Enable automatic push to Baidu
  Google:
    Enable: true # Turn on automatic push to Google
    Id: # id of the Google tracking code
  "360":
    Enable: true # Enable automatic push to 360
    Id: # 360 tracking code id
```

**Note**: 360 and Google's automatic push, you need the id of the tracking code of the corresponding platform, please refer to the manual content of the corresponding platform.

### Configuring a static picture CDN

To make it easier to manage articles and static image resources, the topic provides a configuration static resource CDN.

Change the `imgcdn` field of the `package.json` file under the theme folder, for example:

```json
{
  "imgcdn": "https://godbmw.com/blog-static"
}
```

If you use image resources in the article, such as `![](/images/test.png)`. Will be replaced with: `https://godbmw.com/blog-static/images/test.png`.

With this feature, users can deploy static image resources on CDN or other servers. The article repository only stores the corresponding `Markdown` of the article. Avoid the size of the warehouse caused by static image resources as the number of articles increases.

### Bottom navigation bar

The bottom navigation bar uses a multi-column and multi-line "barrier" layout, which can be used to place content such as "recommended blog", "open source project", "special support", etc., which are not commonly used in the main body of the website.

Change the `footer` field, for example:

```yml
Footer:
  - 
    Title: "Blog recommendation"
    Children:
      - 
        Name: "GodBMW"
        Path: "https://godbmw.com/"
      - 
        Name: "阮一峰's personal website"
        Path: "http://ruanyifeng.com/"
  -
    Title: "Catch me"
    Children: 
      -
        Name: "Nuggets"
        Path: "https://juejin.im/user/5b91fcf06fb9a05d3c7fd4a5"
      -
        Name: "Know"
        Path: "https://www.zhihu.com/people/godbmw/activities"
```

### Other information at the bottom

Change the `footer_contact` field and fill in your contact details, for example:

```yml
Email: yuanxin.me@gmail.com
```

Change the `start_time` field and fill in the setup time, for example:

```yml
Start_time: "2018-02-10"
```

### Custom scripts and style files

Change the `custom_styles` field to introduce a custom style file, for example:

```yml
Custom_styles: 
  - style.css
  - style2.css
```

Change the `custom_scripts` field to introduce a custom script file, for example:

```yml
Custom_scripts: 
  - script.js
  - script2.js
```

**Note**: In order not to block the page, the custom script file is inserted before `</body>` instead of `<head>`.

## 5. Warning

### Respect original

1. You can modify the description at the bottom of the page according to your personal needs, but please do not remove the copyright notice of the theme of "theme-ad". 
2. The review system uses `Valine`, please do not remove the copyright notice of the Valley. 
3. Respect originality and wish you a happy time in the open source community

### Web Security

If you have the `Leancloud` platform enabled, as well as related commenting features, PV features or access reminders, please read this section carefully!

With the help of `Leancloud` to circumvent the back-end deployment, the fool-like one-click launch related functions. But with it, the security issues caused by `appid` and `appkey` exposed in the browser environment.

Please go to `leancloud` in your application => left navigation bar => Settings => Security Center to configure:

![](https://godbmw.com/blog-static/images/%E5%BC%80%E6%BA%90%E9%A1%B9%E7%9B%AE/Theme-BMW%E4%B8 %AD%E6%96%87%E6%96%87%E6%A1%A3/8.png)

First, turn off the unwanted "service switches" (only the "data store" service is reserved):

![](https://godbmw.com/blog-static/images/%E5%BC%80%E6%BA%90%E9%A1%B9%E7%9B%AE/Theme-BMW%E4%B8 %AD%E6%96%87%E6%96%87%E6%A1%A3/9.png)

Finally, set up your "Web" secure domain name (blog/personal website address):

![](https://godbmw.com/blog-static/images/%E5%BC%80%E6%BA%90%E9%A1%B9%E7%9B%AE/Theme-BMW%E4%B8 %AD%E6%96%87%E6%96%87%E6%A1%A3/10.png)