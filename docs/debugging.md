# Debugging

## VS Code
https://github.com/microsoft/vscode-recipes/tree/master/debugging-Ruby-on-Rails

You need to add ruby-debug-ide and debase to your gemfile

```sh
bundle add ruby-debug-ide

bundle add debase
```

### launch.json file

```js
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Start Rails server",
            "type": "Ruby",
            "request": "launch",
            "cwd": "${workspaceRoot}",
            "program": "${workspaceRoot}/bin/rails",
            "args": [
                "server",
                "-p",
                "3000"
            ]
        },
        {
            "name": "Debug Rails server",
            "type": "Ruby",
            "request": "launch",
            "cwd": "${workspaceRoot}",
            "useBundler": true,
            "pathToBundler": "/home/neil/.rbenv/shims/bundle",
            "pathToRDebugIDE": "/home/neil/.rbenv/versions/2.6.5/lib/ruby/gems/2.6.0/gems/ruby-debug-ide-0.7.0",
            "program": "${workspaceRoot}/bin/rails",
            "args": [
                "server",
                "-p",
                "3000"
            ]
        }
        // {
        //     "name": "Run RSpec - all",
        //     "type": "Ruby",
        //     "request": "launch",
        //     "cwd": "${workspaceRoot}",
        //     "program": "/path/to/rubygem/bin/rspec",
        //     "args": [
        //         "--pattern",
        //         "${workspaceRoot}/spec/**/*_rspec.rb"
        //     ]
        // },
        // {
        //     "name": "Debug RSpec - open spec file",
        //     "type": "Ruby",
        //     "request": "launch",
        //     "cwd": "${workspaceRoot}",
        //     "useBundler": true,
        //     "pathToBundler": "/home/neil/.rbenv/shims/bundle",
        //     "pathToRDebugIDE": "/path/to/rubygem/gems/ruby-debug-ide-x.x.x/bin/rdebug-ide",
        //     "debuggerPort": "1235",
        //     "program": "/path/to/rubygem/bin/rspec",
        //     "args": [
        //         "${file}"
        //     ]
        // },
        // {
        //   "name": "Debug RSpec - open spec file on a certain line",
        //   "type": "Ruby",
        //   "request": "launch",
        //   "cwd": "${workspaceRoot}",
        //   "useBundler": true,
        //   "pathToBundler": "/home/neil/.rbenv/shims/bundle",
        //   "pathToRDebugIDE": "/path/to/rubygem/gems/ruby-debug-ide-x.x.x/bin/rdebug-ide",
        //   "debuggerPort": "1235",
        //   "program": "/path/to/rubygem/bin/rspec",
        //   "args": ["${file}:${lineNumber}"]
        // }
    ]
}


```
