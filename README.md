#### Image show
```
import numpy as np
from PIL import Image

image = Image.open("lena.png")
np_array = np.array(image)

pil_image=Image.fromarray(np_array)
pil_image.show()
```

<img src="https://github.com/Hyeseong0317/Visualizationtool/blob/main/images/lena.PNG" width="20%">

```
import numpy as np 
from PIL import Image 

array = np.random.randint(255, size=(400, 400),dtype=np.uint8)
image = Image.fromarray(array)
image.show() 
```

<img src="https://github.com/Hyeseong0317/Visualizationtool/blob/main/images/noise.PNG" width="20%">

#### Image L mode, P mode

L mode -> gray scale image

P mode -> If you have a P mode image, that means it is palettised. That means there is a palette with up to 256 different colours in it, and instead of storing 3 bytes for R, G and B for each pixel, you store 1 byte which is the index into the palette.

RGB mode -> ex) img = Image.fromarray(img.astype('uint8'), mode='RGB') # value 0~256 for each channel

[What is the difference between images in 'P' and 'L' mode in PIL?](https://stackoverflow.com/questions/52307290/what-is-the-difference-between-images-in-p-and-l-mode-in-pil)

<img src="https://github.com/Hyeseong0317/Visualizationtool/blob/main/images/imageLmodePmode.PNG" width="60%">
