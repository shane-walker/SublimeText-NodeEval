NodeEval Sublime Text 2 Package
=============================

### Use the NodeJS binary to evaluate a document or selection(s) and print the results

Screenshots
--------
![Preview](https://github.com/mediaupstream/SublimeText-NodeEval/raw/master/screenshots/NodeEval_output1.png "Output to a new File") ![Preview](https://github.com/mediaupstream/SublimeText-NodeEval/raw/master/screenshots/NodeEval_output2.png "Output to Console, etc...")  


Install
-------
Installation via the [Package Control](http://wbond.net/sublime_packages/package_control) (Search for `NodeEval`)
  
To install manually clone this project into your `Sublime Text 2\Packages` folder:

*OSX*

    git clone git://github.com/mediaupstream/SublimeText-NodeEval.git ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/NodeEval

*Windows*

    git clone git://github.com/mediaupstream/SublimeText-NodeEval.git "%APPDATA%\Sublime Text 2\Packages\NodeEval"


Usage
-----
After installation you will have:  

* Context Menu and `Tools` Menu items:
  - `NodeEval` - evaluate the current selection(s) / document with `node`
  - `NodeEval - Continuous (Toggle)` - Continually evaluate the current selection(s) / document with `node`. This command is a toggle for the current document / selection(s) only. You can set the refresh rate in the Sublime settings (see below)
* Default keyboard shortcuts:  
  - `ctrl+n,e`  
* Package Settings: `Preferences > Package Settings > NodeEval`  
  ```javascript
    {
      // The absolute path to your nodejs executable
      // e.g. "/usr/local/bin/node" or "C:\\bin\\node.exe"
      "node_command": "/usr/local/bin/node",

      // How to output the results, options include:
      // - new [default] "send output to a new file"
      // - console       "send output to a new Panel (Console) view"
      // - replace       "overwrite the current file/selection with the output"
      // - clipboard     "there is no output, output copied to clipboard"
      "output": "new",

      // if output type is "new" the output is overwritten, set to false to append the output
      "overwrite_output": true,

      // if set to true the output is copied to the clipboard
      // if `output` is set to "clipboard" this value is ignored
      "copy_to_clipboard": false,

      // refresh rate threshold for "continuous" mode (in milliseconds)
      "threshold": 200
    }
  ```

The commands work on a selection, multiple selections or if nothing is selected the whole document. Your script will be eval'd through the nodejs repl.  

Your results may contain `undefined` in places, for example if your last line is an expression who's return value is `undefined` you will see that in the output...  

----

**Why not just use the NodeJS ST2 plugin, or the nodejsLauncher plugin ?**   
the `NodeJS` plugin is awesome, but it's also really bloated. also I don't think that the `nodejsLauncher` actually works, I looked at the sourcecode and was like wtf.



Author & Contributors
----------------------
[Derek Anderson](http://twitter.com/derekanderson)


License
-------
MIT License