# yolov4-tiny on DOTA dataset
## suh dud
kawjdklawjdlkawjd


### printing feature maps
uncomment line 35,36,37 and line 119 - 136
If you only want the first the first layer (or a specific layer for that matter) add `if( i >= 1) { break; }`

### Creating CAM for the different classes
Uncomment 242 - 246 and 253 - 254 in the same file and rebuild it again. but comment out 251 - 252 to make peace with the colab gods that despise images in the console
```
//static int img_counter = 0;
//img_counter++;
//char buff[256];
//sprintf(buff, "attention_img_%d.png", img_counter);
//save_image_png(attention_img, buff);
...
//sprintf(buff, "attention_mask_img_%d.png", img_counter);
//save_image_png(attention_mask_img, buff);
```
    
# TODO
- Lave en colab der ikke er scuffed, måske pointer hvordan vi fik den til at bruge de forskellige metoder til at få vores data.
  - Enten prøve at køre det forfra eller fiks det shit vi har nu, tænker på de fucking .jpg's over det hele
- Få output fra CAM og se om det er noget værd


# NOTES
- Darknet er HORRIBLE i colab pga. den ikke gider vise billeder i konsollen, det fucker ALTING.

- Alle former for `show_img` og `resize_window` skal af helvedes til før det dur, ellers så fucker det OGSÅ.
```
show_image(im, "adversarial data augmentation");
resize_window_cv("adversarial data augmentation", 500, 500);
```