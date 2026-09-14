# Wortshatzer User Guide

This guide covers the normal Windows workflow: install Wortshatzer, capture words while studying, save useful vocabulary, and move it into Anki.

## 1. Install Wortshatzer

Open the [latest release](https://github.com/MAliD0/Wortshatzer-Releases/releases/latest) and download **`Wortshatzer-Installer.exe`**.

Run the installer and choose the application folder you want. Wortshatzer keeps its normal user data separately under:

```text
%LOCALAPPDATA%\Wortshatzer.UserData
```

This keeps vocabulary and settings independent from the application installation directory.

Portable, MSI, and standard setup packages may also be available on the release page. The interactive installer is the recommended choice for normal use.

## 2. First launch

On first launch, configure the language workflow you want to use.

Start with:

1. **Source language** — the language of the word you are learning.
2. **Target language** — the language you want translations or explanations in.
3. **Translation / dictionary workflow** — choose the provider combination appropriate for that language pair.
4. **Vocabulary list** — choose where newly saved words should go.

The current application is especially focused on German and Japanese learning workflows.

## 3. Capture a word

Wortshatzer is designed so you do not need to keep the main window in front while studying.

### Screen-region OCR

The default capture shortcut is:

```text
Ctrl + Shift + O
```

Use it when a word is visible on screen:

1. Press `Ctrl + Shift + O`.
2. Select the word or short phrase on screen.
3. Wortshatzer performs OCR using the active source-language workflow.
4. The recognized result is normalized and passed to the configured translation/dictionary pipeline.
5. Review the result in the popup.

This is useful for webpages, PDFs, games, videos with readable subtitles, and other applications where copying text directly is inconvenient.

OCR accuracy depends on the source image. Larger text, good contrast, and a tight selection usually produce better results.

### Clipboard capture

Use clipboard capture when the source application lets you copy text normally.

Copy a word or short phrase, then use Wortshatzer's clipboard capture action from the application or tray workflow. Clipboard capture avoids OCR when clean source text is already available.

### Manual input

Use manual input when:

- OCR has difficulty with a stylized font;
- the source cannot be copied;
- you want to correct a captured form;
- you simply want to look up a word directly.

## 4. Review the result

A result can contain more than a direct translation. Depending on the selected language and provider workflow, Wortshatzer may show:

- normalized or canonical word form;
- translation;
- dictionary meanings or senses;
- examples;
- part-of-speech information;
- language-specific fields;
- source information used for enrichment.

### German

German workflows can use canonical-form and morphology information, including Verbformen-backed data where configured. This helps turn an inflected form encountered in real text into a more useful learning entry.

### Japanese

Japanese workflows support normalization across romaji, kana, and kanji and can use Japanese lexical lookup data. This makes capture more useful when the visible form and the form you want to learn are not identical.

## 5. Save vocabulary

When a result is useful, save it to the selected vocabulary list.

Saved vocabulary is stored locally. Depending on the available enrichment data, an entry can retain captured, canonical, and learning forms together with translation and dictionary fields.

Open **Vocabulary** to manage saved material. From there you can review entries, edit them, remove unwanted entries, and refresh information from the configured source when supported.

## 6. Configure card fields

Wortshatzer lets the vocabulary workflow and the Anki card workflow remain related without forcing every available dictionary field onto every card.

Use the card / Anki field settings to choose which information is useful for your learning direction. Typical fields include combinations of:

- source word;
- translation;
- reading or alternate writing;
- definition;
- examples;
- grammar or morphology information;
- tags.

You can also configure card direction and duplicate behavior where those options are available.

## 7. Use Anki

Wortshatzer supports two main ways to move vocabulary into Anki.

### Direct AnkiConnect synchronization

Use this when you want Wortshatzer to send configured cards directly to Anki.

Before synchronizing:

1. Install the **AnkiConnect** add-on in Anki.
2. Start Anki.
3. Make sure AnkiConnect is running normally.
4. Configure the appropriate Anki deck / card settings in Wortshatzer.
5. Run the explicit synchronization action from Wortshatzer.

If synchronization fails, first check that Anki itself is open and that AnkiConnect is installed and enabled.

### TSV export

Use TSV export when you want a file-based workflow instead of direct synchronization.

Export the selected vocabulary list and import the resulting file through Anki's normal import interface. This is also useful for inspecting or editing the exported data before import.

## 8. Desktop and tray behavior

Wortshatzer is intended to remain available while you study in other applications.

Depending on your settings, it can:

- remain available through the Windows tray;
- close the main window to the tray instead of exiting;
- launch when you sign in to Windows;
- continue providing capture shortcuts while the main window is hidden.

Use **Exit Wortshatzer** when you want to fully stop the application rather than only hide the main window.

Wortshatzer also uses single-instance handling so a second launch does not create another independent owner of the same tray, hotkeys, and local database.

## 9. Appearance

The desktop interface supports:

- **Light** theme;
- **Dark** theme;
- **System** theme;
- optional user color overrides.

Use the appearance settings to make the popup and main interface fit the environment in which you normally study.

## 10. Provider notes

Some translation and dictionary workflows use online services or websites. Their availability can depend on network access and on the external provider continuing to expose compatible data.

DeepL is optional and requires valid DeepL configuration before it can be used. Dictionary fallback chains and scraper profiles allow the application to keep provider-specific behavior separate from the rest of the vocabulary workflow.

## Troubleshooting

### OCR recognized the wrong text

Try selecting a smaller region containing only the target word. Avoid including unrelated text, icons, or subtitles above and below the intended line. If recognition is still wrong, use manual input for that word.

### Nothing happens when I use the OCR shortcut

Check that Wortshatzer is still running in the Windows tray and verify the configured shortcut in Settings. Another application can also reserve the same key combination.

### Anki synchronization fails

Check these in order:

1. Anki is open.
2. AnkiConnect is installed and enabled.
3. The configured deck/card settings still exist in Anki.
4. Wortshatzer is using the intended Anki synchronization configuration.

You can use TSV export as a file-based alternative when direct synchronization is not appropriate.

### I closed the main window but Wortshatzer is still running

If **Close main window to tray** is enabled, this is expected. Open Wortshatzer again from the tray icon or use **Exit Wortshatzer** to stop it completely.

### Where is my vocabulary stored?

Normal persistent data is kept under:

```text
%LOCALAPPDATA%\Wortshatzer.UserData
```

Do not delete this folder if you want to keep the local vocabulary database and settings.

## Updates

Download current installers and portable builds from the [Wortshatzer Releases page](https://github.com/MAliD0/Wortshatzer-Releases/releases).

The release repository is also the public location for user-facing documentation and release downloads.
