---
title: Skype for Business-Clientvideoauflösungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Überprüfen Sie die Clientvideoanforderungen bei der Planung für Skype for Business Server.'
ms.openlocfilehash: 895345ddee8ac17338977bdb161172bf975de343d7d86be1a053ccac8f4f0e7f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293932"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business-Clientvideoauflösungen
 
**Zusammenfassung:** Überprüfen Sie die Videoanforderungen des Clients, während Sie Skype for Business Server planen.
  
Dieser Artikel beschreibt die Videohardwareunterstützung für Skype for Business Videoanrufe und beschreibt, wie Sie die erwartete Videoqualität für verschiedene Konfigurationen von Computern, Tablets und mobilgeräten ermitteln. 
  
IT-Experten werden diese Informationen nützlich finden, um die Eignung von Laptops zu bewerten, die bereits in ihrer Organisation verwendet werden oder für die Verwendung in Betracht gezogen werden. Sie können auch im [Lösungskatalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog) nach Informationen auf bestimmten Geräten suchen.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows Desktop-, Mac- und Tablet-Videoanforderungen und -funktionen

Skype for Business verwendet die Hardwarebeschleunigung für die Videocodierung und -decodierung basierend auf dem Standard H.264/MPEG-4 Part 10 Advanced Video Coding. Auf diese Weise können Computer mit niedrigeren CPU-Taktgeschwindigkeiten Videos mit höherer Auflösung codieren und decodieren. Die Videohardware-Anforderungen hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.
  
Weitere Informationen finden Sie unter [Windows- und Mac-Hardwareanforderungen.](https://products.office.com/office-system-requirements)
  
### <a name="video-hardware-requirements"></a>Anforderungen an die Videohardware

|**Feature**|**Anforderung**|
|:-----|:-----|
|Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)  <br/> |• Grafikkarte muss DirectX 9.0 unterstützen und die DXVA2_ModeH264_VLD_NoFGT Decodierungsmodus und die DirectX 9-API verfügbar machen.  <br/> • Der neueste Grafikkartentreiber muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen  <br/> |Die folgenden hardwarebeschleunigte Videocodierungslösungen von Intel werden unterstützt:  <br/> • Intel HD Graphics 2000-, 2500-, 3000- und 4000-Chipsätze der zweiten und dritten Generation (oder neuere Versionen) mit integrierten Hardware-Video-Encodern. Die Installation des Intel HD Graphics-Treibers 15.28.9.2884 oder des neuesten Treibers, der Folgendes enthält, ist erforderlich:  <br/> • Anzeigetreiber 9.17.10.2884 oder der neueste Treiber  <br/> • Hardware Media Foundation Transform (HMFT) Version 3.12.10.31 oder die neueste HMFT  <br/> Die folgenden hardwarebeschleunigte Videocodierungslösungen für AMD werden unterstützt:  <br/> • AMD Video Codec Engine, das in mehreren separaten Grafikkarten und in integrierten beschleunigten Verarbeitungseinheiten von AMD A-Series Accelerated Processors verfügbar ist. Der AMD Video Codec Engine-Treiber 9.12.0.0 oder höher muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen  <br/> |USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.  <br/> **Hinweis:** Skype for Business unterstützt UVC 1.5-Kameras mit Windows 8 oder Windows 8.1, einschließlich uvc 1.5. Da Windows 7 keine Unterstützung für UVC 1.5 umfasst, behandelt Skype for Business UVC 1.5-Kameras als normale Kameras ohne Hardwarecodierungsunterstützung. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Ermitteln der Funktionen für die H.264-Videocodierung und -Decodierung

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
|640 x 360  <br/> |1280 x 720  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Nicht zutreffend  <br/> |
   
**Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080  <br/> |1 Kern und VideoEncodeScore = 3,0  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |2 Kerne und VideoEncodeScore = 4,5  <br/> |
|960 x 540  <br/> |1920 x 1080  <br/> |2 Kerne und VideoEncodeScore = 6,0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore = 6,7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore = 8,2  <br/> |
   
> [!NOTE]
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Daher kann die Codierungsfunktion für einen Computer ohne hardwarebeschleunigte Encoder nur auf Windows 8 oder Windows 8.1 erreicht werden, wobei die maximale WinSAT-Bewertung 9,9 beträgt. 
  
**Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |Alle Intel HD Graphics-Modelle der 2. und 3. Generation  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Videofunktionen für mobile Geräte

In der folgenden Tabelle werden die maximalen Videoauflösungen beschrieben, die auf unterstützten mobilen Geräten verfügbar sind. For more information about mobile device support, [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md).
  
|**Feature**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Maximale Auflösung der H.264-Codierung  <br/> |Vga  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad Mini 1 und höher  <br/> 720p: iPad Air/iPad Mini 2/iPad Pro und höher  <br/> |Bis zu VGA je nach Gerätemodell  <br/> |
|Maximale Auflösung der H.264-Decodierung  <br/> |Vga  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad Mini 1 und höher  <br/> 720p: iPad Air/iPad Mini 2/iPad Pro und höher  <br/> |Bis zu VGA je nach Gerätemodell  <br/> |
   

