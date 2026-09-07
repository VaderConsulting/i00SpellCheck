# i00SpellCheck

i00 Spell Check is a stand-alone VB.NET WinForms spell-check and control-extension library by Kris Bennett (i00 Productions). It adds offline, no-Word, no-network spell checking to `TextBox` / `RichTextBox` / `DataGridView` (and plugins for `Label`, FastColoredTextBox, printing, translation, and speech) via `EnableControlExtensions()` / `EnableSpellCheck`. Third-party tree (assembly title Spell Check, company i00 Productions); there is no separable VaderConsulting wrapper.

**Source last updated:** 2015-06-20 · **Language:** VB.NET (plus C# test) · **Target:** .NET Framework 3.5 · **Output:** WinForms exe (`i00SpellCheck.exe`, also referenced as the library) + plugin and test exes

## Solution structure

| Project | Language | Type | Purpose |
|---------|----------|------|---------|
| `i00SpellCheck` (`i00SpellCheck/i00SpellCheck.vbproj`) | VB.NET | WinForms exe (`i00SpellCheck`) | Core spell-check engine, dictionaries (`dic.dic` / `syn.syn` / `def.def`), `SpellCheckControlBase`, TextBox/DataGridView plugins, about screen. |
| `i00BindingList` (`Components/i00BindingList`) | VB.NET | WinForms exe (`i00BindingList`) | BindingList + DataGridView with filter plugins (used by the spell-check UI). |
| `PrefMon` (`Components/PrefMon`) | VB.NET | WinForms exe (`PrefMon`) | Performance-monitor form used by the engine. |
| `LabelPlugin` | VB.NET | WinForms exe plugin | Spell-check overlay for `Label`. |
| `FastColoredTextBoxPlugin` | VB.NET | WinForms exe plugin | Spell-check plugin for Pavel Torgashov's FastColoredTextBox. |
| `TextBoxPrinter` | VB.NET | WinForms exe plugin | TextBox printing control extension. |
| `TextBoxSpeechRecognition` | VB.NET | WinForms exe plugin | Speech / dictation control extension. |
| `TextBoxTranslator` | VB.NET | WinForms exe plugin | Translation control extension (flag images). |
| `OSControlRenderer` | VB.NET | WinForms exe plugin | OS-themed control renderer extension. |
| `SelectedControlHighlight` | VB.NET | WinForms exe plugin | Highlights the selected control. |
| `BasicTest` | VB.NET | WinForms exe | Minimal host calling `EnableControlExtensions()`. |
| `CSharpTest` | C# | WinForms exe | C# sample host (`this.EnableControlExtensions()`). |
| `HanksDictionaryTest` | VB.NET | WinForms exe | Alternate dictionary from Hanks `dic.txt` word counts. |
| `OpenOfficeHunspellDictionaryTest` | VB.NET | WinForms exe | Hunspell / OpenOffice `en_US` dictionary test. |
| `Test` | VB.NET | WinForms exe | Full demo harness (`StartupObject` `Test.Autoexec`). Live folder truncated in the OneDrive zip (only `Autoexec.vb`); complete copy under `Backup/Tests/Test`. |
| `WordDictionaryTest` | VB.NET | WinForms exe | Microsoft Word dictionary adapter test. Live folder empty after truncated zip; complete copy under `Backup/Tests/WordDictionaryTest`. |

Solution folders also include **Plugins**, **3rd Party**, **Components**, and **3rd Party Dictionaries**. `Backup/` is a Visual Studio upgrade backup of the same projects. `~Used/` holds related scratch projects and bundled binaries (`FastColoredTextBox.dll`, `NHunspell.dll`).

## How to open

Open `SpellCheck.sln` in Visual Studio 2012 or later (solution format 12.00 / Visual Studio 2012; `.vbproj` ToolsVersion 3.5, ProductVersion 9.0.21022 / VS 2008; `CSharpTest.csproj` ToolsVersion 4.0 after upgrade). All listed projects target .NET Framework 3.5 WinForms. Build `i00SpellCheck` first, then plugins and tests. `Test` and `WordDictionaryTest` need the `Backup/Tests/` copies (or a restored zip) because the live folders were truncated in the OneDrive download.

## Requirements

- Visual Studio 2008 to 2012, .NET Framework 3.5

## Attribution and provenance

Working copy from Dave Robinson's OneDrive Historical Dev folder `i00SpellCheck`.

- **Author:** Kris Bennett, i00 Productions
- **Assembly title / product:** Spell Check
- **Assembly company:** i00 Productions
- **Assembly copyright:** ©i00 Productions
- **Upstream:** [i00/i00SpellCheck](https://github.com/i00/i00SpellCheck); historical Code Project / VBForums *i00 Spell Check and Control Extensions*
- **File headers:** ©i00 Productions All rights reserved / Created by Kris Bennett; property remains with i00 Productions; VBForums usage-notice request

VS `.suo` / `.user` files were in the zip and are gitignored. `bin/` and `obj/` build outputs (including per-test copies of definition PNGs and translator flags) are gitignored. OneDrive zip was truncated (no EOCD); `7z` recovered source. Missing live files were almost all under `bin/`; `Tests/Test` and `Tests/WordDictionaryTest` live source is incomplete (use `Backup/`).

## License

Original **i00 Productions** terms (file headers + later MIT as published on GitHub by Kris Bennett). This repository does **not** relicense the tree as VaderConsulting MIT. There is no separable Dave Robinson wrapper. See `LICENSE` and `THIRD_PARTY_NOTICES.md`.
