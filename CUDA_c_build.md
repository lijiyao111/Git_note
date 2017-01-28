# Building CUDA code in Sublime Text 3

1. Install Visual Studio (2015 version I am using)
2. Install CUDA
3. ctrl+shift+p -> Package Control: Install Package -> CUDA C++
4. ctrl+shift+p -> “PackageResourceviewer: Open Resource”
5. Then CUDA C++ –>  cuda-c++.sublime-build , this will open the build config file for CUDA C

```
{
    "shell_cmd": "\"C:\\Program Files (x86)\\Microsoft Visual Studio 14.0\\Common7\\Tools\\vsvars32.bat\" & nvcc -Wno-deprecated-gpu-targets \"${file}\" -o \"${file_path}/${file_base_name}\"",
\\ check the location of your vsvars32.bat, which is in the same location as VsDevCmd.bat (Developer Command Prompt for VS2015) file, above shows location on my computer

    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "working_dir": "${file_path}",
    "selector": "source.c, source.c++",

    "variants":
    [
        {
            "name": "Run",
            "shell_cmd": "\"C:\\Program Files (x86)\\Microsoft Visual Studio 14.0\\Common7\\Tools\\vsvars32.bat\" & nvcc -Wno-deprecated-gpu-targets \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\""
        }
    ]
}
```
