#rosblockly
---
> This is a project based on __*Google Blockly*__ and [__*Robot Web Tools*__][3]


###Requirements
**Notice**: You may need a proxy to access the world Internet.
- use block_factory to build new blocks, add the generators(python) for them.
- If your js code is in **ECMASCRIPT5** style, please add `("language","ECMASCRIPT5),"`  in each **gen_*()** function's `param` setting variable.
- `tsocks ./build.py` compile blockly with tsocks+SSocks.
- Use `RobotWebTools`[`starter_template`][1], follow the [`ROS JavaScript Style Guide`][2]

[1]: https://github.com/RobotWebTools/starter-template "Github | RobotWebTools starter template"
[2]: http://wiki.ros.org/JavaScriptStyleGuide "ROS Wiki | ROS JavaScript Style Guide"
[3]: http://robotwebtools.org/ "Robot Web Tools | robotwebtools.org"
