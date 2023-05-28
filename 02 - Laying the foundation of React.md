## Intro :

- Currently we are working with modern JS and our apps are also made using it.
- But suppose our user is using a browser from 90's, our website might not load properly as Modern JS was not invented at that time and thus, bowser won't understand our website's code.
- There is a replacement code available for the modern JS functionalities which is compatible with older versions of browser. So when we write "browserlists" - (mentions which versions of browser our code must support) in our package.json, our code gets converted to that code.
- So "Babel" which is a JS library/package, is the one who converts the code using the "browserlists" provided.
- So we don't have to write polyfills.

### NOTE : 'git init' is a command which makes your folder/repo compatible with git. Also generates '.gitignore' file. You can also use all features of git in your repo now such as branching, push, pull, etc.
