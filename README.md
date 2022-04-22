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

#### Image L mode, P mode, RGB mode

[PIL image mode](https://pillow.readthedocs.io/en/stable/handbook/concepts.html#concept-modes)

L mode -> gray scale image

P mode -> If you have a P mode image, that means it is palettised. That means there is a palette with up to 256 different colours in it, and instead of storing 3 bytes for R, G and B for each pixel, you store 1 byte which is the index into the palette.

RGB mode -> ex) img = Image.fromarray(img.astype('uint8'), mode='RGB') # value 0~256 for each channel

[What is the difference between images in 'P' and 'L' mode in PIL?](https://stackoverflow.com/questions/52307290/what-is-the-difference-between-images-in-p-and-l-mode-in-pil)

<img src="https://github.com/Hyeseong0317/Visualizationtool/blob/main/images/imageLmodePmode.PNG" width="60%">

----
### 영상 지식
#### jpeg
JPEG 표준 안에는 많은 선택사항들이 있지만, 그중 대부분은 거의 사용되지 않는다. 아래 설명은 픽셀당 24비트 (빨강, 초록, 파랑 각 8비트씩)의 색상정보를 가진 데이터를 변환하는 일반적인 방법에 대한 간단한 설명이다. 아래 설명한 방식에선 손실 압축 방식을 사용한다.

색공간 변환
우선 각 픽셀의 RGB 데이터를 YCbCr이라는 다른 색공간 데이터로 변환한다. 이 색공간은 NTSC나 PAL 방식의 컬러 텔레비전 전송에 쓰이는 색공간과 유사하다. Y 성분은 픽셀의 루마 정보를 가지고 있으며, Cb와 Cr 성분은 색차 정보(chroma components)를 가지고 있다. 
#### 사람의 눈이 색상 성분보다 휘도 성분에 더 민감하기 때문에 색상 정보를 더 많이 압축하기 위해서 YCbCr 색공간으로 변환한다. 색공간 변환 시 제한된 정밀도 (채널당 8 비트) 때문에 정보가 완전히 보전되지 않는다. 따라서 뒤에서 양자화를 전혀하지 않더라도 원본과 완전히 일치하지 않는다. 즉, JPEG 저장시 화질을 100%으로 하더라도 원본과 차이가 있게 된다.
