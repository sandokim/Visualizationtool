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

[What is the difference between images in 'P' and 'L' mode in PIL?](https://stackoverflow.com/questions/52307290/what-is-the-difference-between-images-in-p-and-l-mode-in-pil)

<img src="https://github.com/Hyeseong0317/Visualizationtool/blob/main/images/imageLmodePmode.PNG" width="60%">
