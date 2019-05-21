---
title: Videoauflösungen für Skype for Business-Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Zusammenfassung: Überprüfen der Client Video Anforderungen bei der Planung für Skype for Business Server.'
ms.openlocfilehash: 15fd424f7ad2e11d473e49e271c7fbf1db83b45c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277279"
---
# <a name="skype-for-business-client-video-resolutions"></a>Videoauflösungen für Skype for Business-Clients
 
**Zusammenfassung:** Überprüfen Sie die Client Video Anforderungen während der Planung für Skype for Business Server.
  
In diesem Artikel wird die Videohardware Unterstützung für Skype for Business-Videoanrufe beschrieben und es wird beschrieben, wie Sie die erwartete Videoqualität für verschiedene Computer-, Tablet-und Mobile Gerätekonfigurationen ermitteln können. 
  
IT-Experten finden diese Informationen hilfreich bei der Beurteilung der Eignung von Laptops, die bereits in Ihrer Organisation verwendet werden, oder unter Berücksichtigung der Verwendung. Sie können auch den [Lösungskatalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog) nach Informationen zu bestimmten Geräten durchsuchen.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows-Desktop-, Mac-und Tablet-Video Anforderungen und-Funktionen

Skype for Business verwendet die Hardwarebeschleunigung für die Videocodierung und-Decodierung basierend auf dem H. 264/MPEG-4 Part 10 Advanced Video Coding Standard. Auf diese Weise können Computer mit niedrigeren CPU-Taktgeschwindigkeiten Video mit höherer Auflösung codieren und decodieren. Die Anforderungen an die Videohardware hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.
  
Sehen Sie sich auch die [Hardwareanforderungen für Windows und Mac an](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Anforderungen an die Videohardware

|**Funktion**|**Anforderung**|
|:-----|:-----|
|Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)  <br/> |• Grafikkarte muss DirectX 9,0 unterstützen und muss den DXVA2_ModeH264_VLD_NoFGT-Decodierungs Modus und die DirectX 9-API verfügbar machen.  <br/> • Der neueste Grafikkartentreiber muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen  <br/> |Folgende hardwarebeschleunigte Videocodierungslösungen von Intel werden unterstützt:  <br/> • Intel HD graphics 2000, 2500, 3000 und 4000-Chipsätze der zweiten und dritten Generation (oder neueren Versionen) mit integrierten Hardware-Video-Encoder. Die Installation des Intel HD Graphics-Treibers 15.28.9.2884 oder des aktuellsten Treibers, der Folgendes enthält, ist erforderlich:  <br/> • Anzeige des Treibers 9.17.10.2884 oder des neuesten Treibers  <br/> • Hardware Media Foundation Transform (HMFT) Version 3.12.10.31 oder die neueste HMFT  <br/> Folgende hardwarebeschleunigte Videocodierungslösungen von AMD werden unterstützt:  <br/> • AMD Video-Codec-Engine, die in mehreren diskreten Grafikkarten und in integrierten beschleunigten Verarbeitungseinheiten von AMD A-Serie-beschleunigten Prozessoren verfügbar ist. Der AMD Video Codec Engine-Treiber 9.12.0.0 oder höher muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen  <br/> |USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.  <br/> **Hinweis:** Skype for Business unterstützt UVC 1,5-Kameras mit Windows 8 oder Windows 8,1, einschließlich Unterstützung für UVC 1,5. Da Windows 7 keine Unterstützung für UVC 1,5 enthält, behandelt Skype for Business UVC 1,5-Kameras als normale Kameras ohne Unterstützung für Hardware-Codierung. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Ermitteln der Fähigkeiten zur H.264-Videocodierung und -decodierung

In der Regel werden die maximalen Codierungs- und Decodierungsmöglichkeiten einer konkreten Computerkonfiguration durch vier Hauptfaktoren bestimmt:
  
- Unterstützung einer hardwarebeschleunigten Decodierung mittels DXVA
    
- Unterstützung einer hardwarebeschleunigten Codierung
    
- Anzahl der physischen Kerne
    
- Windows Experience Index (WEI)
    
Das Windows System Assessment Tool (WinSAT) ermittelt den WEI-Wert. Wenn Sie WinSAT ausführen, generiert das Tool auf dem Computer im Verzeichnis %windir%\Performance\WinSAT\DataStore das XML-Dokument „Formal.Assessment“. Diese XML-Datei enthält die beiden folgenden Bewertungen, die für die Ermittlung der Codierungs- und Decodierungsmöglichkeiten ausgesprochen wichtig sind:
  
- Der Wert „VideoEncodeScore“ gibt die softwarebasierte Viedeocodierungsfähigkeit des Computers an.
    
- Der Wert „GraphicsScore“ gibt die hardwarebeschleunigte Codierungsfähigkeit des Computers an.
    
Die folgenden drei Tabellen erläutern die maximalen Codierungs- und Decodierungsfähigkeiten verschiedener PC-Typen in Abhängigkeit von der unterstützten Hardwarebeschleunigung. Für Auflösungen von 640 x 360 und darüber beträgt die maximal unterstützte Framerate 30 Frames pro Sekunde (fps). Für Auflösungen unter 640 x 360 beträgt die maximal unterstützte Framerate 15 fps.
  
**Computer ohne DXVA und ohne hardwarebeschleunigten Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424 x 240 (640 x 360 bei 15 fps für Szenarien, bei denen nur empfangen wird)  <br/> |1 Kern und VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |-  <br/> |
   
**Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920x1080  <br/> |1 Kern und VideoEncodeScore ≥ 3,0  <br/> |
|640 x 360  <br/> |1920x1080  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|960 x 540  <br/> |1920x1080  <br/> |2 Kerne und VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 Kerne und VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Die maximale Codierungsfähigkeit für einen Computer ohne hardwarebeschleunigten Codierer kann daher nur unter Windows 8 oder Windows 8.1 erreicht werden, wo der maximale WinSAT-Wert bei 9,9 liegt. 
  
**Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920x1080  <br/> |Alle Intel HD Graphics-Modelle der 2. und 3. Generation  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Videofunktionen für mobile Geräte

In der folgenden Tabelle werden die maximalen Videoauflösungen beschrieben, die auf unterstützten mobilen Geräten verfügbar sind. Weitere Informationen zur Unterstützung mobiler Geräte finden Sie unter [Vergleich der Features für mobile Clients in Skype for Business](mobile-feature-comparison.md).
  
|**Funktion**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Maximale Auflösung der H.264-Codierung  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad mini 1 und höher  <br/> 720p: iPad Air/iPad mini 2/iPad Pro und höher  <br/> |Bis zu VGA je nach Gerätemodell  <br/> |
|Maximale Auflösung der H.264-Decodierung  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad mini 1 und höher  <br/> 720p: iPad Air/iPad mini 2/iPad Pro und höher  <br/> |Bis zu VGA je nach Gerätemodell  <br/> |
   

