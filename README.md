## Synopsis

This is a [Sublime Text 2/3](http://www.sublimetext.com) plugin.

**Add "$" symbol before PHP variable name**

AutoPHPDollar automatically inserts a "$" character before variables.
Type the variable name without a "$", and this plugin will add it.

## Installation

Go to your `Packages` subdirectory under ST's data directory (replace <ST version>
with "2" or "3" depending on what version of ST you are using):

* Windows: `%APPDATA%\Sublime Text <ST version>`
* OS X: `~/Library/Application Support/Sublime Text <ST version>/Packages`
* Linux: `~/.config/sublime-text-<ST version>`
* Portable Installation: `Sublime Text <ST version>/Data`

Then clone this repository:

    git clone git://github.com/graarh/sublime-AutoPHPDollar.git

That's it!

## Options

Several options are available to customize the plugin behavior.

### Add rules for detecting variables

You can add custom rules, that improves variables detection.
The rule contains regular expression to find a variable without
dollar character, and the replacement of found text.

``` js
"rules": [
    {
        "search":  "(?<![\\$\\w\\d\\>])(\\w[\\w\\d]*)(?=\\s*=)",
        "replace": "$\\1"
    }
]
```

### Add keywords or buildin function names to ignore names list

You can add words, that should be ignored by plugin. It can be buildin function name, like array_walk, or PHP keyword. In PHP, you can use variable name like $private, but you dont want
to add the $ sign to each "private" you typed. So, add this name to this list.
``` js
"ignore names": [
    "private",
    "public",
    "protected"
]
```

### Add keywords, that never followed by variable

You can add words, that never has variable name after it. For example, this is the function keyword.
You can not use constructions like function $myfuncname($args) in PHP, so you do not want to add $ sign to the function name. Or constant name.

``` js
"ignore after": [
    "class",
    "function",
    "const"
]
```

### Roadmap and TODO:
- improve variables detection
