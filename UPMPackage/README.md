# UTB - Universal Text Box
This plugin adds multi-lingual support to "TextMeshPro" Unity plugin. 
You need to have `TextMeshPro` plugin in your project if you have unity 2022 or older. You can install TMPro via `Package Manager`.

Currently Arabic, Farsi and Hebrew are supported. If you find an issue with one of these languages or want support for another RTL language, open an issue.
In this version of UTB, we're building upon the foundation laid out in the previous repository, enhancing it to support more languages and addressing minor bugs for a smoother user experience. A significant change involves renaming TMP log names for better practicality.

Special Thanks to:
- [pnarimani](https://github.com/pnarimani/)
- [hk1ll3r](https://github.com/hk1ll3r/)
# Attention
Looking for maintainers. Send email to solisadeq@gamil.com

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


# Features for RTL languages
### Farsi, Arabic and Hebrew
![Persian Text](Screenshots/Persian-Text.PNG)
![Arabic Text](Screenshots/Arabic-Text.PNG)
![Hebrew Text](Screenshots/Hebrew-Text.PNG)

### Realtime milti-lingual Text
You don't need to convert, copy and paste texts. Start writing and texts will be converted right away.  
  
![Preview](Screenshots/Realtime.gif)

### Rich Text
All `Text Mesh Pro` and `RTL Text Mesh Pro`'s tags are available in `UTB - Universal Text Box`.
  
![Rich Text Preview](Screenshots/Rich%20Text.PNG)

### Multi-Lingual InputField (See [known issues](#known-issues))
Realtime InputField is supported.  
  
![Input Field Preview](Screenshots/InputField.gif)  

### Multi-Lingual Dropdown (See [known issues](#known-issues))
  
![Dropdown Preview](Screenshots/Dropdown.gif)

### Multiline
Yes, This plugin has no problem with multi-line in multi-lingual texts.
  
![Multiline Preview](Screenshots/Multiline.PNG)

### AutoSize
Auto Font Size is fully supported.  
  
![AutoSize Preview](Screenshots/AutoSize.gif)

### Chinese,Japanise and Korean languages are soon gonna be supported

more languages are in order.  

### English, Farsi and Arabic digits are supported
  
![Numbers Preview](Screenshots/Numbers.PNG)

### Arabic Tashkeel
Arabic tashkeel are supported.  
  
![Tashkeel Preview](Screenshots/Arabic%20Text.PNG)  

### Zero-Width No-Joiner character support
You can insert Zero-Width No-Joiner character with Ctrl+Shift+2 hotkey.  
  
![ZWNJ Preview](Screenshots/zwnj.PNG)  

# Installation
* You need to have `TextMeshPro` plugin in your project. You can install TMPro via `Package Manager`if you're using 2022 or older but there is no need for 2023 and newer versions.
### from .unitypackage file
Download the latest unitypackage file from the [releases](https://github.com/Sadeqsoli/UTB-UniversalTextBox/releases/) section and import it into your project from "Assets -> Import Package -> Custom Package..." menu in Unity.

### from OpenUPM
[SadeqSoltani](https://github.com/Sadeqsoli) maintains a package manager version of this repo on [OpenUPM](https://openupm.com/packages/com.universaltextbox.utb/).

In Project Settings window, add OpenUPM as a scoped registry or if you have already added it, add the new scope to it.

![ProjectSettings](Screenshots/ProjectSettings.PNG)

Then in Package Manager window, change scope to *My Registries*. Select "RTL Text Mesh Pro" package and press *Install*.

![PackageManager](Screenshots/PackageManager.PNG)

The sample scenes and demo resources (fonts, shaders, etc.) are included in the package as a .unitypackage file. You need to import those into your Assets folder to use them. From the project window navigate to the package folder and double click "RTLTMPRo-demo-resources" file to import these assets into your project.

![Project](Screenshots/Project.PNG)
## How To Use
1. Open one of the range files in `Assets/UniversalTextBox/Ranges/` folder using your favorite text editor.
2. Make sure you have copied the ranges that you want to use.
3. Open the `Window/TextMeshPro/Font Asset Creator` window in Unity.
4. Assign your font in the `Font Source` field (ensure your font supports RTL characters).
5. Set `Character Set` to `Unicode Range`.
6. Paste the copied ranges inside the `Character Sequence (Hex)` field.
7. Press the `Generate Font Atlas` button and wait for it to generate the atlas file.
8. Press the `Save TextMeshPro Font Asset` button and save the asset.
9. Use the `GameObject/UI/* - UTB` menu to create Multi-Lingual UI elements, or replace `Text Mesh Pro UGUI` and `RTL Text Mesh Pro` components with `UTB - Universal Text Box`.
10. Assign your font asset to the `Font Asset` property in the `UTB - Universal Text Box` component.
11. Enter text in the `UTB INPUT BOX` section.
  
## Usage Description
### Farsi [Gonna Change]
When checked, English numbers will be converted to Farsi numbers.
When unchecked, English numbers will be converted to Arabic numbers.  

### Preserve Numbers [Gonna Change]
When checked numbers will not be converted.  

### Force Fix  [Gonna be Deleted]
RTL Text Mesh Pro does not fix texts that start with English characters. 
Checking this checkbox forces RTL TextMeshPro to fix the text even when it starts with English character. 
**Multi-line English texts will have problem on components that have `ForceFix` checked.**  

### Fix Tags  [Gonna Change]
When checked, RTL Text Mesh Pro will try to fix rich text tags.  

# Known Issues
* **Fixed in latest version. For older versions follow the steps below**
  We need to override the `text` property of `TextMeshProUGUI`. But the `text` property is not defined `virtual`. You need to manually make the property virtual.  
  * Open `TMP_Text.cs` from TextMeshPro source code
  * add virtual keyword to text property.  
  ![Text](Screenshots/TextProperty.PNG)
  * Open `RTLTextMeshPro.cs` and uncomment the top line where it says `//#define RTL_OVERRIDE`
  * Now you can use InputFields and Dropdowns.
  
# Contribution
All contributions are welcomed. Just make sure you follow the project's code style. also if you want to use RTL ONLY visit [pnarimani](https://github.com/pnarimani/RTLTMPro) or [hk1ll3r](https://github.com/hk1ll3r/RTLTMPro).
If you have any issues leave your comment [here](https://github.com/Sadeqsoli/UTB-UniversalTextBox/issues) and if there was any question or contribution to Universal Text Box contact me on: solisadeq@gamil.com

### Feedback

Your feedback is invaluable to us! If you encounter any issues or have suggestions for improvement, please don't hesitate to reach out. Together, we can make UTB the best text input solution for Unity projects.

Thank you for choosing UTB - Universal Text Box!