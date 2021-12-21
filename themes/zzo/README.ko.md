[comment]: <> (# Zzo theme for Hugo)

[comment]: <> ([English]&#40;https://github.com/zzossig/hugo-theme-zzo/blob/master/README.md&#41; | )

[comment]: <> (한국어)

[comment]: <> (🔥🔥🔥)

[comment]: <> (zzo theme을 업데이트한 후 `config.toml` 파일에서 page 변수를 삭제해주세요)

[comment]: <> (```diff)

[comment]: <> ([outputs])

[comment]: <> (  <del>page = ["HTML", "SearchIndex"]</del>)

[comment]: <> (```)

[comment]: <> (검색 관련 인덱스 생성위치를 변경했습니다)

[comment]: <> (🔥🔥🔥)

[comment]: <> (클릭해 주셔서 감사합니다. Zzo theme은 많은 기능을 지원하고있고 있습니다. 기술 블로그를 운영하기에 최적화 되어있습니다!&#40;적어도 제생각엔...&#41;)

[comment]: <> (Zzo theme을 이용할 시 가장 매력적인 포인트 한가지는, 한글로 저와 소통할 수 있다는 점? 입니다. )

[comment]: <> (## Documentation)

[comment]: <> (영문버전 도큐먼트)

[comment]: <> ([https://zzo-docs.vercel.app/zzo]&#40;https://zzo-docs.vercel.app/zzo&#41;)

[comment]: <> (## Table of contents)

[comment]: <> (* [기능]&#40;#features&#41;)

[comment]: <> (* [최소 휴고 버전]&#40;#minimum-hugo-version&#41;)

[comment]: <> (* [설치]&#40;#installation&#41;)

[comment]: <> (* [업데이트]&#40;#updating&#41;)

[comment]: <> (* [예제 사이트 돌리기]&#40;#run-example-site&#41;)

[comment]: <> (* [설정]&#40;#configuration&#41;)

[comment]: <> (* [갤러리]&#40;#gallery&#41;)

[comment]: <> (* [컨택 페이지]&#40;#contact-page&#41;)

[comment]: <> (* [토크 페이지]&#40;#talks-page&#41;)

[comment]: <> (* [쇼케이스 페이지]&#40;#showcase-page&#41;)

[comment]: <> (* [다국어]&#40;#multi-language&#41;)

[comment]: <> (* [저자]&#40;#author&#41;)

[comment]: <> (* [Favicon]&#40;#favicon&#41;)

[comment]: <> (* [커스터마이징]&#40;#customizing&#41;)

[comment]: <> (* [외부 라이브러리 사용]&#40;#external-library&#41;)

[comment]: <> (* [Shortcodes]&#40;#shortcodes&#41;)

[comment]: <> (## Features)

[comment]: <> (* 다양한 스킨 지원&#40;dark, light, solarized, ...&#41;)

[comment]: <> (* 모바일 메뉴)

[comment]: <> (* 최신 HTML5, CSS 기술 이용)

[comment]: <> (* 심플한 블로그)

[comment]: <> (* 검색 엔진 최적화 &#40;SEO&#41;)

[comment]: <> (* 다국어 지원 &#40;i18n&#41;)

[comment]: <> (* 반응형 디자인)

[comment]: <> (* RSS feed 지원)

[comment]: <> (* 검색 &#40;지원 예정&#41;)

[comment]: <> (* 갤러리 지원)

[comment]: <> (* 코드 하이라이트)

[comment]: <> (* 토크 페이지)

[comment]: <> (* 쇼케이스 페이지)

[comment]: <> (## Minimum Hugo version)

[comment]: <> (최소 요구 Hugo 버전은 0.60.0 입니다.)

[comment]: <> (## Installation)

[comment]: <> (우선 설정 파일을 만드셔야 합니다. 설정파일이 없거나 설정값이 잘못 될 경우, 실행이 안되실 수 있습니다.)

[comment]: <> ([설정]&#40;#configuration&#41; 링크를 참조하여 설정파일을 만들어주세요.)

[comment]: <> (설정 파일을 다 만드셨으면, theme 폴더에 zzo 폴더를 만들고, 그곳에 이 레포지토리를 다운로드 하신 파일을 복사 붙여넣기 하시면 됩니다.)

[comment]: <> (이렇게 파일을 복사 붙여넣기 하시면, 나중에 제가 여러가지 버그나 이슈를 업데이트 했을 때, 님이 만드신 블로그를 최신 Zzo theme으로)

[comment]: <> (업데이트 하고 싶으시면 해당 Zzo theme을 지우고 다시 다운로드 한 다음, 복붙하시면 되겠습니다.)

[comment]: <> (```bash)

[comment]: <> ($ git clone https://github.com/zzossig/hugo-theme-zzo.git themes/zzo)

[comment]: <> (```)

[comment]: <> (깃헙을 이용하여 블로그를 관리하신다면, 섭모듈을 사용하여 Zzo theme을 쉽게 최신버전으로 유지하실 수 있습니다.)

[comment]: <> (루트 폴더에서 다음 코드를 입력해주시면 submodule로써 Zzo theme이 설치됩니다:)

[comment]: <> (```bash)

[comment]: <> (git submodule add https://github.com/zzossig/hugo-theme-zzo.git themes/zzo)

[comment]: <> (```)

[comment]: <> (## Updating)

[comment]: <> (From the root of your site:)

[comment]: <> (```bash)

[comment]: <> (git submodule update --remote --merge)

[comment]: <> (```)

[comment]: <> (## Run example site)

[comment]: <> (From the root of themes/zzo/exampleSite:)

[comment]: <> (```bash)

[comment]: <> (hugo server --themesDir ../..)

[comment]: <> (```)

[comment]: <> (## Configuration)

[comment]: <> (0. 저같은 경우, 디렉토리 하나를 만들고 그곳에 다음과같이 사이트를 만듭니다.)

[comment]: <> (```bash)

[comment]: <> (hugo new site .)

[comment]: <> (```)

[comment]: <> (1. 0번 단계에서 만드신 디렉토리로 들어가주세요.)

[comment]: <> (config.toml 파일이 보이신다면, 과감하게 지워주세요. 아래 단계들은 제가 사용하는 config 파일들입니다.)

[comment]: <> (모두 그냥 복사, 붙여넣기 해서 파일을 만드시면 되는데, 귀찮으신 분들은 exampleSite 폴더에 있는 config 폴더를)

[comment]: <> (루트 디렉토리에 그냥 복사 붙여넣기 하셔도 됩니다.)
 
[comment]: <> (아래는 설정 파일 구조구요. _default폴더의 _&#40;언더스코어&#41; 뺴먹지 마세요!)

[comment]: <> (```bash)

[comment]: <> (root)

[comment]: <> (├── config)

[comment]: <> (│   ├── _default)

[comment]: <> (│   │   ├── config.toml)

[comment]: <> (│   │   ├── languages.toml)

[comment]: <> (│   │   ├── menus.en.toml)

[comment]: <> (│   │   ├── params.toml)

[comment]: <> (```)

[comment]: <> (2. config.toml)

[comment]: <> (```bash)

[comment]: <> (baseURL = "http://example.org/" # The URL of your site.)

[comment]: <> (title = "Hugo Zzo Theme" # Title of your site)

[comment]: <> (theme = "zzo" # Name of Zzo theme folder in `themes/`.)

[comment]: <> (defaultContentLanguage = "en" # Default language to use &#40;if you setup multilingual&#41;)

[comment]: <> (defaultContentLanguageInSubdir = true # baseURL/en/, baseURL/kr/ ...)

[comment]: <> (hasCJKLanguage = true # Set `true` for Chinese/Japanese/Korean languages.)

[comment]: <> (summaryLength = 70 # The length of a post description on a list page.)

[comment]: <> (buildFuture = true # if true, we can use future date for talks page)

[comment]: <> (copyright = "©{year}, All Rights Reserved" # copyright symbol: $copy; current year: {year})

[comment]: <> (timeout = 10000)

[comment]: <> (enableEmoji = true)

[comment]: <> (paginate = 13 # Number of items per page in paginated lists.)

[comment]: <> (rssLimit = 100)

[comment]: <> (enableGitInfo = false # When true, the modified date will appear on a summary and single page. Since GitHub info needs to be fetched, this feature will slow down to build depending on a page number you have)

[comment]: <> (googleAnalytics = "")

[comment]: <> ([markup])

[comment]: <> (  [markup.goldmark])

[comment]: <> (    [markup.goldmark.renderer])

[comment]: <> (      hardWraps = true)

[comment]: <> (      unsafe = true)

[comment]: <> (      xHTML = true)

[comment]: <> (  [markup.highlight])

[comment]: <> (    codeFences = true)

[comment]: <> (    lineNos = true)

[comment]: <> (    lineNumbersInTable = true)

[comment]: <> (    noClasses = false)

[comment]: <> (  [markup.tableOfContents])

[comment]: <> (    endLevel = 3)

[comment]: <> (    ordered = false)

[comment]: <> (    startLevel = 2)

[comment]: <> ([outputs])

[comment]: <> (  home = ["HTML", "RSS", "JSON"])

[comment]: <> ([taxonomies])

[comment]: <> (  category = "categories")

[comment]: <> (  tag = "tags")

[comment]: <> (  series = "series")

[comment]: <> (```)

[comment]: <> (3. languages.toml)

[comment]: <> (```bash)

[comment]: <> ([en])

[comment]: <> (  title = "Hugo Zzo Theme")

[comment]: <> (  languageName = "English")

[comment]: <> (  weight = 1)

[comment]: <> ([ko])

[comment]: <> (  title = "Hugo Zzo Theme")

[comment]: <> (  languageName = "한국어")

[comment]: <> (  weight = 2)

[comment]: <> (```)

[comment]: <> (4. menus.en.toml)

[comment]: <> (You shoud make your own menu.)

[comment]: <> (```bash)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "about")

[comment]: <> (  name = "about")

[comment]: <> (  url = "about")

[comment]: <> (  weight = 1)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "archive")

[comment]: <> (  name = "archive")

[comment]: <> (  url = "archive")

[comment]: <> (  weight = 2)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "gallery")

[comment]: <> (  name = "gallery")

[comment]: <> (  url = "gallery")

[comment]: <> (  weight = 3)
    
[comment]: <> ([[main]])

[comment]: <> (  parent = "gallery")

[comment]: <> (  name = "cartoon")

[comment]: <> (  url = "gallery/cartoon")

[comment]: <> ([[main]])

[comment]: <> (  parent = "gallery")

[comment]: <> (  name = "photo")

[comment]: <> (  url = "gallery/photo")

[comment]: <> ([[main]])

[comment]: <> (  identifier = "posts")

[comment]: <> (  name = "posts")

[comment]: <> (  url = "posts")

[comment]: <> (  weight = 4)
    
[comment]: <> ([[main]])

[comment]: <> (  identifier = "notes")

[comment]: <> (  name = "notes")

[comment]: <> (  url = "notes")

[comment]: <> (  weight = 5)

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (5. params.toml)

[comment]: <> (```bash)

[comment]: <> (logoText = "Zzo" # Logo text that appears in the site navigation bar.)

[comment]: <> (logoType = "short" # long, short -> short: squre shape includes logo text, long: rectangle shape not includes logo text)

[comment]: <> (logo = true # Logo that appears in the site navigation bar.)

[comment]: <> (description = "The Zzo theme for Hugo example site." # for SEO)

[comment]: <> (custom_css = [] # custom_css = ["scss/custom.scss"] and then make file at root/assets/scss/custom.scss)

[comment]: <> (custom_js = [] # custom_js = ["js/custom.js"] and then make file at root/assets/js/custom.js)

[comment]: <> (useFaviconGenerator = false # https://www.favicon-generator.org/)

[comment]: <> (languagedir = "ltr" # ltr / rtl)

[comment]: <> (themeOptions = ["dark", "light", "hacker", "solarized", "kimbie"] # select options for site color theme)

[comment]: <> (notAllowedTypesInHome = ["contact", "talks", "about", "showcase"] # not allowed page types in home page. type can be set in front matter or default to folder name.)

[comment]: <> (notAllowedTypesInHomeSidebar = ["about", "archive", "showcase"] # not allowed page types in home page sidebar&#40;recent post titles&#41;.)

[comment]: <> (notAllowedTypesInArchive = ["about", "talks", "showcase"] # not allowed page types in archive page)

[comment]: <> (notAllowedTypesInHomeFeed = ["about", "archive", "contact", "talks", "showcase", "publication", "presentation", "resume", "gallery"])

[comment]: <> (enablePinnedPosts = true # show pinned posts first in the main view)

[comment]: <> (viewportSize = "normal" # widest, wider, wide, normal, narrow)

[comment]: <> (enableUiAnimation = true)

[comment]: <> (hideSingleContentsWhenJSDisabled = false)

[comment]: <> (minItemsToShowInTagCloud = 1 # Minimum items to show in tag cloud)

[comment]: <> (# appbar)

[comment]: <> (enableAppbarSearchIcon = false)

[comment]: <> (enableAppbarLangIcon = false)

[comment]: <> (# header)

[comment]: <> (homeHeaderType = "text" # text, img, slide, typewriter)

[comment]: <> (hideHomeHeaderWhenMobile = false)

[comment]: <> (# menu)

[comment]: <> (showMobileMenuTerms = ["tags", "categories", "series"])

[comment]: <> (# navbar)

[comment]: <> (enableThemeChange = true # site color theme)

[comment]: <> (# search)

[comment]: <> (enableSearch = true # site search with fuse)

[comment]: <> (enableSearchHighlight = true # when true, search keyword will be highlighted)

[comment]: <> (searchContent = true # include content to search index)

[comment]: <> (searchDistance = 100 # fuse option: distance)

[comment]: <> (searchThreshold = 0.4 # 0.0: exact match, 1.0: any match)

[comment]: <> (# body)

[comment]: <> (enableBreadcrumb = true # breadcrumb for list, single page)

[comment]: <> (enableGoToTop = true # scroll to top)

[comment]: <> (enableWhoami = true # at the end of single page)

[comment]: <> (summaryShape = "classic" # card, classic, compact)

[comment]: <> (archiveGroupByDate = "2006" # "2006-01": group by month, "2006": group by year)

[comment]: <> (archivePaginate = 13 # items per page)

[comment]: <> (paginateWindow = 1 # setting it to 1 gives 7 buttons, 2 gives 9, etc. If set 1: [1 ... 4 5 6 ... 356] [1 2 3 4 5 ... 356] etc)

[comment]: <> (talksPaginate = 8 # items per page)

[comment]: <> (talksGroupByDate = "2006" # "2006-01": group by month, "2006": group by year)

[comment]: <> (# whoami: usage - home page sidebar, single page bottom of post. all values can be empty)

[comment]: <> (myname = "zzossig")

[comment]: <> (email = "zzossig@gmail.com")

[comment]: <> (whoami = "Web Developer")

[comment]: <> (bioImageUrl = "" # image url like "http//..." or "images/anyfoldername/mybioimage.jpg" If not set, we find a avatar image in root/static/images/whoami/avatar.&#40;png|jpg|svg&#41;)

[comment]: <> (useGravatar = false # we use this option highest priority)

[comment]: <> (location = "Seoul, Korea")

[comment]: <> (organization = "Hugo")

[comment]: <> (link = "https://github.com/zzossig/hugo-theme-zzo")

[comment]: <> (# sidebar)

[comment]: <> (enableBio = true # in home page sidebar)

[comment]: <> (enableBioImage = true # in home page sidebar)

[comment]: <> (enableSidebar = true # Set to false to create the full width of the content.)

[comment]: <> (enableSidebarTags = true # if you want to use tags.)

[comment]: <> (enableSidebarSeries = true)

[comment]: <> (enableSidebarCategories = true)

[comment]: <> (enableHomeSidebarTitles = true)

[comment]: <> (enableListSidebarTitles = true)

[comment]: <> (enableToc = true # single page table of contents, you can replace this param to toc&#40;toc = true&#41;)

[comment]: <> (hideToc = false # Hide or Show toc)

[comment]: <> (tocPosition = "inner" # inner, outer)

[comment]: <> (tocFolding = false)

[comment]: <> (enableTocSwitch = true # single page table of contents visibility switch)

[comment]: <> (itemsPerCategory = 5 # maximum number of posts shown in the sidebar.)

[comment]: <> (sidebarPosition = "right" # bio, profile component layout position)

[comment]: <> (tocLevels = ["h2", "h3", "h4"] # minimum h2, maximum h4 in your article)

[comment]: <> (enableSidebarPostsByOrder = false # another lists in the sidebar)

[comment]: <> (# footer)

[comment]: <> (showPoweredBy = true # show footer text: Powered by Hugo and Zzo theme)

[comment]: <> (showFeedLinks = true # RSS Feed )

[comment]: <> (showSocialLinks = true # email, facebook, twitter ...)

[comment]: <> (enableLangChange = true # show button at bottom left of footer.)

[comment]: <> (# service)

[comment]: <> (googleTagManager = "" # GTM-XXXXXX)

[comment]: <> (baiduAnalytics = "" # alternative of google analytics)

[comment]: <> (enableBusuanzi = false # if set true, total page view, total unique visitors show up in the footer.)

[comment]: <> (busuanziSiteUV = true # unique visitors &#40;total number of visitors&#41;)

[comment]: <> (busuanziSitePV = true # site total page view count)

[comment]: <> (busuanziPagePV = true # post view count)

[comment]: <> (# rss)

[comment]: <> (updatePeriod = "" # Possible values: 'hourly', 'daily', 'weekly', 'monthly', or 'yearly'.)

[comment]: <> (updateFrequency = "")

[comment]: <> (fullContents = false)

[comment]: <> (# comment)

[comment]: <> (enableComment = true)

[comment]: <> (disqus_shortname = "" )

[comment]: <> (commento = false)

[comment]: <> ([gitment]          # Gitment is a comment system based on GitHub issues. see https://github.com/imsun/gitment)

[comment]: <> (  owner = ""              # Your GitHub ID)

[comment]: <> (  repo = ""               # The repo to store comments)

[comment]: <> (  clientId = ""           # Your client ID)

[comment]: <> (  clientSecret = ""       # Your client secret)

[comment]: <> ([utterances]       # https://utteranc.es/)

[comment]: <> (  owner = ""              # Your GitHub ID)

[comment]: <> (  repo = ""               # The repo to store comments)

[comment]: <> (  message = ""      # Optional)

[comment]: <> (  link = ""         # Optional)

[comment]: <> ([gitalk]           # Gitalk is a comment system based on GitHub issues. see https://github.com/gitalk/gitalk)

[comment]: <> (  owner = ""              # Your GitHub ID)

[comment]: <> (  repo = ""               # The repo to store comments)

[comment]: <> (  clientId = ""           # Your client ID)

[comment]: <> (  clientSecret = ""       # Your client secret)

[comment]: <> (# Valine.)

[comment]: <> (# You can get your appid and appkey from https://leancloud.cn)

[comment]: <> (# more info please open https://valine.js.org)

[comment]: <> ([valine])

[comment]: <> (  enable = false)

[comment]: <> (  appId = '你的appId')

[comment]: <> (  appKey = '你的appKey')

[comment]: <> (  notify = false  # mail notifier , https://github.com/xCss/Valine/wiki)

[comment]: <> (  verify = false # Verification code)

[comment]: <> (  avatar = 'mm' )

[comment]: <> (  placeholder = '说点什么吧...')

[comment]: <> (  visitor = false)

[comment]: <> ([changyan])

[comment]: <> (  changyanAppid = ""        # Changyan app id             # 畅言)

[comment]: <> (  changyanAppkey = ""       # Changyan app key)

[comment]: <> ([livere])

[comment]: <> (  livereUID = ""            # LiveRe UID                  # 来必力)

[comment]: <> (# Isso: https://posativ.org/isso/)

[comment]: <> ([isso])

[comment]: <> (  enable = false)

[comment]: <> (  scriptSrc = "" # "https://isso.example.com/js/embed.min.js")

[comment]: <> (  dataAttrs = "" # "data-isso='https://isso.example.com' data-isso-require-author='true'")

[comment]: <> ([socialOptions] # if set, social icons will show up.)

[comment]: <> (  email = "mailto:your@email.com")

[comment]: <> (  phone = "")

[comment]: <> (  facebook = "http://example.org/")

[comment]: <> (  twitter = "http://example.org/")

[comment]: <> (  github = "https://github.com/zzossig/hugo-theme-zzo")

[comment]: <> (  stack-overflow = "")

[comment]: <> (  instagram = "")

[comment]: <> (  google-plus = "")

[comment]: <> (  youtube = "")

[comment]: <> (  medium = "")

[comment]: <> (  tumblr = "")

[comment]: <> (  linkedin = "")

[comment]: <> (  pinterest = "")

[comment]: <> (  stack-exchange = "")

[comment]: <> (  telegram = "")

[comment]: <> (  steam = "")

[comment]: <> (  weibo = "")

[comment]: <> (  douban = "")

[comment]: <> (  csdn = "")

[comment]: <> (  gitlab = "")

[comment]: <> (  mastodon = "")

[comment]: <> (  jianshu = "")

[comment]: <> (  zhihu = "")

[comment]: <> (  signal = "")

[comment]: <> (  whatsapp = "")

[comment]: <> (  matrix = "")

[comment]: <> (  xmpp = "")

[comment]: <> (  dev-to = "")

[comment]: <> (  gitea = "")

[comment]: <> (  google-scholar = "")

[comment]: <> (  twitch = "")

[comment]: <> ([donationOptions])

[comment]: <> (  enable = false # if set, the donation button will show up on the single page.)

[comment]: <> (  alipay = "" # Alipay QR Code image &#40;example path: images/donation/alipay-qrcode.png&#41; and put your file at root/static/images/donation/)

[comment]: <> (  wechat = "" # Wechat pay QR Code image &#40;example path: same as above&#41;)

[comment]: <> (  paypal = "" # Paypal URL)

[comment]: <> (  patreon = "" # Patreon URL)

[comment]: <> (  bitcoin = "" # example path: images/donation/bitcoin-code-image.png)

[comment]: <> ([copyrightOptions])

[comment]: <> (  enableCopyrightLink = false # if set, you can add copyright link)

[comment]: <> (  copyrightLink = "")

[comment]: <> (  copyrightLinkImage = "")

[comment]: <> (  copyrightLinkText = "")

[comment]: <> (# possible share name: "facebook","twitter", "reddit", "linkedin", "tumblr", "weibo", "douban", "line", "whatsapp", "telegram")

[comment]: <> ([[share]])

[comment]: <> (  name = "facebook")

[comment]: <> (  username = "")

[comment]: <> ([[share]])

[comment]: <> (  name = "twitter")

[comment]: <> ([[footerLinks]])

[comment]: <> (  name = "")

[comment]: <> (  link = "")

[comment]: <> ([[footerLinks]])

[comment]: <> (  name = "")

[comment]: <> (  link = "")

[comment]: <> (```)

[comment]: <> (## Gallery)

[comment]: <> (갤러리는 두가지 모두가 존재해요. 하나씩 올리거나 한번에 올리거나.)

[comment]: <> (```bash)

[comment]: <> (content/gallery/anygalleryname/index.md)

[comment]: <> (---)

[comment]: <> (title: "{{ replace .Name "-" " " | title }}")

[comment]: <> (date: {{ .Date }})

[comment]: <> (description: )

[comment]: <> (type: gallery)

[comment]: <> (mode: one-by-one # at-once or one-by-one)

[comment]: <> (tags:)

[comment]: <> (-)

[comment]: <> (series:)

[comment]: <> (-)

[comment]: <> (categories:)

[comment]: <> (-)

[comment]: <> (images: # when mode is one-by-one, images front-matter variable works)

[comment]: <> (  - image: image1.jpg # image path: static/gallery/anygalleryname/image1.jpg)

[comment]: <> (    caption: caption1)

[comment]: <> (  - image: image2.jpg # image path: static/gallery/anygalleryname/image2.jpg)

[comment]: <> (    caption: caption2)

[comment]: <> (    ...)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (갤러리를 만드시려면 우선 type을 갤러리로 하셔야 하구요, mode를 one-by-one으로 하시면 images에 이미지를 위와 같이 하나씩 입력해주셔야 해요. )

[comment]: <> (그럼 이미지가 위에 적힌 순서대로 나타날거에요. mode를 at-once로 하시면, static 폴더에 있는 이미지를 전부 불러올거에요. 예를들어 위의 코드에서 mode를 at-once로 했다면,)

[comment]: <> (static/gallery/anygalleryname 폴더에 있는 이미지를 전부 읽어 갤러리 페이지에 나타날 거에요.)

[comment]: <> (1. Make a gallery folder under the content folder)

[comment]: <> (```bash)

[comment]: <> (root)

[comment]: <> (├── content)

[comment]: <> (│   ├── gallery)

[comment]: <> (```)

[comment]: <> (2. Make a sub folder under the gallery folder)

[comment]: <> (```bash)

[comment]: <> (root)

[comment]: <> (├── content)

[comment]: <> (│   ├── gallery)

[comment]: <> (│   │   ├── anygalleryname)

[comment]: <> (```)

[comment]: <> (3. Make a index.md file under the sub folder using this command)

[comment]: <> (```bash)

[comment]: <> (hugo new --kind gallery gallery/anygalleryname/index.md)

[comment]: <> (```)

[comment]: <> (4. Put your images in static folder)

[comment]: <> (```bash)

[comment]: <> (root)

[comment]: <> (├── static)

[comment]: <> (│   ├── gallery)

[comment]: <> (│   │   ├── anygalleryname)

[comment]: <> (│   │   │   ├── ...your images here)

[comment]: <> (```)

[comment]: <> (## Contact Page)

[comment]: <> (현재 이용 가능한 서비스: [formspree]. 다른 서비스를 이용하고 싶으시면 새 이슈를 만들어주세요. 서비스 파라미터를 빈값으로 설정하면 마크다운으로 해당 페이지를 채울 수 있습니다.)

[comment]: <> (1. 파일을 다음 경로에 만들어줍니다. root/content/contact/index.md)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title: "Contact")

[comment]: <> (date: 2019-12-17T23:58:33+09:00)

[comment]: <> (description: Contact page)

[comment]: <> (type: contact)

[comment]: <> (service: formspree)

[comment]: <> (formId: "your@email.com")

[comment]: <> (---)

[comment]: <> (This is contact page.)

[comment]: <> (```)

[comment]: <> (2. 컨택트 메뉴를 다음 경로에 추가해줍니다. root/config/_default/menus.en.toml.)

[comment]: <> (```toml)

[comment]: <> (...)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "contact")

[comment]: <> (  name = "contact")

[comment]: <> (  url = "contact")

[comment]: <> (  weight = 6)

[comment]: <> (```)

[comment]: <> (## Talks Page)

[comment]: <> (Talks 페이지는 아카이브 페이지와 유사한 UI의 페이지입니다. 비디오, 피티 등등의 링크를 모아서 보여주는 용도로 씁니다. Talks 페이지를 추가하려면 아래의 순서대로 따라해주세요.)

[comment]: <> (1. 파일을 root/content/talks/_index.md. 경로에 다음과 같이 만듭니다.)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title: "Talks")

[comment]: <> (date: 2019-12-30T11:14:14+09:00)

[comment]: <> (description: Talks Page)

[comment]: <> (titleWrap: wrap # wrap, nowrap)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (2. 또 다른 파일을 만들어 줍니다. 이곳에 내용을 넣어주세요. )

[comment]: <> (root/content/talks/myLinks.md)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title: "My Awesome links")

[comment]: <> (date: 2019-12-31T00:04:50+09:00)

[comment]: <> (publishDate: 2019-12-31)

[comment]: <> (description:)

[comment]: <> (tags:)

[comment]: <> (-)

[comment]: <> (series:)

[comment]: <> (-)

[comment]: <> (categories:)

[comment]: <> (-)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (3. 마지막으로 메뉴만 다음 과 같이 만들어 주면 됩니다. )

[comment]: <> (root/config/_default/menus.en.toml file)

[comment]: <> (```toml)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "talks")

[comment]: <> (  name = "talks")

[comment]: <> (  url = "talks")

[comment]: <> (  weight = 6)

[comment]: <> (```)

[comment]: <> (4. 추가적으로, date를 미래의 날짜를 쓰고 싶으시면 다음 단계를 따라서 해주세요.)

[comment]: <> (    - 다음 경로의 설정파일&#40;root/config/_default/config.toml&#41;에서 `buildFuture`를 추가해주세요.)

[comment]: <> (    ```toml)

[comment]: <> (    ...)

[comment]: <> (    buildFuture = true)

[comment]: <> (    ...)

[comment]: <> (    ```)

[comment]: <> (    - talks폴더의 마크다운 파일에 `publishDate`를 추가해주세요. root/content/talks/myLinks.md)

[comment]: <> (    ```yaml)

[comment]: <> (    ---)

[comment]: <> (    title:)

[comment]: <> (    date:)

[comment]: <> (    publishDate: 2020-02-20)

[comment]: <> (    ...)

[comment]: <> (    ---)

[comment]: <> (    ...)

[comment]: <> (    ```)

[comment]: <> (## Showcase Page)

[comment]: <> (Showcase 페이지는 프로젝트를 전시하는 페이지 입니다. 페이지를 만드시려면 아래 단계를 진행해주세요.)

[comment]: <> (1. 다음 경로에 파일을 만듭니다. `root/content/showcase/_index.md`.)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title: "Showcase overview" # For SEO)

[comment]: <> (date: 2020-01-19T15:43:38+09:00)

[comment]: <> (description: My portfolio, repos, works overview page # For SEO)

[comment]: <> (enableBio: true # Set to false if you want to hide the bio component.)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (2. 다음 경로에 카테고리 폴더와 파일을 만듭니다. `root/content/showcase/hugo/_index.md` file. &#40;저의 경우, hugo가 카테고리 폴더입니다.&#41;)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title: "Hugo" # section name)

[comment]: <> (date: 2020-01-19T21:04:11+09:00)

[comment]: <> (description: Hugo theme collection # For SEO)

[comment]: <> (category: theme # meta info appeared on a card bottom side. category in category)

[comment]: <> (enableBio: true)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (3. 프로젝트당 한개의 md파일을 만들어 주세요.)

[comment]: <> (`root/content/showcase/hugo/my-awesome-project.md`)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title: "My Awesome Project" # apperared on a card component)

[comment]: <> (date: 2020-01-19T21:13:42+09:00)

[comment]: <> (description: Hello world! This is my awesome project! # apperared on a card component)

[comment]: <> (weight: 1 # card ordering)

[comment]: <> (link: https://github.com/zzossig/hugo-theme-zzo)

[comment]: <> (repo: https://github.com/zzossig/hugo-theme-zzo)

[comment]: <> (pinned: true # appreared on a overview page.)

[comment]: <> (thumb: feature3/css3.png # relative path in static/images)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (4. 마지막으로, 메뉴를 등록해주세요.)

[comment]: <> (`root/config/_default/menus.en.toml`)

[comment]: <> (```toml)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "showcase")

[comment]: <> (  name = "Showcase")

[comment]: <> (  url = "showcase")

[comment]: <> (  weight = 7)

[comment]: <> (```)

[comment]: <> (## Multi Language)

[comment]: <> (Zzo theme의 기본 언어는 영어입니다. 한국어로 바꾸시려면 다음과 같이 해주세요.)

[comment]: <> (1. 우선 메뉴파일을 만듭니다.)

[comment]: <> (```bash )

[comment]: <> (root)

[comment]: <> (├── config)

[comment]: <> (│   ├── _default)

[comment]: <> (│   │   ├── ...)

[comment]: <> (│   │   ├── menus.ko.toml)

[comment]: <> (```)

[comment]: <> (```bash)

[comment]: <> (config/_default/menus.ko.toml)

[comment]: <> ([[main]])

[comment]: <> (  identifier = "about")

[comment]: <> (  name = "about")

[comment]: <> (  url = "/about/")

[comment]: <> (  weight = 1)

[comment]: <> ([[main]])

[comment]: <> (    identifier = "archive")

[comment]: <> (    name = "archive")

[comment]: <> (    url = "/archive/")

[comment]: <> (    weight = 2)

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (2. content 폴더에 마크다운 파일을 작성하실 때, 확장자 앞에 ko를 붙여주세요!)

[comment]: <> (```bash)

[comment]: <> (hugo new about/index.ko.md)

[comment]: <> (hugo new posts/markdown-syntax.ko.md)

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (3. i18n 파일을 만듭니다.)

[comment]: <> (```bash)

[comment]: <> (i18n/ko.toml)

[comment]: <> ([search-placeholder])

[comment]: <> (other = "검색...")

[comment]: <> ([summary-dateformat])

[comment]: <> (other = "2006년 01월 02일")

[comment]: <> ([tags])

[comment]: <> (other = "태그")

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (4. 설정 파일에 기본언어 항목 값을 변경해줍니다.)

[comment]: <> (```bash)

[comment]: <> (defaultContentLanguage = "ko")

[comment]: <> (defaultContentLanguageInSubdir = true)

[comment]: <> (hasCJKLanguage = true)

[comment]: <> (```)

[comment]: <> (## Customizing)

[comment]: <> (기본적으로 theme 폴더안에 있는 내용은 안건드시는게 좋지만, 건드신다면 나중에 theme을 업데이트 하는게 복잡해 질 수도 있습니다. 현재 상태로 별로 업데이트가 필요 없다고 느끼신다면 theme에 있는 파일을 마음대로 고치셔도 됩니다. 그게 아니라면 아래에 있는 방식으로 커스터마이징 하시기를 추천드립니다.)

[comment]: <> (추가로, custom css나 custom js를 아래의 방식대로 이용하시면, 페이지 로드 속도가 약간 더 느려지는 것을)

[comment]: <> (발견했습니다.)

[comment]: <> (### custom css)

[comment]: <> (1. config 폴더의 params.toml 파일에 아래와같이 커스텀 스타일 파일을 명시해주세요.)

[comment]: <> (```bash)

[comment]: <> (config/_default/params.toml)

[comment]: <> (...)

[comment]: <> (custom_css = ["css/custom.css", "scss/custom.scss", ...])

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (2. 위 설정파일에 명시한 대로 실제 파일을 만들어 주세요.)

[comment]: <> (```bash)

[comment]: <> (assets/scss/custom.scss)

[comment]: <> (assets/css/custom.css)

[comment]: <> (```)

[comment]: <> (3. 만약 특정 색상을 변경하고 싶으시면, 위에 만든 커스텀 스타일 파일에 해당 부분의 스타일을 오버라이드 해줘야 합니다. 예를들어 backdrop 색상을 변경하고자 하시면, 다음과 같이 해주셔야 합니다.)

[comment]: <> (```css)

[comment]: <> (assets/scss/custom.scss or assets/css/custom.css)

[comment]: <> (...)

[comment]: <> (#body {)

[comment]: <> (  background-color: red !important;)

[comment]: <> (})

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (### custom js)

[comment]: <> (1. config 폴더의 params.toml 파일에 아래와같이 커스텀 파일을 명시해주세요.)

[comment]: <> (```bash)

[comment]: <> (config/_default/params.toml)

[comment]: <> (...)

[comment]: <> (custom_js = ["js/custom.js", ...])

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (2. 실제 파일을 생성해 주시구요.)

[comment]: <> (```bash)

[comment]: <> (assets/js/custom.js)

[comment]: <> (```)

[comment]: <> (### custom syntax highlighting)

[comment]: <> (1. root/data 폴더에 skin.toml파일을 만들어주세요. theme_dark_chroma, theme_light_chroma, ... 파라미터의 항목의 값을 원하시는 코드 하이라이트 테마값으로 변경해주세요. [이 링크]&#40;https://xyproto.github.io/splash/docs/all.html&#41;를 참조해서 값을 변경하시면 됩니다. 만약 theme_[xxxx]_chroma 값에 - 나 _ 같은 특수문자가 있다면 지워주세요.)

[comment]: <> (예를들어, solarized-dark256 값을 입력하시려면, 다음과 같이 해주세요.)

[comment]: <> (```)

[comment]: <> (root/data/skin.toml)

[comment]: <> (theme_dark_chroma = "solarizeddark256")

[comment]: <> (```)

[comment]: <> (2. 특정 색상을 변경하고 싶으시다면, [[custom-css]&#40;#custom-css&#41;]에서 만든 파일에 chroma class를 오버라이드 해야합니다. 잘 모르겠으면 문의주세요!)

[comment]: <> (```)

[comment]: <> (root/assets/scss/custom.scss)

[comment]: <> (.chroma {)

[comment]: <> (  background-color: #123456 !important;)

[comment]: <> (})

[comment]: <> (```)

[comment]: <> (### custom header)

[comment]: <> (홈페이지에서 헤더 부분에 4가지 종류의 헤더를 입힐 수 있습니다. 슬라이더, 이미지, 텍스트, 그리고 아무것도 입력 안하시면 빈공간이 됩니다.)

[comment]: <> (1. config/_default/params.toml 설정파일에 homeHeaderType 값을 변경해주세요. 가능한 값은 slide, img, text, typewriter입니다.)

[comment]: <> (2. root/content/_index.md에 _index.md 파일을 만들어주세요 그리고 아래 내용을 복붙해주세요.)

[comment]: <> (3. 변수의 이름만으로 의미가 전달된다고 생각합니다. 값을 하나씩 변경해보면서 원하시는 대로 커스터마이징 해주세요.)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (header:)

[comment]: <> (  - type: text)

[comment]: <> (    height: 200)

[comment]: <> (    paddingX: 50)

[comment]: <> (    paddingY: 0)

[comment]: <> (    align: center)

[comment]: <> (    title:)

[comment]: <> (      - HUGO)

[comment]: <> (    subtitle:)

[comment]: <> (      - The world’s fastest framework for building websites)

[comment]: <> (    titleColor: # #123456, red)

[comment]: <> (    titleShadow: false)

[comment]: <> (    titleFontSize: 44)

[comment]: <> (    subtitleColor: # #123456, red)

[comment]: <> (    subtitleCursive: false)

[comment]: <> (    subtitleFontSize: 16)

[comment]: <> (    spaceBetweenTitleSubtitle: 20)
  
[comment]: <> (  - type: img)

[comment]: <> (    imageSrc: images/header/background.jpg # your image file path: root/static/images/header/background.jpg)

[comment]: <> (    imageSize: cover # auto|length|cover|contain|initial|inherit)

[comment]: <> (    imageRepeat: no-repeat # repeat|repeat-x|repeat-y|no-repeat|initial|inherit)

[comment]: <> (    imagePosition: center # x% y%| xpos ypos| left top| center bottom| ...)

[comment]: <> (    height: 235)

[comment]: <> (    paddingX: 50)

[comment]: <> (    paddingY: 0)

[comment]: <> (    align: center)

[comment]: <> (    title:)

[comment]: <> (      -)

[comment]: <> (    subtitle:)

[comment]: <> (      -)

[comment]: <> (    titleColor:)

[comment]: <> (    titleShadow: false)

[comment]: <> (    titleFontSize: 44)

[comment]: <> (    subtitleColor:)

[comment]: <> (    subtitleCursive: false)

[comment]: <> (    subtitleFontSize: 16)

[comment]: <> (    spaceBetweenTitleSubtitle: 20)

[comment]: <> (  - type: slide)

[comment]: <> (    height: 235)

[comment]: <> (    options:)

[comment]: <> (        startSlide: 0)

[comment]: <> (        auto: 5000 # auto slide delay 5000ms&#40;5sec&#41;)

[comment]: <> (        draggable: true # slide draggable)

[comment]: <> (        autoRestart: true # restart after drag finished)

[comment]: <> (        continuous: true # last to first)

[comment]: <> (        disableScroll: true)

[comment]: <> (        stopPropagation: true)

[comment]: <> (    slide:)

[comment]: <> (      - paddingX: 50)

[comment]: <> (        paddingY: 0)

[comment]: <> (        align: left)

[comment]: <> (        imageSrc: images/header/background.jpg)

[comment]: <> (        imageSize: cover)

[comment]: <> (        imageRepeat: no-repeat)

[comment]: <> (        imagePosition: center)

[comment]: <> (        title:)

[comment]: <> (          - header title1)

[comment]: <> (        subtitle:)

[comment]: <> (          - header subtitle1)

[comment]: <> (        titleFontSize: 44)

[comment]: <> (        subtitleFontSize: 16)

[comment]: <> (        spaceBetweenTitleSubtitle: 20)

[comment]: <> (      - paddingX: 50)

[comment]: <> (        paddingY: 0)

[comment]: <> (        align: center)

[comment]: <> (        imageSrc: images/header/background.jpg)

[comment]: <> (        imageSize: cover)

[comment]: <> (        imageRepeat: no-repeat)

[comment]: <> (        imagePosition: center)

[comment]: <> (        title:)

[comment]: <> (          - header title2)

[comment]: <> (        subtitle:)

[comment]: <> (          - header subtitle2)

[comment]: <> (        titleFontSize: 44)

[comment]: <> (        subtitleFontSize: 16)

[comment]: <> (        spaceBetweenTitleSubtitle: 20)

[comment]: <> (      - paddingX: 50)

[comment]: <> (        paddingY: 0)

[comment]: <> (        align: right)

[comment]: <> (        imageSrc: images/header/background.jpg)

[comment]: <> (        imageSize: cover)

[comment]: <> (        imageRepeat: no-repeat)

[comment]: <> (        imagePosition: center)

[comment]: <> (        title:)

[comment]: <> (          - header title3)

[comment]: <> (        subtitle:)

[comment]: <> (          - header subtitle3)

[comment]: <> (        titleFontSize: 44)

[comment]: <> (        subtitleFontSize: 16)

[comment]: <> (        spaceBetweenTitleSubtitle: 20)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (### custom grid)

[comment]: <> (1. 폴더에 grid.toml 파일을 만들어주세요. &#40;data/grid.toml&#41;)

[comment]: <> (2. themes/zzo/data/grid.toml 파일에 있는 내용을 위에서 만든 파일에 복붙해주세요.)

[comment]: <> (3. 원하시는 대로 값을 변경해주세요.)

[comment]: <> (4. 변경 후, 휴고를 재시작 해주세요.)

[comment]: <> (```toml)

[comment]: <> (data/grid.toml example)

[comment]: <> (grid_max_width = "960")

[comment]: <> (grid_max_unit = "px" #  "px", "\"%\""  Using% is limited to using full width.)

[comment]: <> (grid_main_main_width = "5")

[comment]: <> (grid_main_main_unit = "fr" # "fr", "px")

[comment]: <> (grid_main_side_width = "2")

[comment]: <> (grid_main_side_unit = "fr" # "fr", "px")

[comment]: <> (grid_column_gap_width = "32")

[comment]: <> (grid_column_gap_unit = "px" # "px")

[comment]: <> (grid_navbar_height = "50px" # "px")

[comment]: <> (grid_row_gap = "0")

[comment]: <> (```)

[comment]: <> (### custom font)

[comment]: <> (1. 커스텀 css 파일을 만들어주세요.)

[comment]: <> (```bash)

[comment]: <> (config/_default/params.toml)

[comment]: <> (...)

[comment]: <> (custom_css = ["css/font.css"])

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> (2. font.css 파일에, font-face를 아래와 같이 만들어주세요.)

[comment]: <> (```css)

[comment]: <> (@font-face {)

[comment]: <> (    font-family: 'Montserrat';)

[comment]: <> (    src: url&#40;'../fonts/montserrat-black.woff2'&#41; format&#40;'woff2'&#41;,)

[comment]: <> (         url&#40;'../fonts/montserrat-black.woff'&#41; format&#40;'woff'&#41;;)

[comment]: <> (    font-weight: 900;)

[comment]: <> (    font-style: normal;)

[comment]: <> (})

[comment]: <> (@font-face {)

[comment]: <> (    font-family: 'Merriweather';)

[comment]: <> (    src: url&#40;'../fonts/merriweather-regular.woff2'&#41; format&#40;'woff2'&#41;,)

[comment]: <> (         url&#40;'../fonts/merriweather-regular.woff'&#41; format&#40;'woff'&#41;;)

[comment]: <> (    font-weight: 400;)

[comment]: <> (    font-style: normal;)

[comment]: <> (})

[comment]: <> (```)

[comment]: <> (3. root/static/fonts/myfont.xxx 폰트 파일을 static 폴더에 넣어주세요. &#40;If your url in step2 is &#40;'../fonts/myfont.xxx'&#41;&#41;.)

[comment]: <> (4. root/data/font.toml 에 font.toml 파일을 만들어주세요. 그리고 아래와 같이 내용을 입력해주세요.)

[comment]: <> (```toml)

[comment]: <> (title_font = "\"Montserrat\", sans-serif")

[comment]: <> (content_font = "\"Merriweather\", serif")

[comment]: <> (```)

[comment]: <> (5. 다른 방식)

[comment]: <> (root/layouts/partials/head/custom-head.html 경로에 파일을 만드시고 폰트를 그곳에서 로드해주세요.)

[comment]: <> (```html)

[comment]: <> (<link href="https://fonts.googleapis.com/css?family=Noto+Sans+KR:400,700&display=swap&subset=korean" rel="stylesheet">)

[comment]: <> (```)

[comment]: <> (### custom copyright)

[comment]: <> (footer의 저작권 텍스트에 링크를 넣고 싶으면 다음과 같이 커스터마이징 하면 됩니다.)

[comment]: <> (1. 설정 파일인 config.toml 에서 copyright 파라미터 값을 설정해주세요.)

[comment]: <> (```toml)

[comment]: <> (...)

[comment]: <> (copyright = This is my {} copyright text)

[comment]: <> (...)

[comment]: <> (```)

[comment]: <> ({} 로 쓰여진 부분이 링크가 들어갈 부분입니다.)

[comment]: <> (2. 설정 파일인 params.toml 에서 copyrightOptions 파라미터 값을 설정해주세요.)

[comment]: <> (```toml)

[comment]: <> (...)

[comment]: <> ([copyrightOptions])

[comment]: <> (  enableCopyrightLink = false)

[comment]: <> (  copyrightLink = "https://...")

[comment]: <> (  copyrightLinkImage = "https://...")

[comment]: <> (  copyrightLinkText = "copyright link text")

[comment]: <> (```)

[comment]: <> (### custom favicon)

[comment]: <> (root/static 폴더에 파비콘을 넣어서 테마의 favicon을 overriding 하시면 됩니다.)

[comment]: <> (## Author)

[comment]: <> (포스트의 저자에 대한 정보를 front matter를 통해서 명시할 수 있습니다.)

[comment]: <> (```yaml)

[comment]: <> (---)

[comment]: <> (title:)

[comment]: <> (...)

[comment]: <> (author: # author name)

[comment]: <> (authorEmoji: 🤖 # emoji for subtitle, summary meta data)

[comment]: <> (authorImage: "/images/whoami/avatar.jpg" # image path in the static folder)

[comment]: <> (authorImageUrl: "" # your image url. We use `authorImageUrl` first. If not set, we use `authorImage`.)

[comment]: <> (authorDesc: # author description)

[comment]: <> (socialOptions: # override params.toml file socialOptions)

[comment]: <> (  email: "")

[comment]: <> (  facebook: "")

[comment]: <> (  ...)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (## Favicon)

[comment]: <> (`favicon.ico`라는 파일을 루트 디렉토리의 static 폴더에 넣어주세요. 파일 이름과 확장자가 정확히 `favicon.ico`여야 합니다.)

[comment]: <> (### Using favicon-genarator)

[comment]: <> (모바일 환경을 고려하신다면 [favicon-generator]&#40;https://www.favicon-generator.org/&#41; 사이트에서 파비콘을 만들어주세요.)

[comment]: <> (- 위의 사이트에서 파비콘을 만들어주세요.)

[comment]: <> (- `root/static/favicon`경로에 폴더를 만들어주세요.)

[comment]: <> (- 해당 폴더에 파비콘을 풀어주세요.)

[comment]: <> (- params.toml 파일에 `useFaviconGenerator`의 값을 `true`로 바꿔주세요.)

[comment]: <> (## External Library)

[comment]: <> (현재 지원하는 외부 라이브러리는 Katex, MathJax, Mermaid, Flowchart.js, chart.js, viz-graph, wavedrom, js-sequence-diagram 입니다. front-matter에 값을 넣어주시면 해당 라이브러리가 로드됩니다.)

[comment]: <> (```bash)

[comment]: <> (---)

[comment]: <> (title: "{{ replace .Name "-" " " | title }}")

[comment]: <> (date: {{ .Date }})

[comment]: <> (...)

[comment]: <> (libraries:)

[comment]: <> (- katex )

[comment]: <> (- mathjax)

[comment]: <> (- chart)

[comment]: <> (- flowchartjs)

[comment]: <> (- msc)

[comment]: <> (- katex)

[comment]: <> (- mermaid)

[comment]: <> (- viz)

[comment]: <> (- wavedrom)

[comment]: <> (---)

[comment]: <> (```)

[comment]: <> (## Shortcodes)

[comment]: <> (### alert)

[comment]: <> (```bash)

[comment]: <> ({{< alert theme="warning" >}} # warning, success, info, danger)

[comment]: <> (**this** is a text)

[comment]: <> ({{< /alert >}})

[comment]: <> (```)

[comment]: <> (### expand)

[comment]: <> (```bash)

[comment]: <> ({{< expand "Expand me" >}}Some Markdown Contents{{< /expand >}})

[comment]: <> (```)

[comment]: <> (### img)

[comment]: <> (```bash)

[comment]: <> (// path: static/images/whoami/avatar.jpg)

[comment]: <> ({{< img src="/images/whoami/avatar.jpg" title="Image4" caption="Image description" alt="image alt" width="50px" height="50px">}})

[comment]: <> (```)

[comment]: <> (### notice)

[comment]: <> (```bash)

[comment]: <> ({{< notice success >}} # success, info, warning, error)

[comment]: <> (success)

[comment]: <> ({{< /notice >}})

[comment]: <> (```)

[comment]: <> (### color)

[comment]: <> (```bash)

[comment]: <> ({{< color "#0000ff" >}}*text*{{< /color >}})

[comment]: <> (```)

[comment]: <> (### box)

[comment]: <> (```bash)

[comment]: <> ({{< box >}})

[comment]: <> (Some contents)

[comment]: <> ({{< /box >}})

[comment]: <> (```)

[comment]: <> (### boxmd)

[comment]: <> (```bash)

[comment]: <> ({{< boxmd >}})

[comment]: <> (Some markdown contents)

[comment]: <> ({{< /boxmd >}})

[comment]: <> (```)

[comment]: <> (### code / codes => 코드를 여러 버전으로 제공할 때 쓰세요. 들여쓰기 잘못하면 이상하게 나와요.)

[comment]: <> (`````)

[comment]: <> ({{< codes java javascript >}})

[comment]: <> (  {{< code >}})

[comment]: <> (  ```java)

[comment]: <> (  System.out.println&#40;'Hello World!'&#41;;)

[comment]: <> (  ```)

[comment]: <> (  {{< /code >}})

[comment]: <> (  {{< code >}})

[comment]: <> (  ```javascript)

[comment]: <> (  console.log&#40;'Hello World!'&#41;;)

[comment]: <> (  ```)

[comment]: <> (  {{< /code >}})

[comment]: <> ({{< /codes >}})

[comment]: <> (`````)

[comment]: <> (### tab / tabs => 여러 버전의 뷰를 제공할 때 쓰세요)

[comment]: <> (탭을 만들 때, 각 탭마다 안의 내용에 따라 고유 아이디를 부여하기 때문에, Tab 안에 있는 내용이 서로 달라야합니다.)

[comment]: <> (`````)

[comment]: <> ({{< tabs Windows MacOS Ubuntu >}})

[comment]: <> (  {{< tab >}})

[comment]: <> (  ### Windows section)

[comment]: <> (  ```javascript)

[comment]: <> (  console.log&#40;'Hello World!'&#41;;)

[comment]: <> (  ```)

[comment]: <> (  {{< /tab >}})

[comment]: <> (  {{< tab >}})

[comment]: <> (  ### MacOS section)

[comment]: <> (  Hello world!)

[comment]: <> (  {{< /tab >}})

[comment]: <> (  {{< tab >}})

[comment]: <> (  ### Ubuntu section)

[comment]: <> (  Great!)

[comment]: <> (  {{< /tab >}})

[comment]: <> ({{< /tabs >}})

[comment]: <> (`````)
