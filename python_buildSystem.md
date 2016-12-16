# Create python 2.7 build system

in Tools -> Build Systems -> New Build System

create a file with name *Python-2.7.sublime-build*. Inside the file:
```
{
    "cmd": ["Your_Python_Location", "-u", "$file"],
    "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
    "selector": "source.python"
}
```

Done!

For more, read (http://docs.sublimetext.info/en/latest/reference/build_systems/basics.html).