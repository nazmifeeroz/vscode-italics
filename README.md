# VsCode Settings for italic fonts

```javascript
"editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "scope": [
          //following will be in italics (=Pacifico)
          "comment",
          "entity.name.type.class", //class names
          "keyword", //import, export, return…
          //"support.class.builtin.js", //String, Number, Boolean…, this, super
          "storage.modifier", //static keyword
          "storage.type.class.js", //class keyword
          "storage.type.function.js", // function keyword
          "storage.type.js", // Variable declarations
          "keyword.control.import.js", // Imports
          "keyword.control.from.js", // From-Keyword
          //"entity.name.type.js", // new … Expression
          "keyword.control.flow.js", // await
          "keyword.control.conditional.js", // if
          "keyword.control.loop.js", // for
          "keyword.operator.new.js", // new
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": [
          //following will be excluded from italics (My theme (Monokai dark) has some defaults I don't want to be in italics)
          "invalid",
          "keyword.operator",
          "constant.numeric.css",
          "keyword.other.unit.px.css",
          "constant.numeric.decimal.js",
          "constant.numeric.json",
          "entity.name.type.class.js"
        ],
        "settings": {
          "fontStyle": ""
        }
      }
    ]
  }
```

> Source: https://github.com/kosimst/Firicico

# To make the code brighter

>The reason it was happening is that apple changed their default font rendering process and the Skia graphics library that Chromium based apps use was effected. Apparently it has been fixed and you will just have to wait until the changes trickle down to VSCode.

```shell
defaults write com.microsoft.VSCode CGFontRenderingFontSmoothingDisabled 0
defaults write com.microsoft.VSCode.helper CGFontRenderingFontSmoothingDisabled 0
defaults write com.microsoft.VSCode.helper.EH CGFontRenderingFontSmoothingDisabled 0
defaults write com.microsoft.VSCode.helper.NP CGFontRenderingFontSmoothingDisabled 0
defaults write com.microsoft.VSCode AppleFontSmoothing -int 1
defaults write com.microsoft.VSCode.helper AppleFontSmoothing -int 1
defaults write com.microsoft.VSCode.helper.EH AppleFontSmoothing -int 1
defaults write com.microsoft.VSCode.helper.NP AppleFontSmoothing -int 1
```
