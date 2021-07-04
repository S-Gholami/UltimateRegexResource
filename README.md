# UltimateRegexResource

📝 A compilation of Regex syntax and resources for the Google DSC Regex Event

[![Discuss On Discord][discord]][discord-url]
[![Contributors][contributors-shield]][contributors-url]
[![Issues][issues]][issues-url]

<!-- 📄 TODO: Add after presentation [**Watch a recording of the Regex presentation here!**](https://www.youtube.com/watch?v=mqhDMv6nIVI) -->

Regex, or [regular expressions](https://en.wikipedia.org/wiki/Regular_expression), are patterns used to match strings. Regex is commonly used for searching/filtering strings for information, input validation, and web scraping. "Real world" examples include everything from validating email addresses to formatting class names in a grades app.

Regex is incredibly powerful, but due to its seemingly unintelligible nature it's also often intimidating to learn and difficult to remember.

![image](https://user-images.githubusercontent.com/47064842/124194070-ee6c7680-da95-11eb-8f9a-0a2d3f7c4f33.png)

For that reason, I've compiled a selection of the most helpful and commonly used regex syntax and some regex resources for your use below!

<!-- The [Docs](https://github.com/GoldinGuy/UltimateRegexResource/tree/main/docs) folder of this repo contains a simple profile/resume static site built on HTML5 and [TailwindCSS](https://v1.tailwindcss.com/) to help learn about [Github pages](https://pages.github.com/). You can clone the repository and test it out yourself, or visit [this link](https://goldinguy.github.io/UltimateRegexResource/) to see a live demo. For more info look at the [README](https://github.com/GoldinGuy/UltimateRegexResource/blob/main/docs/README.md) for the `/docs` directory. -->

- This repo contains a powerpoint presentation that can be viewed online [here](https://docs.google.com/presentation/d/1cTKU9GCAiubAG2wcFk9VdNwo5mn0ulzB7bJz9GICAWY/edit?usp=sharing).

- Anywhere used below, `char` is shorthand for `character` (letter, digit or symbol), and `exp` is shorthand for a `regular expression`.

## 📄 Table of Contents

TBD

<!-- - [Installing Git](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/set-up-git)
- [Gitting Existing Projects](#-gitting-existing-projects)
- [Gitting Started - Setting Up a New Repo](#-gitting-started---setting-up-a-new-repo)
- [The Nitty Gitty - Examine History & State](#-the-nitty-gitty---examine-history--state)
- [Branching Out - Grow, Mark & Tweak History](#-branching-out---grow-mark--tweak-history)
- [Git Gud - Dealing With Merge Conflicts](#-git-gud---dealing-with-merge-conflicts)
- [Git More - Pushing, Pulling, & Remote Origin](#-git-more---pushing-pulling--remote-origin)
- [Gitting Complicated - The Danger Zone](#-gitting-complicated---the-danger-zone)
- [Git Resources](#-more-git-resources)
- [Contributing](#contributing) -->

### ✒️ "Balderdash" Basics (of Regex)

- Regular expressions start and end with "slash" characters `/`.
- Patterns return the first [case-sensitive](https://en.wikipedia.org/wiki/Case_sensitivity) match they find by default.

Therefore: given the sample string `I scream, you scream, we all scream for ice cream`, `/scream/` matches the first instance of "scream."

This behavior can be modified with [flags](#-flags).

### 🖋️ "Flapdoodle" Flags

| Syntax | Flag          | Behavior                                                       | Example  |
| ------ | ------------- | -------------------------------------------------------------- | -------- |
| `g`    | _global_      | Returns additional matches                                     | `/foo/g` |
| `i`    | _insensitive_ | Allows case-insensitive matches                                | `/foo/i` |
| `x`    | _verbose_     | Ignore whitespace & allow comments                             | `/foo/x` |
| `u`    | _unicode_     | Expressions are treated as Unicode (UTF-16)                    | `/foo/u` |
| `s`    | _singleline_  | Treats entire string as one line (allows `.` to match newline) | `/foo/s` |
| `m`    | _multiline_   | Start & end anchors now trigger on each line                   | `/foo/m` |
| `n`    | _nth match_   | Matches text returned by _nth_ group                           | `/foo/m` |

Regex includes several flags that are appended to the end of the expression to change behavior. Using the string `I scream, you scream, we all SCREAM for ice cream`, the updated regex `/scream/gi` will now return `scream scream SCREAM`.

### ✏️ "Gibberish" Characters

| Syntax | Character            | Matches                                                                                         | Example String | Example Expression | Example Match |
| ------ | -------------------- | ----------------------------------------------------------------------------------------------- | -------------- | ------------------ | ------------- |
| `.`    | _any_                | Literally any char _(except line break)_                                                        | `a-c1-3`       | `a.c`              | `a-c`         |
| `\w`   | _word_               | ASCII char _(Or Unicode char in Python & C#)_                                                   | `a-c1-3`       | `\w-\w`            | `a-c`         |
| `\d`   | _digit_              | Digit 0-9 _(Or Unicode digit in Python & C#)_                                                   | `a-c1-3`       | `\d-\d`            | `1-3`         |
| `\s`   | _whitespace_         | Space, tab, vertical tab, newline, carriage return _(Or Unicode seperator in Python, C#, & JS)_ | `a b`          | `a\sb`             | `a b`         |
| `\W`   | **NOT** _word_       | Anything `\w` does not match                                                                    | `a-c1-3`       | `\W-\W`            | `1-3`         |
| `\D`   | **NOT** _digit_      | Anything `\d` does not match                                                                    | `a-c1-3`       | `\D-\D`            | `a-c`         |
| `\S`   | **NOT** _whitespace_ | Anything `\s` does not match                                                                    | `a-c1-3`       | `\S-\S`            | `a-c`         |

### 🖋️ "Bafflegab" Special Characters

| Syntax | Special Character | Matches                                             | Example String | Example Expression | Example Match |
| ------ | ----------------- | --------------------------------------------------- | -------------- | ------------------ | ------------- |
| `\`    | _escape_          | The following when preceding them: `[{()}].*+?$^/\` | `)$[]*{`       | `\[\]`             | `[]`          |

| Syntax | Substitute        | Behavior                      |
| ------ | ----------------- | ----------------------------- |
| `\n`   | _newline_         | Insert a newline char         |
| `\t`   | _tab_             | Insert a tab char             |
| `\r`   | _carriage return_ | Insert a carriage return char |
| `\f`   | _form-feed_       | Insert a form feed char       |

### 🖌️ "Rigmarole" Ranges

| Syntax     | Range                 | Matches                                     | Example String     | Example Expression | Example Match   |
| ---------- | --------------------- | ------------------------------------------- | ------------------ | ------------------ | --------------- |
| `[pog]`    | _word list_           | Either `p`, `o`, or `g`                     | `awesomePOSSUM123` | `[awesum]+`        | `awes`          |
| `[^pog]`   | **NOT** _word list_   | Any char except `p`, `o`, or `g`            | `awesomePOSSUM123` | `[^awesum]+`       | `o`             |
| `[a-z]`    | _word range_          | Any char between `a` and `z`, inclusive     | `awesomePOSSUM123` | `[a-z]+`           | `awesome`       |
| `[^a-z]`   | **NOT** _word range_  | Any char not between `a` and `z`, inclusive | `awesomePOSSUM123` | `[^a-z]+`          | `123`           |
| `[0-9]`    | _digit range_         | Any char between `0` and `9`, inclusive     | `awesomePOSSUM123` | `[0-9]+`           | `123`           |
| `[^0-9]`   | **NOT** _digit range_ | Any char not between `0` and `9`, inclusive | `awesomePOSSUM123` | `[^0-9]+`          | `awesomePOSSUM` |
| `[a-zA-Z]` | _word range_          | Any char not between `a` and `z`, inclusive | `awesomePOSSUM123` | `[a-zA-Z]+`        | `awesomePOSSUM` |
| `[a-zA-Z]` | _word range_          | Any char not between `a` and `z`, inclusive | `awesomePOSSUM123` | `[a-zA-Z]+`        | `awesomePOSSUM` |

### 🖌️ "Jargon" Quantifiers

| Syntax  | Quantifier | Matches                                     | Example String | Example Expression | Example Match |
| ------- | ---------- | ------------------------------------------- | -------------- | ------------------ | ------------- |
| `?`     | _optional_ | 0 or 1 of the preceding expression          | `ccc`          | `c?`               | `c`           |
| `{X}`   | _X_        | X of the preceding expression               | `ccc`          | `c{2}`             | `cc`          |
| `{X,}`  | _X+_       | X or more of the preceding expression       | `ccc`          | `c{2,}`            | `ccc`         |
| `{X,Y}` | _range_    | Between X and Y of the preceding expression | `ccc`          | `c{1,3}`           | `ccc`         |

Beyond standard quantifiers, there are a few additional modifiers: _greedy_, _lazy_, and _possessive_.

| Syntax | Quantifier      | Matches                                                                                      | Example String | Example Expression | Example Match |
| ------ | --------------- | -------------------------------------------------------------------------------------------- | -------------- | ------------------ | ------------- |
| `*`    | _0+ greedy_     | 0 or more of the preceding expression, using as many chars as possible                       | `abccc`        | `c*`               | `ccc`         |
| `+`    | _1+ greedy_     | 1 or more of the preceding expression, using as many chars as possible                       | `abccc`        | `c+`               | `ccc`         |
| `*?`   | _0+ lazy_       | 0 or more of the preceding expression, using as few chars as possible                        | `abccc`        | `c*?`              | `c`           |
| `+?`   | _1+ lazy_       | 1 or more of the preceding expression, using as few chars as possible                        | `abccc`        | `c+?`              | `c`           |
| `*+`   | _0+ possessive_ | 0 or more of the preceding expression, using as many chars as possible, without backtracking | `abccc`        | `c*+`              | `ccc`         |
| `++`   | _1+ possessive_ | 1 or more of the preceding expression, using as many chars as possible, without backtracking | `abccc`        | `c++`              | `ccc`         |

Put simply, greedy quantifiers match as much as possible, lazy as little as possible, and possessive as much as possible without backtracking.

What this means in practice is that possessive quantifiers will always return either the same match as greedy quantifiers, or if backtracking is required they will return no match. Therefore, posessive quantifiers should be used when you know backtracking is _not_ necessary, allowing increased performance.

### 🖊️ Gobbledygook Groups

| Syntax     | Group       | Matches                                                         | Example String     | Example Expression      | Example Match      |
| ---------- | ----------- | --------------------------------------------------------------- | ------------------ | ----------------------- | ------------------ |
| `\|`       | _alternate_ | Either the preceding or following expression                    | `truly rural`      | `truly\|rural`          | `truly`            |
| `(...)`    | _isolate_   | Everything enclosed; treats as separate capture group           | `truly rural`      | `truly (rural)`         | `truly`, `rural`   |
| `(?:...)`  | _include_   | Everything enclosed; enables using quantifiers on part of regex | `truly ruralrural` | `truly (?:rural)+`      | `truly ruralrural` |
| `(?\|...)` | _combine_   | Everything enclosed; treats all matches as same group           | `truly rural`      | `(?\|(rural)\|(truly))` | `truly`            |
| `(?>...)`  | _atomic_    | Longest possible string without backtracking                    | `truly rural`      | `(?>rur)`               | ` rur`             |
| `(?#...)`  | _comment_   | Everything enclosed; treats as comment and ignores              | `truly #rural`     | `truly (?#rural)`       | `truly`            |

### 🖍️ "Malarkey" Anchors

| Syntax | Anchor                  | Matches                                             | Example String       | Example Expression | Example Match |
| ------ | ----------------------- | --------------------------------------------------- | -------------------- | ------------------ | ------------- |
| `^`    | _start_                 | Start of string                                     | `she sells seasells` | `^\w+`             | `she`         |
| `$`    | _end_                   | End of string                                       | `she sells seasells` | `\w+$`             | `seashells`   |
| `\b`   | _word boundary_         | Between a character matched and not matched by `\w` | `she sells seasells` | `s\b`              | `s`           |
| `\B`   | **NOT** _word boundary_ | Between two characters matched by `\w`              | `she sells seasells` | `\w+$`             | `seashells`   |

There are additional anchors available that are unaffected by multiline mode [m](#-flags).

| Syntax | Anchor         | Matches                                            | Example String    | Example Expression | Example Match |
| ------ | -------------- | -------------------------------------------------- | ----------------- | ------------------ | ------------- |
| `\A`   | _multi-start_  | Start of string                                    | `she sees cheese` | `\A\w+`            | `she`         |
| `\Z`   | _multi-end_    | End of string                                      | `she sees cheese` | `\w+\Z`            | `cheese`      |
| `\Z`   | _absolute end_ | Absolute end of string, ignoring trailing newlines | `she sees cheese` | `\w+\Z`            | `cheese`      |

<!--
### ✒️ "Mumbo Jumbo" Regex Resources

- [Git Docs](https://git-scm.com/doc), for those who want to dive deep into the documentation
- [Git Handbook](https://guides.github.com/introduction/git-handbook/), for those who want a quick overview
- [Visual Git CheatSheet](https://ndpsoftware.com/git-cheatsheet.html), for those who are visual learners
- [Official Printable PDF CheatSheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf), for those who need the physcial copy
- [Visualize Git Under the Hood](https://git-school.github.io/visualizing-git/), allows you to explore exactly how commands affect repo structure
- [Stanford GitMagic](http://www-cs-students.stanford.edu/~blynn/gitmagic/), a plain but detailed quide to git
- [GitReady](http://gitready.com/), lets you learn git one commit at a time
- [Git From the Bottom Up](https://jwiegley.github.io/git-from-the-bottom-up/), gives you a better understanding of the powerful system
- [Git, the Simple Guide](https://rogerdudler.github.io/git-guide/), as stated, with no deep knowledge required
- [Git Explained (Not just commands)](https://towardsdatascience.com/git-help-all-2d0bb0c31483), a brief guide including more than commands
- [Git-It](https://github.com/jlord/git-it-electron#what-to-install), an app that teaches you git via challenges in the terminal
- [Interactive Way to Learn Git Branching](https://learngitbranching.js.org/), for an enjoyable way to tackle an important concept
- [Git Markdown Emoji](https://github.com/ikatyang/emoji-cheat-sheet), to spice up your Git repos
- [Article on Writing Good Commit Messages](https://chris.beams.io/posts/git-commit/), which pretty much everyone could stand to improve ;)
- [Github Student Developer Pack](https://education.github.com/pack), seriously, if you're a student you should have this
- [Intro to Git Rebase](https://dev.to/maxwell_dev/the-git-rebase-introduction-i-wish-id-had), a great explanation of a powerful command -->

### "Codswallop" Contributing

1. Fork UltimateRegexResource [here](https://github.com/GoldinGuy/UltimateRegexResource/fork)
2. Create a branch with your improvements (`git checkout -b improvement/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin improvement/fooBar`)
5. Create a new Pull Request

#### Meta

Created by [@GoldinGuy](https://github.com/GoldinGuy) for the FAU Google DSC Regex Event.

<!-- Markdown link & img dfn's -->

[discord-url]: https://discord.gg/gKYSMeJ
[discord]: https://img.shields.io/discord/689176425701703810
[issues]: https://img.shields.io/github/issues/GoldinGuy/UltimateRegexResource
[issues-url]: https://github.com/GoldinGuy/UltimateRegexResource/issues
[contributors-shield]: https://img.shields.io/github/contributors/GoldinGuy/UltimateRegexResource.svg?style=flat-square
[contributors-url]: https://github.com/GoldinGuy/UltimateRegexResource/graphs/contributors
