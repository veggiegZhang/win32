---
Description: 'The digital zoom ratio when the image was shot.'
ms.assetid: '1164e2c9-0864-4520-a3be-0c29a5b70ba4'
title: 'System.Photo.DigitalZoom'
---

# System.Photo.DigitalZoom

The digital zoom ratio when the image was shot. Read from the camera in the file's Exchangeable Image File (EXIF) information. This property is calculated from [System.Photo.DigitalZoomNumerator](shell.props_System_Photo_DigitalZoomNumerator) and [System.Photo.DigitalZoomDenominator](shell.props_System_Photo_DigitalZoomDenominator). If the numerator of the recorded value is 0, a digital zoom was not used.

## Windows 10, version 1703, Windows 10, version 1607, Windows 10, version 1511, Windows 10, version 1507, Windows 8.1, Windows 8, Windows 7, Windows Vista

```
propertyDescription
   name = System.Photo.DigitalZoom
   shellPKey = PKEY_Photo_DigitalZoom
   formatID = F85BF840-A925-4BC2-B0C4-8E36B598679E
   propID = 100
   SearchInfo
      InInvertedIndex = false
      IsColumn = true
   typeInfo
      type = Double
      IsInnate = true
```

## Remarks

PKEY values are defined in Propkey.h.

## Related topics

<dl> <dt>

[Exchangeable Image File Format for Digital Still Cameras: Exif Version 2.2](http://www.exif.org/Exif2-2.PDF)
</dt> <dt>

[propertyDescription](shell.propdesc_schema_propertyDescription)
</dt> <dt>

[searchInfo](shell.propdesc_schema_searchInfo)
</dt> <dt>

[labelInfo](shell.propdesc_schema_labelInfo)
</dt> <dt>

[typeInfo](shell.propdesc_schema_typeInfo)
</dt> <dt>

[displayInfo](shell.propdesc_schema_displayInfo)
</dt> <dt>

[stringFormat](shell.propdesc_schema_stringFormat)
</dt> <dt>

[booleanFormat](shell.propdesc_schema_booleanFormat)
</dt> <dt>

[numberFormat](shell.propdesc_schema_numberFormat)
</dt> <dt>

[dateTimeFormat](shell.propdesc_schema_dateTimeFormat)
</dt> <dt>

[enumeratedList](shell.propdesc_schema_enumeratedList)
</dt> <dt>

[drawControl](shell.propdesc_schema_drawControl)
</dt> <dt>

[editControl](shell.propdesc_schema_editControl)
</dt> <dt>

[filterControl](shell.propdesc_schema_filterControl)
</dt> <dt>

[queryControl](shell.propdesc_schema_queryControl)
</dt> </dl>

 

 


