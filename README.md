# trilium-themes
Themes for the [trilium](https://github.com/zadam/trilium) note app by [zadam](https://github.com/zadam/trilium)

* __Ayu-Mirage__ - based on [Ayu](https://github.com/ayu-theme/ayu-colors) by [ayu-theme](https://github.com/ayu-theme)
* __*COMING SOON*__ __Gruvbox__ - based on [Gruvbox](https://github.com/morhetz/gruvbox) by [morhetz](https://github.com/morhetz)

## "Installation"/Use steps
1. Clone this repo locally
2. Drag and Drop the .css files into trilium 
3. If you want the fonts used in the themes see the [font](https://github.com/bncarey42/trilium-themes/blob/master/README.md#fonts) instructions below 
4. Enable the theme in your options menu under the appearance tab.

### Fonts
Fonts in trilium are stored in the .woff2 format and in the notes table in the document have a mime type of "<<<???application/octet stream???>>> rather than '<<<???file/ttf???>>>'
1. All the fonts I've used are avalible to download at [Google Fonts](https://fonts.google.com) in .ttf format 
2. Convert the `.ttf` to `.woff2` I used [Google's woff2](https://github.com/google/woff2). 
3. Drag and drop converted font into trilium 
4. Update its mime type in the document. To do this you'll need the font's noteID. Open the options menu and choose "<<<???Querry SQL database???>>>" and execute the following update statement:
```SQL
UPDATE notes SET mime='<<<???application/octet stream???>>>' WHERE noteID='$noteID'; 
```
5. Update the file's attributes in trilium to include the <<<???CustomResourcePRovider???>>>=fonts/$fontName
