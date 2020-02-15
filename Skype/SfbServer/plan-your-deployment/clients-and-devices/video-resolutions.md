---
title: Skype for Business-Client-Videoauflösungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Zusammenfassung: Überprüfen der Client Video Anforderungen bei der Planung für Skype for Business Server.'
ms.openlocfilehash: 126c19d817a2cd656b7d581e0d467db80e4969e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027976"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business-Client-Videoauflösungen
 
**Zusammenfassung:** Überprüfen Sie die Client-Video Anforderungen, während Sie Skype for Business Server planen.
  
In diesem Artikel wird die Videohardware Unterstützung für Skype for Business Videoanrufe beschrieben, und es wird beschrieben, wie Sie die erwartete Videoqualität für verschiedene Computer-, Tablet-und Mobile Gerätekonfigurationen bestimmen. 
  
IT-Experten finden diese Informationen hilfreich bei der Bewertung der Eignung von Laptops, die bereits in Ihrer Organisation verwendet werden, oder unter Berücksichtigung der Verwendung. Sie können auch im [Lösungskatalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog) nach Informationen zu bestimmten Geräten suchen.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows-Desktop, Mac und Tablet-Video Anforderungen und-Funktionen

Skype for Business verwendet Hardwarebeschleunigung für Videocodierung und-Decodierung basierend auf dem Standard H. 264/MPEG-4 Part 10 Advanced Video Coding. Auf diese Weise können Computer mit niedrigeren CPU-Taktfrequenzen codieren und Videos mit höherer Auflösung decodieren. Die Videohardware-Anforderungen hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.
  
Siehe auch [Windows-und Mac-Hardwareanforderungen](https://products.office.com/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Hardwareanforderungen für Video

|**Feature**|**Anforderung**|
|:-----|:-----|
|Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)  <br/> |• Grafikkarte muss DirectX 9,0 unterstützen und muss den DXVA2_ModeH264_VLD_NoFGT Decodierungs Modus und die DirectX 9-API verfügbar machen.  <br/> • Der neueste Grafikkartentreiber muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen  <br/> |Die folgenden Intel hardwarebeschleunigten Video Codierungs Lösungen werden unterstützt:  <br/> • Intel HD graphics 2000, 2500, 3000 und 4000 Chipsätze der zweiten und dritten Generation (oder höhere Versionen) mit integrierter Hardware-Video Encoder. Die Installation des Intel HD-Grafiktreibers 15.28.9.2884 oder des neuesten Treibers, der Folgendes enthält, ist erforderlich:  <br/> • Anzeigetreiber 9.17.10.2884 oder der neueste Treiber  <br/> • Hardware Media Foundation Transform (HMFT) Version 3.12.10.31 oder die neueste HMFT  <br/> Die folgenden AMD-hardwarebeschleunigten Video Codierungs Lösungen werden unterstützt:  <br/> • AMD Video Codec Engine, die in mehreren diskreten Grafikkarten und in integrierten beschleunigten Verarbeitungseinheiten von AMD A-Series Accelerated Processors verfügbar ist. Der AMD Video Codec Engine Driver 9.12.0.0 oder höher muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen  <br/> |USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.  <br/> **Hinweis:** Skype for Business unterstützt UVC 1,5-Kameras mit Windows 8 oder Windows 8.1, einschließlich Unterstützung für UVC 1,5. Da Windows 7 keine Unterstützung für UVC 1,5 enthält, behandelt Skype for Business UVC 1,5-Kameras als normale Kameras ohne Unterstützung für Hardware Codierung. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Bestimmen der H. 264-Videocodierung und-Decodierungsfunktionen

In der Regel werden die maximalen Codierungs- und Decodierungsmöglichkeiten einer konkreten Computerkonfiguration durch vier Hauptfaktoren bestimmt:
  
- Unterstützung einer hardwarebeschleunigten Decodierung mittels DXVA
    
- Unterstützung einer hardwarebeschleunigten Codierung
    
- Anzahl der physischen Kerne
    
- Windows Experience Index (WEI)
    
Das Windows System Assessment Tool (WinSAT) ermittelt den WEI-Wert. Wenn Sie WinSAT ausführen, generiert das Tool auf dem Computer im Verzeichnis %windir%\Performance\WinSAT\DataStore das XML-Dokument "Formal.Assessment". Diese XML-Datei enthält die beiden folgenden Bewertungen, die für die Ermittlung der Codierungs- und Decodierungsmöglichkeiten ausgesprochen wichtig sind:
  
- Der Wert "VideoEncodeScore" gibt die softwarebasierte Viedeocodierungsfähigkeit des Computers an.
    
- Der Wert "GraphicsScore" gibt die hardwarebeschleunigte Codierungsfähigkeit des Computers an.
    
Die folgenden drei Tabellen erläutern die maximale Codierungs- und Decodierungsfähigkeiten verschiedener PC-Typen in Abhängigkeit der unterstützten Hardwarebeschleunigung. Für Auflösungen von 640 x 360 und darüber beträgt die maximal unterstützte Framerate 30 Frames pro Sekunde (fps). Für Auflösungen unter 640 x 360 beträgt die maximal unterstützte Framerate 15 fps.
  
**Computer ohne DXVA und ohne hardwarebeschleunigten Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424 x 240 (640 x 360 bei 15 fps für Szenarien bei denen nur empfangen wird)  <br/> |1 Kern und VideoEncodeScore ≥ 4,0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1280X720  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|1280X720  <br/> |1280X720  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1280X720  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Nicht zutreffend  <br/> |
   
**Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920x1080  <br/> |1 Kern und VideoEncodeScore = 3,0  <br/> |
|640 x 360  <br/> |1920x1080  <br/> |2 Kerne und VideoEncodeScore = 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 Kerne und VideoEncodeScore = 6,0  <br/> |
|1280X720  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore = 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore = 8,2  <br/> |
   
> [!NOTE]
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Die Codierungsfunktion für einen Computer ohne einen hardwarebeschleunigten Encoder kann daher nur auf Windows 8 oder Windows 8.1 erreicht werden, wobei die maximale WinSAT-Punktzahl 9,9 beträgt. 
  
**Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|1280X720  <br/> |1920x1080  <br/> |Alle Intel HD Graphics-Modelle der 2. und 3. Generation  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Videofunktionen für mobile Geräte

In der folgenden Tabelle werden die maximalen Videoauflösungen beschrieben, die auf unterstützten mobilen Geräten verfügbar sind. Weitere Informationen zur Unterstützung mobiler Geräte finden Sie unter [Mobile Client Feature Comparison for Skype for Business](mobile-feature-comparison.md).
  
|**Feature**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Maximale Auflösung der H. 264-Codierung  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad Mini 1 und höher  <br/> 720p: iPad Air/iPad Mini 2/iPad pro und höher  <br/> |Je nach Gerätemodell bis zu VGA  <br/> |
|H. 264-Decodierungs maximale Auflösung  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad Mini 1 und höher  <br/> 720p: iPad Air/iPad Mini 2/iPad pro und höher  <br/> |Je nach Gerätemodell bis zu VGA  <br/> |
   

