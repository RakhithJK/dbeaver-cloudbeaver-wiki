## Features
* [Description](#description)
* [Shortcuts](#shortcuts)
* [Statement Execution](#statement-execution)
* [Script execution](#script-execution)
* [[Query Execution Plan]]

## Overview

### Description
SQL Editor supports autocomplete, syntax highlight, statement execution, script execution and execution plan for some databases.

![SQL Editor](https://github.com/dbeaver/cloudbeaver/wiki/images/sql_editor/sql-editor.png)

### Shortcuts
| Shortcut                   | Description                             |
|----------------------------|-----------------------------------------|
| Ctrl+Enter                 | Execute SQL statement                   |
| Ctrl+\ or Ctrl+Shift+Enter | Execute SQL statement in new tab        |
| Alt+X                      | Execute script                          |
| Shift+Ctrl+E               | Show exectution plan                    |
| Alt+T                      | Open SQL Editor in separate browser tab |

### Statement Execution
To execute the statement place cursor on the line with the statement or select part of the script. Press the `Run` icon in the left toolbar or use the `Ctrl+Enter` shortcut. The result of the statement execution will be shown under the script editor area. Results will be grouped (`Result - 1 (1)`, `Result - 1 (2)`) if statement execution is finished with more than one result.

![Statement Execution](https://github.com/dbeaver/cloudbeaver/wiki/images/sql_editor/sql-editor-results.png)

### Script Execution

![Script Execution](https://github.com/dbeaver/cloudbeaver/wiki/images/sql_editor/sql-editor-script-executing.png)

