Contribution Guidelines
---
1. Clone this repo
2. All the snippets are located inside of the `/snippets/` folder. 
  
    - `javascript.json` for Javascript related snippets
    - `snippets.code-snippets` for all other snippets

3. How to modify:

    a. For new entries, copy the snippet syntax below (or an existing one for simplicity)

   b. For existing entries, simply search the list `Ctrl+F`, and modify as you like.

4. Submit a [pull request](https://github.com/dons20/UIKit-VSCode/pulls) to the repository.

#### Snippet Template

```json
"snippet-uk-PREFIX": {
    "prefix": "uk-PREFIX",
    "body": [ 	
        "HTML HERE",
        "Multiple Lines Seperated with double quotes and a comma",
            "\t Lines that start with the tab character, should also be visually tabbed for better readability",
        "Set tab locations with $0 - any number you specify, with $0 automatically being the last tab location",
        "Last Line does not have a comma"
    ],
    "description": "Enter your description here"
}, 
```
If applicable, please update the list of commands in `README.md` with your changes if you added or renamed a snippet.

Snippet Modification Tips
---

Getting the hang of modifying snippets can be tricky at first, so here are some useful tips to get you started.

#### Official Documentation

First, [check out Microsoft's offical documentation on snippets](https://code.visualstudio.com/Docs/customization/userdefinedsnippets)

#### Keeping snippets well formatted

HTML code needs to have proper indentation to be human readable, so use the `\t` modifier in front of a string in the `"body"` to tab it in. You can combine multiple `\t` characters to properly indent the code as you like.

Take the body portion of a snippet example below:

```json
    ...

    "body": [   
        "<html>",
            "\t<body>",
            "\t</body>",
        "</html>"
    ],

    ...
```

When inserted into a document, it would be displayed as:

```html
<html>
    <body>
    </body>
</html>
```

#### Testing Changes:

1. Press `F1` in Visual Studio Code
2. Click on "Preferences: Configure User Snippets"
3. Click on HTML
4. Copy the contents of `html.json` from the existing project, to your user snippets.
5. Create a local `html` file to test it in... e.g. `test.html`
6. Start typing in the command you wish to test.

#### Tab Locations

When a user enters a snippet, you may want to add some placeholder content for them to modify with ease, simply by pressing tab to cycle through them. The official documentation covers this more, but here are two simple examples.

You can have a user tab through locations in order from 1 to any number, but `0` is the final stop for the tab.
```json
    "body": [   
        "<h1>$1</h1>",
        "<p>$2</p>",
        "<p>$0</p>"
    ],
```

You can also have placeholder content that is automatically highlighted when the user tabs to it.

```json
    "body": [   
        "<h1>${1:Sample header}</h1>",
        "<p>${2:Paragraph 1}</p>",
        "<p>${0:Final Stop}</p>"
    ],
```
