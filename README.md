# ADMX Template for LibreOffice
Windows Group Policy Template for [AlloOffice](https://allotropia.de/) (also usable with [LibreOffice](https://www.libreoffice.org/)).

### Attention
When you add a "policy" in the admx file, add the corresponding "presentation" in all adml files (not just in your language).
Otherwise, this causes the following error for users of these adml files:

    Resource "$(string.something)" referenced in attribute displayName could not be found.
    File Path\to\something.admx, line xxx, column xxx

## Localization
[ITS Tool](http://itstool.org) is used to extract strings from adml file, and merge them back.

Create the pot from the adml file:

    itstool -i adml.its -o en-US/LibreOffice-adml.pot en-US/LibreOffice.adml

Then translate the strings with any translation app and generate the .mo file.

After that, merge the translated strings to the adml file:

    itstool -m LibreOffice-adml.mo -o it-IT/ LibreOffice.adml
