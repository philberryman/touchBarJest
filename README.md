# touchBarJest

![GitHub Logo](https://github.com/philberryman/touchBarJest/images/touchBar.png)
Format: ![Alt Text](url)

A super simple evening project to get my (or your) Jest test results showing on your MacBook Pro TouchBar.

Most of the heavy lifting for this project was done by My Touchbar My Rules (https://github.com/Toxblh/MTMR). I have just created a few lines of code to get Jest output on the touchbar.

## How to use

Clone this repo (I have used my User directory)

Download and install My Touchbar My Rule (MTMR) from https://github.com/Toxblh/MTMR

Open Preferences of MTMR (from the MTMR icon on the OS X top menu bar)

Add the following to the config file: the config file is an array so put it before the closing ]
You will need to edit the "filePath" to wherever these files are on your machine.

```,
    {
    "type": "appleScriptTitledButton",
        "source": {
      "filePath": "/Users/philberryman/touchBarJest/touchBarJest.scpt",
    },
    "align": "right",
    "bordered": false,
    "refreshInterval": 2,
  }
```

Run Jest so that it outputs a json file everytime it runs.
For example edit package.json  scripts (the example below is for a Create React App project)

```"test": "react-scripts test --verbose --outputFile='/users/philberryman/touchBarJest/testOutput.json' --json --watchAll",```

Run the node script that converts the output into a string for the touchBar

```node convertTestOutput.js``` from touchBarJest directory

convertTestOutput.js can be edited very easily to create whatever string you want to show on the touchbar. It currently shows something along the lines of :

Test:5:10

where there are 10 tests and 5 are passing.

All very simple. Not very clever. But it works...

Let me know if you use it / find it useful / have any issues. 

Twitter: @philberryman

ps. No this project doesn't have any of its own tests. Oh the irony. 

