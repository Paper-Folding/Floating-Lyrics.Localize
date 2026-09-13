<h1 align="center">
    <img src="icon/brand_icon256.png" alt="Plugin's branch icon" width="200">
    <br/>
    AIMP Floating Lyrics Plugin
</h1>

> Also see [Post on AIMP Forum](https://aimp.ru/forum/index.php?topic=77574.0).

> What's this?  
> The repo currently provides AIMP-Floating-Lyrics-Plugin localization files, releases and descriptions.  
> As I'm from China, I only know about Chinese and English. If you are interested, you can help translate this plugin to other languages.

### About Plugin

Here I present my hand-made plugin: AIMP Floating Lyrics Player and Editor Plugin.
It has these features:

1. It plays synchronized lyrics file(currently only supports ".lrc" file format with UTF-8 or ASCII encoding) for your song, it reads from your local lrc file alongside with your song file, or if your song file has synchronized lyrics embedded(like ID3v2 tag supported by AIMP), it will also play it;
2. For playing lyrics, you can style text color, text size, text shadow and more, I have written a preference window to configure these(and more configurations will be brought in the future updates);
3. For playing lyrics, currently I implemented 3 playing styles, one-line fade in fade out lyrics text, scroll horizontally and two-line;
4. You can make or edit your own ".lrc" file, just right click the playing lyrics window, choose "Make / Edit Lyrics". Or in AIMP playlist, right click playlist item(aka, songs in your library), choose "Send to - Lyrics Editor".
5. About the lyrics editor, when it opens, it will fill basic information automatically if possible, otherwise, you should input information yourself.
6. Some hint to use the lyrics editor: Currently I exposed 3 hotkeys to inert/replace/delete timestamp on active line, they are bound with F7/F8/F9 keys globally by default. You can always change these hotkeys in AIMP's "Hotkeys" configuration, but remember, local hotkeys won't work, because the lyrics editor is not recognized by AIMP as local window. The inserted or replaced timestamp is always the timestamp that AIMP is current playing at, so ideally you just play the song once and inserted timestamps all by yourself. There are also some handy buttons there, you can hover on them to see brief descriptions.

\*Tip: you can set lyrics playing window's background color to a totally transparent value, which looks fancy, however, even though it is transparent, it is not transparent for mouse clicks, which may cause some inconvenience. There is a workaround(since v1.3.0) when mouse hovers at that time, background will become less transparent. You can also enable click-through to prevent this.

As a software developer, this is my hobby project.  
If you find any issue or have any feature request, feel free to tell me on AIMP forum(https://aimp.ru/forum/index.php?topic=77574.0), or create a new issue here(https://github.com/Paper-Folding/Floating-Lyrics.Localize/issues/new).

### How to Install & Use

#### **Since v1.3.2:**

Plugin' file name looks like "aimp_floating_lyrics_x86_64_net[DOTNET_RUNTIME_VERSION]\_ver\_[VERSION].aimppack" since this version.

Be sure to install corresponding version of dotnet runtime(`DOTNET_RUNTIME_VERSION`) first (You only need to install one of the files listed below):

> .NET 8.0 Desktop Runtime (`DOTNET_RUNTIME_VERSION = net8.0`):
>
> - for AIMP x64: https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-8.0.30-windows-x64-installer
> - for AIMP x86: https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-8.0.30-windows-x86-installer
>
> .NET 10.0 Desktop Runtime (`DOTNET_RUNTIME_VERSION = net10.0`):
>
> - for AIMP x64: https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-10.0.11-windows-x64-installer
> - for AIMP x86: https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-10.0.11-windows-x86-installer

Plugin files are released as `.aimppack` format, you can easily install them with AIMP.

> There will be no .NET 8.0 releases in the future after .NET 8 reaches end-of-life, so it is highly recommended to upgrade to .NET 10.0 Desktop Runtime from now on.

#### **Prior to v1.3.2:**

1. Download and install ".NET 8.0 Desktop Runtime":
    - for AIMP x64: https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-8.0.30-windows-x64-installer
    - for AIMP x86: https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-8.0.30-windows-x86-installer

2. ~~Download and install "Visual C++ Redistributable 2012" from https://www.microsoft.com/en-us/download/details.aspx?id=30679, make sure to pick x86 or x64, which depends on AIMP x86 or x64 your are using. (a known issue listed below also mentions this runtime package, if you are not sure, I recommend you just download and install it);~~

You no longer need to install VC++ 2012 since v1.2.4, plugin has already included necessary files.

3. Unzip "aimp_floating_lyrics_x[86\_or\_64]\_ver\_[VERSION].zip" and drop extracted "aimp_floating_lyrics" folder to "[your-AIMP-x86-or-x64-installation-folder]/Plugins";
4. Finally, open AIMP and check "Floating Lyrics" menu item in AIMP's main menu to show lyrics player window and let's roll!

### Troubleshooting

In some rare cases when critical bug happened or crashes(contact me if you can), AIMP might disable the plugin entirely, you can follow these steps to re-enable:

> i. Make sure to close AIMP instance before proceed;  
> ii. Open "AIMP.ini" file within "[your-AIMP-installation-directory]/Profile" directory, search and delete these lines (it may differ from your file, but should look similar):
>
> ```ini
> [Plugins]
> aimp_floating_lyrics.dll=0
>
> [Plugins.CachedInfo]
> aimp_floating_lyrics.dll=0|||||1552900961
> ```
>
> iii. If this still does not work, you can try to delete whole `[aimp_floating_lyrics_plugin]` section in "AIMP.ini" file, which resets all configurations of the plugin.

Try launching AIMP after that, plugin should work now.

### Plugin Screenshots

![Floating lyrics Window](/screenshots/floating_window.png)
![Floating lyrics Window Context Menu](/screenshots/context-menu.jpg)
![Lyrics Editor](/screenshots/lyrics_editor.jpg)
![Preference Window](/screenshots/preference_window.jpg)
![Configuration Panel in AIMP](/screenshots/configuration_panel_in_AIMP.jpg)

### Update History

Please refer to [changelog.md](/changelog.md).
