#Custom Unity Package

UPM Unity Package Manager is Unitys equivalent of NPM. This is the process required to create custom Unity packages distributed via UMP.
UPM packages must adhere to UPM standards and convensions for them to function properly.

see [Unitys docs](https://docs.unity3d.com/Manual/CustomPackages.html)

###Creating a new embedded package
Follow these instructions if you want to create a custom package inside your project folder.

1. Open the Unity Hub, and create an empty project on your computer. You can also use an existing project on your computer, and embed the package under your project or install the package from a local folder. However, starting with a new project makes the package contents less prone to errors.
2. Using your computer’s file manager (for example the Windows File Explorer or the macOS Finder), navigate to your project folder and locate the Packages subfolder.
3. Create a new subfolder for your package inside the Packages folder using a name that matches the package name. For example, if your package is called com.example.mypackage, the subfolder should also be called com.example.mypackage. Note: This is particularly important if your package contains assets, because the AssetDatabase looks for an asset path that matches Packages/<your-package-name>/Assets, regardless of what the actual folder is called.
4. Open your preferred text editor and create a JSON file called package.json.
5. Save it under the new package root folder you created.
6. Fill out all required and mandatory fields in the [package manifest](https://docs.unity3d.com/Manual/upm-manifestPkg.html) (package.json) file.
7. Layout your package structure to adhere to the [package layout convension](https://docs.unity3d.com/Manual/cus-layout.html)

###Package Manifest Example
```
{
  "name": "com.unity.example",
  "version": "1.2.3",
  "displayName": "Package Example",
  "description": "This is an example package",
  "unity": "2019.1",
  "unityRelease": "0b5",
  "dependencies": {
    "com.unity.some-package": "1.0.0",
    "com.unity.other-package": "2.0.0"
 },
 "keywords": [
    "keyword1",
    "keyword2",
    "keyword3"
  ],
  "author": {
    "name": "Unity",
    "email": "unity@example.com",
    "url": "https://www.unity3d.com"
  }
}
```

###Package Layout Example
```
<root>
  ├── package.json
  ├── README.md
  ├── CHANGELOG.md
  ├── LICENSE.md
  ├── Editor
  │   ├── Unity.[YourPackageName].Editor.asmdef
  │   └── EditorExample.cs
  ├── Runtime
  │   ├── Unity.[YourPackageName].asmdef
  │   └── RuntimeExample.cs
  ├── Tests
  │   ├── Editor
  │   │   ├── Unity.[YourPackageName].Editor.Tests.asmdef
  │   │   └── EditorExampleTest.cs
  │   └── Runtime
  │        ├── Unity.[YourPackageName].Tests.asmdef
  │        └── RuntimeExampleTest.cs
  └── Documentation~
       └── [YourPackageName].md
``

