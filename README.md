# trilium-themes

Themes for the [trilium](https://github.com/zadam/trilium) note app by [zadam](https://github.com/zadam/trilium)

* __Ayu-Mirage__ - based on [Ayu](https://github.com/ayu-theme/ayu-colors) by [ayu-theme](https://github.com/ayu-theme)
* __Darkasher__ - a little something I threw together on a Sunday morning
* __TrashPanda__ - based on [jetbrains-trash-panda-theme](https://github.com/jasonhulbert/jetbrains-trash-panda-theme) by [Jason Hulbert](https://github.com/jasonhulbert)
* __NuDark__ - I was bored and wanted something Nu

For more info on theming trilium see the [trilium wiki](https://github.com/zadam/trilium/wiki/Themes).

## Installation/Use

1. Clone this repo locally
2. Drag and Drop / Import the .css files into trilium and ensure that the note is created as a `CSS Code note`
3. Update the new note's attributes to include the `appTheme` lable set equal to the name of your theme e.g. `#appTheme=my-cool-theme`
4. If you want the fonts used in the themes see the [font](https://github.com/bncarey42/trilium-themes/blob/master/README.md#fonts) instructions below
5. Enable the theme in your options menu under the appearance tab.

### Fonts

Fonts in trilium are stored in the .woff2 format and in the notes table in the document have a mime type of `'application/octet-stream'` rather than `'file/woff2'`. To define custom fonts trilium uses a [custom request handler](https://github.com/zadam/trilium/wiki/Custom-request-handler). These instruction are how I've found to get fonts to work.

1. All the fonts I've used are avalible to download from the [google webfonts helper](https://google-webfonts-helper.herokuapp.com/fonts) in many formats including .woff2
2. Drag and drop the font file into trilium into a subdirectory of your themes directory called 'fonts'
3. Update the note's mime type in the database document. To do this you'll need the font's noteID (you can get this by clicking the `Note Info` button in the note's top toolbar). Open the menu and choose Open SQL Console or use alt-O and execute the following update statement:

    ```SQL
    UPDATE notes SET mime='application/octet-stream' WHERE noteID='$noteID'; 
    ```

4. Update the file's attributes in trilium to include 'customResourceProvider=fonts/$fontName'
