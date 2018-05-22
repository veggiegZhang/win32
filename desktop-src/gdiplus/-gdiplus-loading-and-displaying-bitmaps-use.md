---
Description: 'To display a raster image (bitmap) on the screen, you need an Image object and a Graphics object.'
ms.assetid: '8c1a26d9-b640-4f38-8276-10c4464525f2'
title: Loading and Displaying Bitmaps
---

# Loading and Displaying Bitmaps

To display a raster image (bitmap) on the screen, you need an [**Image**](-gdiplus-class-image-class.md) object and a [**Graphics**](-gdiplus-class-graphics-class.md) object. Pass the name of a file (or a pointer to a stream) to an **Image** constructor. After you have created an **Image** object, pass the address of that **Image** object to the **DrawImage** method of a **Graphics** object.

The following example creates an [**Image**](-gdiplus-class-image-class.md) object from a JPEG file and then draws the image with its upper-left corner at (60, 10):


```
Image image(L"Grapes.jpg");
graphics.DrawImage(&amp;image, 60, 10);
```



The following illustration shows the image drawn at the specified location.

![screen shot of a window that contains an image, with a callout for the origin point ](images/imageposition1.png)

The [**Image**](-gdiplus-class-image-class.md) class provides basic methods for loading and displaying raster images and vector images. The [**Bitmap**](-gdiplus-class-bitmap-class.md) class, which inherits from the **Image** class, provides more specialized methods for loading, displaying, and manipulating raster images. For example, you can construct a **Bitmap** object from an icon handle (HICON).

The following example obtains a handle to an icon and then uses that handle to construct a [**Bitmap**](-gdiplus-class-bitmap-class.md) object. The code displays the icon by passing the address of the **Bitmap** object to the **DrawImage** method of a [**Graphics**](-gdiplus-class-graphics-class.md) object.


```
HICON hIcon = LoadIcon(NULL, IDI_APPLICATION);
Bitmap bitmap(hIcon);
graphics.DrawImage(&amp;bitmap, 10, 10);
```



 

 


