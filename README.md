# `nodejs` - Help Installation, Error and Problem Resolve

Note:
- This documentation is only for help common issue that writer's found.
- For some reason, this documentation maybe not resolve the problem.

## On Windows

### node-gyp with msvs_version and msbuild_path problem

Some people may confuse they can't set npm config and showing error. So this is just small trick may can fix the problem.
Before editing you have to install python and msbuild. The msbuild can use from visual studio instead.
For the python you can ignore if you have installed before.
For the vs_buildtools you can download from here [Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools)
(using "Visual C++ build tools" workload) or [Visual Studio Community](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community)
(using the "Desktop development with C++" workload)

#### Set npm config

If you can't set config from command ```npm config set msvs_version``` just edit the configuration manually with this command from your cmd or powershell

```
npm config edit
```

The notepad will open .npmrc file and add this to your .npmrc file

```
msvs_version=2022
msbuild_path=C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\MSBuild\Current\Bin\MSBuild.exe
python=C:\Users\{Your User Name}\AppData\Local\Programs\Python\Python311\python.exe
```

For those config only example, if you have different path for your file, just add to that config.
Save changes and run your npm command again to install dependencies or something else.

Tested with:
- node v18.14.2
- npm v9.5.0
- msvs_version 2017 and 2022
- python v2.7.15 and python v3.11.1

Note:
- If use msvs_version 2022 and python 3.11 still error on install node-sass v7 try to install node-sass@latest or v8.0.0

Source:
- [node-gyp documentation](https://github.com/nodejs/node-gyp#on-windows)
