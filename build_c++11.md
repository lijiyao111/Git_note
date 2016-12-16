# Building C++11 code in Sublime Text 3

By default Sublime Text does not build C++ with C++ 11 features. Follow below steps to activate the c++ 11 building feature in Sublime Text 3.  Steps are tested on Windows. I don’t think this will be too different on Mac or Linux except the shortcut.

1. Install PackageResourceViewer plugin
2. Open the command center by entering Ctrl + Shift + p
3. Type “PackageResourceviewer: Open Resource”
4. Then C++ –>  C++ Single File.Sublime-build , this will open the build config file for C++
5. Where ever you g++ add -std=c++11 infront of it and save the file

```
{
    "shell_cmd": "g++ -std=c++11 \"${file}\" -o \"${file_path}/${file_base_name}\"",
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "working_dir": "${file_path}",
    "selector": "source.c, source.c++",

    "variants":
    [
        {
            "name": "Run",
            "shell_cmd": "g++ -std=c++11 \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\""
        }
    ]
}
```