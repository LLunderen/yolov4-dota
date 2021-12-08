# yolov4-tiny on DOTA dataset

### printing feature maps
uncomment line 35,36,37 and line 119 - 136
If you only want the first the first layer (or a specific layer for that matter) add `if( i >= 1) { break; }` (will print each layer and their filters if not specified resulting in thousands of images)

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
- Få output fra CAM og se om det er noget værd (se teori)
- upload ting
  - lave nogle test billeder i repo som man henter og laver sine tests på (se workflow)
  - wget dataset fra drive (https://unix.stackexchange.com/questions/136371/how-to-download-a-folder-from-google-drive-using-terminal)
- # teori om CAM, se slack fra wigz


# NOTES
- Darknet er HORRIBLE i colab pga. den ikke gider vise billeder i konsollen, det fucker ALTING.

- Alle former for `show_img` og `resize_window` skal af helvedes til før det dur, ellers så fucker det OGSÅ.
```
// show_image(im, "adversarial data augmentation");
// resize_window_cv("adversarial data augmentation", 500, 500);
```


# workflow:
- ## download darknet
  - [x] build darknet
    - [ ] make a segment about changing the correct file to enable different features
- ## wget data
  - [x] dataset from google drive (https://drive.google.com/file/d/1f5riyMndim_yFMy63Nqn6IdwCOW6eK2j/view?usp=sharing)
  - [x] weights + configs + obj.data + obj.names (classes)

- ## train model
  - [x] maybe define parameters so it is easy to change between the different configs and setups. (if additional features are enabled then make sure the cfg and so on is correct)
- [x] show precision of model
  - detector map EZ
- [ ] show some results
  - [x] show predictions
  - [ ] show a collection of predictions
  - [ ] take some test images and show their resulst (can we rename the output to avoid overriding "predicions.jpg") (gid Alexey var lige så god til sit eget repo som han er til at svare comments https://github.com/pjreddie/darknet/issues/723#issuecomment-383332978)
    - show multiple at once (2-5?)