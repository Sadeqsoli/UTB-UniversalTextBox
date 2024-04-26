## UTB - Universal Text Box

In this version of UTB, we're building upon the foundation laid out in the previous repository, enhancing it to support more languages and addressing minor bugs for a smoother user experience. A significant change involves renaming TMP log names for better practicality.

Special Thanks to:
- [pnarimani](https://github.com/pnarimani/)
- [hk1ll3r](https://github.com/hk1ll3r/)

### What's New?

- **Language Support**: We're expanding language support to ensure a wider range of users can benefit from UTB. Whether it's English, Persian, or any other language, UTB strives to provide a seamless text input experience.
  
- **Bug Fixes**: We're squashing minor bugs to enhance UTB's stability and reliability. Your experience with UTB should be smoother than ever before.

### Contribution

We welcome contributions to UTB! If you have ideas for improvements or want to fix bugs, feel free to submit pull requests. Together, we can make UTB even better.

### Documentation

**Note**: The documentation below requires updating to reference the new RTLTextMeshPro.

#### RTLTextMeshPro

RTLTextMeshPro is a powerful component designed to support right-to-left (RTL) text, particularly for languages such as Persian. With RTLTextMeshPro, you can seamlessly integrate RTL text input into your Unity projects.

**Features**:
- Automatic RTL Detection: RTLTextMeshPro intelligently detects RTL text, ensuring proper rendering and alignment.
- Language Support: RTLTextMeshPro supports languages with RTL scripts, providing a versatile solution for diverse text input needs.
- Customization Options: Tailor RTLTextMeshPro to your requirements with options to preserve numbers, enable Farsi script support, fix tags, and force fixes as needed.

**Usage**:
1. Attach RTLTextMeshPro to your TextMeshPro text component in Unity.
2. Customize the component properties to suit your requirements, such as preserving numbers or enabling Farsi script support.
3. RTLTextMeshPro will automatically handle RTL text rendering, ensuring a seamless experience for users.

### Future Updates

We're committed to continuously improving UTB to meet the evolving needs of our users. Stay tuned for future updates, including additional language support and feature enhancements.

### Feedback

Your feedback is invaluable to us! If you encounter any issues or have suggestions for improvement, please don't hesitate to reach out. Together, we can make UTB the best text input solution for Unity projects.

Thank you for choosing UTB - Universal Text Box!
# RTL Text Mesh Pro
This plugin adds Right-to-left language support to "TextMeshPro" Unity plugin. 
You need to have `TextMeshPro` plugin in your project. You can install TMPro via `Package Manager`.

Currently Arabic, Farsi and Hebrew are supported. If you find an issue with one of these languages or want support for another RTL language, open an issue.

[![openupm](https://img.shields.io/npm/v/com.nosuchstudio.rtltmpro?label=openupm&registry_uri=https://package.openupm.com)](https://openupm.com/packages/com.nosuchstudio.rtltmpro/)

- [Features](#features)
- [Installation](#installation)
- [Creating Fonts](#how-to-create-font-assets)
- [Usage](#usage-description)
- [Known Issues](#known-issues)
- [Contribution](#contribution)

# Features
### Farsi, Arabic and Hebrew
![Persian Text](Screenshots/Persian-Text.PNG)
![Arabic Text](Screenshots/Arabic-Text.PNG)
![Hebrew Text](Screenshots/Hebrew-Text.PNG)

### Realtime RTL Text
You don't need to convert, copy and paste texts. Start writing and texts will be converted right away.  
  
![Preview](Screenshots/Realtime.gif)

### Rich Text
All `Text Mesh Pro`'s tags are available in `RTL Text Mesh Pro`
  
![Rich Text Preview](Screenshots/Rich%20Text.PNG)

### RTL InputField (See [known issues](#known-issues))
Realtime InputField is supported.  
  
![Input Field Preview](Screenshots/InputField.gif)  

### RTL Dropdown (See [known issues](#known-issues))
  
![Dropdown Preview](Screenshots/Dropdown.gif)

### Multiline
Yes, This plugin has no problem with multiline RTL texts.
  
![Multiline Preview](Screenshots/Multiline.PNG)

### AutoSize
Auto Font Size is fully supported.  
  
![AutoSize Preview](Screenshots/AutoSize.gif)

### English, Farsi and Arabic digits are supported
  
![Numbers Preview](Screenshots/Numbers.PNG)

### Arabic Tashkeel
Arabic tashkeel are supported.  
  
![Tashkeel Preview](Screenshots/Arabic%20Text.PNG)  

### Zero-Width No-Joiner character support
You can insert Zero-Width No-Joiner character with Ctrl+Shift+2 hotkey.  
  
![ZWNJ Preview](Screenshots/zwnj.PNG)  

# Installation
> :information_source: You need to have `TextMeshPro` plugin in your project. You can install TMPro via `Package Manager`. DO NOT Install Text Mesh Pro from Asset Store.
 
### from .unitypackage file
Download the latest unitypackage file from the [releases](https://github.com/sorencoder/RTLTMPro/releases) section and import it into your project from "Assets -> Import Package -> Custom Package..." menu in Unity.

### from OpenUPM
[hk1ll3r](https://github.com/hk1ll3r/) maintains a package manager version of this repo on [OpenUPM](https://openupm.com/packages/com.nosuchstudio.rtltmpro/).

In Project Settings window, add OpenUPM as a scoped registry or if you have already added it, add the new scope to it.

![ProjectSettings](Screenshots/ProjectSettings.PNG)

Then in Package Manager window, change scope to *My Registries*. Select "RTL Text Mesh Pro" package and press *Install*.

![PackageManager](Screenshots/PackageManager.PNG)

The sample scenes and demo resources (fonts, shaders, etc.) are included in the package as a .unitypackage file. You need to import those into your Assets folder to use them. From the project window navigate to the package folder and double click "RTLTMPRo-demo-resources" file to import these assets into your project.

![Project](Screenshots/Project.PNG)

# How To Create Font Assets
You need to create font assets from font files to use them with TextMeshPro. Here are basic instructions for convenience. You can check out the [official TextMeshPro documentation](https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/FontAssetsCreator.html) to learn more.
  
Open `Window/TextMeshPro/Font Asset Creator` window.

![FontAssetCreatorWindow](Screenshots/FontAssetCreator.PNG)

1. Assign your font in `Font Source` field (Your font must include your characters)
2. Set atlas size. For Arabic we recomment 512x512 and for Hebrew 128x128 as a minimum. A larger atlas will have better quality but larger size on disk.
3. Set `Character Set` to `Unicode Range`.
4. Copy character ranges from files under `Assets/RTLTMPro/Ranges` folder into `Character Sequence (Hex)`.
   * Arabic letters are in `ArabicLetters.txt` file
   * Arabic digits are in `ArabicDigits.txt` file
   * Arabic tashkeel letter are in `ArabicTashkeel.txt` file.
   * All arabic characters are in `ArabicAll.txt`. Normally you would use this to create your font asset.
   * Hebrew letters are in `HebrewLetters.txt`.
6. Press `Generate Font Atlas` button and wait for it to generate the atlas.
7. Press `Save TextMeshPro Font Asset` and save the font asset.
  
## Usage Description

* Use `GameObject/UI/* - RTLTMP` menu to create RTL UI elements. (Alternatively you can replace `Text Mesh Pro UGUI` components with `RTL Text Mesh Pro`)
* Assign your font asset `Font Asset` property in `RTL Text Mesh Pro` component 
* Enter text in `RTL TEXT INPUT BOX` secion.

### Farsi
When checked, English numbers will be converted to Farsi numbers.
When unchecked, English numbers will be converted to Arabic numbers.  

### Preserve Numbers
When checked numbers will not be converted.  

### Force Fix
RTL Text Mesh Pro does not fix texts that start with English characters. 
Checking this checkbox forces RTL TextMeshPro to fix the text even when it starts with English character. 
**Multiline English texts will have problem on components that have `ForceFix` checked.**  

### Fix Tags
When checked, RTL Text Mesh Pro will try to fix rich text tags.  

# Known Issues
* **Fixed in latest version. For older versions follow the steps below**.
  We need to override the `text` property of `TextMeshProUGUI`. But the `text` property is not defined `virtual`. You need to manually make the property virtual.  
  * Open `TMP_Text.cs` from TextMeshPro source code
  * add virtual keyword to text property.  
  ![Text](Screenshots/TextProperty.PNG)
  * Open `RTLTextMeshPro.cs` and uncomment the top line where it says `//#define RTL_OVERRIDE`
  * Now you can use InputFields and Dropdowns.
  
# Contribution
All contributions are welcome. Make sure you follow the project's code style. We actively monitor pull requests.

Contact: 
- sorencoder@gmail.com
- hossein.shbz@gmail.com
