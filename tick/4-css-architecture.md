#### Project Css Architecture

```
project
|
└───sass
|   │
│   └───abstracts : (include static value such function, mixin, variable)
│   │    _<file-name>.scss
│   │    _<file-name>.scss
|   │
│   └───base : (include animation, base, typography, utills)
│   |    _<file-name>.scss
│   |    _<file-name>.scss
|   |
│   └───components : (include individual component in project)
│       _<file-name>.scss
│       _<file-name>.scss
|   │
│   └───layout : (include layout in prpoject)
│   |    _<file-name>.scss
│   |    _<file-name>.scss
|   │
│   └───pages : (include page style)
│   |    _<file-name>.scss
│   |    _<file-name>.scss
|   │
│   └───main.scss (main import file)
│
│
└───folder2
│
└───folder3

```
