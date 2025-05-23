# Ableton Live Manual Online to HTML & PDF
.NET project to download and generate the Ableton Live online manual to HTML & PDF

> This project is focused in the generation of the version 12 manual HTML & PDF of Ableton Live, but is valid to generate the HTML & PDF files for the manual of Ableton Live 11 too

Online References: 
* [Ableton Live Manual (all)](https://help.ableton.com/hc/en-us/articles/206769450-Live-Manual)
* [Ableton Live 11 - Manual Online](https://www.ableton.com/en/live-manual/11/)
* [Ableton Live 12 - Manual Online](https://www.ableton.com/en/live-manual/12/)

Offiline Documents:
* An example of the manual of Ableton Live 12 generated by this application can be read [here HTML](/docs/Ableton_Live_12-en.html) or [here Markdown](/docs/Ableton_Live_12-en.md) or [here PDF](/docs/Ableton_Live_12-en.pdf) with date generation *24/05/2024 - 12:00 AM*


## The problem
Ableton Live 12 is the new version of Ableton Live, but the manual of the product can be read online only (at the moment)

A lot of people need to be able to read the manual offline, in the tablet, computer or other device

To solve with situation, this project generates the content into HTML and PDF formats to be used offline

> Note: This project lets you generate the PDF document for the version 11 and version 12. You can modify the settings of this application to point the version and language. However, and in this moment, Ableton has the documentation for the version 12 in English only


## Requirements
This project is a *Console Application* developed using [Microsoft .NET 8](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)

Additionally, this project uses two external packages
* [System.Configuration.ConfigurationManager](https://www.nuget.org/packages/System.Configuration.ConfigurationManager/) to read the application's settings
* [HtmlAgilityPack](https://www.nuget.org/packages/HtmlAgilityPack/) to read the HTML content and find information by tags, etc, and extract the content
* [PuppeteerSharp](https://www.nuget.org/packages/PuppeteerSharp/) to generate the PDF file


## Features
The main goal to write this project is to be able to generate the HTML and PDF content to read the manual of Ableton Live offline in the train, home or other place

You can modify some settings to adapt the process to your needs
- `HeaderPage`
- `HomePage`
- `HtmlFilePath`
- `LinkPageContains`
- `PdfFilePath`

### Features included in the Settings

#### **HeaderPage**
`HeaderPage` is **optional** and lets you to write some information for the first and extra page of the HTML and PDF

The default content of this part is
```HTML
<div id=\"chapter_content\" style=\"display:block;page-break-inside: avoid;page-break-after: avoid;page-break-before: always;\"><h1 data-number=\"0\" id=\"welcome-to-live\">Ableton<br>Reference Manual<br>Version 12</h1><br></div>
```

> Important: the first block or part in the **style** tag, is important to break the page when we want to print the content into PDF

The special characters like `<`, `>` or `"` should be replaced by `&lt;`, `&gt;` or `'`

In the content used by default, we should put in the settings something like:
```HTML
&lt;div id=\'chapter_content\' style=\'display:block;page-break-inside: avoid;page-break-after: avoid;page-break-before: always;\'&gt;&lt;h1 data-number=\'0\' id=\'welcome-to-live\'&gt;Ableton&lt;br&gt;Reference Manual&lt;br&gt;Version 12&lt;/h1&gt;&lt;br&gt;&lt;/div&gt;
```

#### **HomePage**
`HeaderPage` is <span style="color:red">**mandatory**</span> and it represents the web page where is located the manual that we want to print

For example: [https://www.ableton.com/en/live-manual/12/](https://www.ableton.com/en/live-manual/12/)

#### **HtmlFilePath**
`HtmlFilePath` is <span style="color:red">**mandatory**</span> and represents the path and name file for the HTML document

For example: `C:\temp\document.html`

#### **LinkPageContains**
`LinkPageContains` is <span style="color:red">**mandatory**</span> and represents a special section to help the process to get the content correctly. It is very similar to the `HomePage`

For example: `/en/live-manual/12/`

#### **PdfFilePath**
`PdfFilePath` is <span style="color:red">**mandatory**</span> and represents the path and name file for the PDF document

For example: `C:\temp\document.pdf`


## Running the application
You can generate and execute the code manually or use the binaries I have generated (*for Windows only in this moment*)

> Your will need [.NET 8](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) to execute this application

- The binaries for Windows (**v1.1.0**) can be located here: [Win-x64 - AbletonLiveManualToPDF v1.1.0.zip](/releases/windows/Win-x64&#32;-&#32;AbletonLiveManualToPDF&#32;v1.1.0.zip)

You will need to execute this tool with the Console or Terminal. In the case of use [Terminal](https://apps.microsoft.com/detail/9n0dx20hk701) the tool will write the direct links to the files generated by the application. To open a file, put over the link and do click pressing the **Ctrl** key

In other case, you can download the project into your hard disk and execute the file `run.bat` in Windows with the Console

In other Operating Systems like macOS or Linux, you can execute the project too (not tested yet but it should be ok!)

There is another command named `build-release.bat` to be used with the Console that generates the binaries that in this case and for Windows, you can find in the previous link
