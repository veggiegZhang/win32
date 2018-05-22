---
Description: 'This topic describes how to create a bitmap decoder by using a stream.'
ms.assetid: '982d2110-ff2f-43e0-a931-cb2b8146ad0a'
title: How to Create a Decoder Using a Stream
---

# How to Create a Decoder Using a Stream

This topic describes how to create a bitmap decoder by using a stream.

To create a bitmap decoder by using a stream

1.  Load an image file into a stream. In this example, a stream is created for an application resource.

    In the application resource definition (.rc) file, define the resource. The following example defines an `Image` resource named `IDR_SAMPLE_IMAGE`.

    ```C++
    IDR_SAMPLE_IMAGE IMAGE "turtle.jpg"
    ```

    

    The resource will be added to the application's resources when the application is built.

2.  Load the resource from the application.

    ```C++
    HRESULT hr = S_OK;

    // WIC interface pointers.
    IWICStream *pIWICStream = NULL;
    IWICBitmapDecoder *pIDecoder = NULL;
    IWICBitmapFrameDecode *pIDecoderFrame = NULL;

    // Resource management.
    HRSRC imageResHandle = NULL;
    HGLOBAL imageResDataHandle = NULL;
    void *pImageFile = NULL;
    DWORD imageFileSize = 0;

    // Locate the resource in the application's executable.
    imageResHandle = FindResource(
       NULL,             // This component.
       L"SampleImage",   // Resource name.
       L"Image");        // Resource type.

    hr = (imageResHandle ? S_OK : E_FAIL);

    // Load the resource to the HGLOBAL.
    if (SUCCEEDED(hr)){
       imageResDataHandle = LoadResource(NULL, imageResHandle);
       hr = (imageResDataHandle ? S_OK : E_FAIL);
    }
    
    ```

    

3.  Lock the resource and get the size.

    ```C++
    // Lock the resource to retrieve memory pointer.
    if (SUCCEEDED(hr)){
       pImageFile = LockResource(imageResDataHandle);
       hr = (pImageFile ? S_OK : E_FAIL);
    }

    // Calculate the size.
    if (SUCCEEDED(hr)){
       imageFileSize = SizeofResource(NULL, imageResHandle);
       hr = (imageFileSize ? S_OK : E_FAIL);
    }
    
    ```

    

4.  Create an [**IWICImagingFactory**](-wic-codec-iwicimagingfactory.md) to create Windows Imaging Component (WIC) objects.

    ```C++
    // Create WIC factory
    hr = CoCreateInstance(
        CLSID_WICImagingFactory,
        NULL,
        CLSCTX_INPROC_SERVER,
        IID_PPV_ARGS(&amp;m_pIWICFactory)
        );
    ```

    

5.  Use the [**CreateStream**](-wic-codec-iwicimagingfactory-createstream.md) method to create an [**IWICStream**](-wic-codec-iwicstream.md) object and initialize it by using the image memory pointer.

    ```C++
    // Create a WIC stream to map onto the memory.
    if (SUCCEEDED(hr)){
       hr = m_pIWICFactory->CreateStream(&amp;pIWICStream);
    }

    // Initialize the stream with the memory pointer and size.
    if (SUCCEEDED(hr)){
       hr = pIWICStream->InitializeFromMemory(
             reinterpret_cast<BYTE*>(pImageFile),
             imageFileSize);
    }
    ```

    

6.  Create an [**IWICBitmapDecoder**](-wic-codec-iwicbitmapdecoder.md) from the new stream object using the [**CreateDecoderFromStream**](-wic-codec-iwicimagingfactory-createdecoderfromstream.md) method.

    ```C++
    // Create a decoder for the stream.
    if (SUCCEEDED(hr)){
       hr = m_pIWICFactory->CreateDecoderFromStream(
          pIWICStream,                   // The stream to use to create the decoder
          NULL,                          // Do not prefer a particular vendor
          WICDecodeMetadataCacheOnLoad,  // Cache metadata when needed
          &amp;pIDecoder);                   // Pointer to the decoder
    }
    ```

    

7.  Get the first [**IWICBitmapFrameDecode**](-wic-codec-iwicbitmapframedecode.md) of the image.

    ```C++
    // Retrieve the first bitmap frame.
    if (SUCCEEDED(hr))
    {
       hr = pIDecoder->GetFrame(0, &amp;pIDecoderFrame);
    }
    ```

    

    The JPEG file format only supports a single frame. Because the file in this example is a JPEG file, the first frame (`0`) is used. For image formats that have multiple frames, see [How to Retrieve the Frames of an Image](-wic-bitmapsources-howto-retrieveimageframes.md) for accessing each frame of the image.

8.  Process the image frame. For additional information about [**IWICBitmapSource**](-wic-codec-iwicbitmapsource.md) objects, see the [Bitmap Sources Overview](-wic-bitmapsources.md).

## See Also

[Programming Guide](-wic-programming-guide.md)


[Reference](-wic-codec-reference.md)


[Samples](-wic-samples.md)


 

 


