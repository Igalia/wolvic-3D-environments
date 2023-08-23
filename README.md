# Wolvic 3D environments

This is the official repository of 3D environments for the Wolvic VR Browser.

## Adding a new environment

1. Environment creators need to provide 6 different images, one for each face of a cube
2. Compress the new textures
*  It can be generated using the `mipgen` software
      * Available in Debian in `libfilament-tools`
      * Command: `mipgen -f ktx -m 1 -c etc_srgb8_rgba_100 <source.png> <destination.ktx>`
      * To generate all of them in a loop
      
         `$ for f in PATH_TO_UNCOMPRESSED_DIR/*png; do mipgen -f ktx -m 1 -c etc_srgb8_rgba_100 $f PATH_TO_DESTINATION_DIR/$(basename ${f%.*})_srgb.ktx; done`
* The new `.ktx` textures should be 513kB size. If they're bigger then you are either not using 1024x1024 images or you're generating textures with alpha layer
3. The new environment must be in its own folder and it should provide 5 files, since some devices don't support ktx compression format (the default)
* A 256x256 screenshot of the new enviroment (env_name.[png | jpg])
* A zip file with the 'rgb' textures with 'ktx' compression (envName.zip)
* A zip file with the 'srgb' textures with 'ktx' compression (envName\_ktx_srgb.zip)
  * both the zip and the files it contains must have the '_srgb' prefix
* A zip file with the 'rgb' textures with 'jpg' compression (envName\_jpg_rgb.zip)
* A zip file with the 'srgb' textures with 'jpg' compression (envName\_jpg_srgb.zip)
  * both the zip and the files it contains must have the '_srgb' prefix



