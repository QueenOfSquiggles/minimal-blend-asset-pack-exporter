# minimal-blend-asset-pack-exporter
 A simple setup for bulk exporting asset packs in Blend format


# Requirements

You will need **blender** and **python** to be installed on your computer. Also blender will need to be on your system PATH. Check with your operating system to see how to do this. If you installed it through normal channels, it's likely already on the path.

# Instructions

There is a fairly helpful prompt system in the scripts. But there are some things to know.

## Downloading

Click on the green `Code` button near the `About` section of the page. At the bottom of the panel that opens, click the option `Download ZIP`.

Once it is downloaded, extract the ZIP archive into a folder.

Finally, you can place the asset pack folders and/or files into the same directory as the `.py` files. (They can be in any number of sub-folders, but they cannot be in a zip archive).

## Glob Patterning
Because this script uses glob patterning, you will need to be sure that `glob` is installed for your python installation. It is part of the standard library, so it is very likely already installed, but if you have a very old installation it may not be.

## Running the script
Open a terminal or command prompt in the directory.

Run the command:
`python run_export_all.py`

## Interacting with the prompts

### Select File Type
You will be prompted with a list of options for supported file types. You can enter the number of the option or the text of the option to choose it. If you fail to match any of the options, you will be prompted again until one is chosen.

For example, if you would like to export for GLTF, which is a widely used file format for 3D models, you could enter:
- `1`
- `gltf`
- `GLTF`

But entering any of the following would not select the GLTF option:
- `0`
- `gl`
- `G`

### Check File List (Optional)
You will be prompted for whether or not to view the files. This is a really good idea if this is your first time using this script. It asks for `(y/n)` which means it is a "yes" or "no" prompt, but it is shortened to 'y' and 'n'. For these prompts, enter `y` if you would like to select it. And `n` if you do not.

For this option, `y` will lead to the script printing out the path of every blend file that has been found in the sub directories. This may be a lot all at once because the files are printed on a separate line


### Cancel Operation (Optional)
This prompts `(y/n)` just like the last prompt. And for `y` it will close the script without exporting the files. This is available in case something has gone wrong, such as accidentally selecting the wrong file type, or if the incorrect blend files were targeted.

### Exporting Phase
The exporting phase is completely automatic. It will run through every blend file found and run the associated python script with blender.

**It is very important** that these scripts are in the same place as the main script and that none are renamed or messed with in any way.

Because of how blender runs python scripts, it will be opened and closed for each individual blend file. The script is set up to not open the GUI when this happens but if something goes wrong that may happen.

Once all of the exports are complete, the script will exit.

If you encounter an error during this step, it is likely that `blender` is not a command or program recognized by your computer. This means you need to put it on your system PATH. Like in the requirements section, check with your Operating System (Windows, Mac, Linux distro) to see how to do this.
