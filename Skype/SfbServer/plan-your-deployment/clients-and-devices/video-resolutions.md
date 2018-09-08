---
title: Skype für Business Client Auflösung
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Zusammenfassung: Überprüfen der Clientanforderungen für video beim Planen von Skype für Business Server.'
ms.openlocfilehash: 0150acf98a2d5219975cf33c573f31f755db62f0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886143"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype für Business Client Auflösung
 
**Zusammenfassung:** Überprüfen der Clientanforderungen für video beim Planen von Skype für Business Server.
  
Dieser Artikel beschreibt die Unterstützung der Videohardware für Skype für Business-Videoanrufe und beschreibt, wie zu erwartenden Videoqualität für verschiedene Computer, Tablet- und Konfigurationen des mobilen Geräts zu ermitteln. 
  
IT-Experten werden diese Informationen bei der Bewertung der Eignung der Laptops bereits in Verwendung in ihrer Organisation oder für die Verwendung zu berücksichtigenden hilfreich. Sie können auch den [Lösungskatalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog) Informationen über spezifische Geräte suchen.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows-Desktop, Mac und Tablet-video-Anforderungen und Funktionen

Skype für Unternehmen verwendet Hardwarebeschleunigung für video codieren und Decodieren basierend auf dem Standard h. 264/MPEG-4 Teil 10 Erweiterte Videocodierung. Dadurch können Computer mit niedrigeren CPU-Takt Geschwindigkeit zum Codieren und Decodieren einer höheren Auflösung. Die Anforderungen an die Videohardware hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.
  
Außerdem finden Sie unter [Windows- und Mac-hardwareanforderungen](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Anforderungen an die Videohardware

|**Funktion**|**Anforderung**|
|:-----|:-----|
|Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)  <br/> |• Grafikkarte muss DirectX 9.0 unterstützen und muss die Decodierung DXVA2_ModeH264_VLD_NoFGT-Modus und der DirectX 9-API verfügbar machen.  <br/> • Die aktuellste Grafikkartentreiber muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen  <br/> |Folgende hardwarebeschleunigte Videocodierungslösungen von Intel werden unterstützt:  <br/> • Zweiten und dritten Generation Intel HD Graphics 2000, 2500, 3000 und 4000 Chipsätze (oder höher) mit integrierter Hardware-videocodierung. Die Installation des Intel HD Graphics-Treibers 15.28.9.2884 oder des aktuellsten Treibers, der Folgendes enthält, ist erforderlich:  <br/> • Grafiktreiber 9.17.10.2884 oder der aktuellste Treiber  <br/> • Hardware Media Foundation (HMFT) Version 3.12.10.31 oder das neueste HMFT umwandeln  <br/> Folgende hardwarebeschleunigte Videocodierungslösungen von AMD werden unterstützt:  <br/> • AMD Video Codec Engine, verfügbar in mehreren separaten Grafikkarten und in integrierten beschleunigt Verarbeitungseinheiten der AMD-Serie eine schnellere Prozessoren. Der AMD Video Codec Engine-Treiber 9.12.0.0 oder höher muss installiert sein.  <br/> |
|Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen  <br/> |USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.  <br/> **Hinweis:** Skype für Unternehmen unterstützt UVC 1,5 Kameras mit Windows 8 oder Windows 8.1, die Unterstützung für UVC 1,5 enthält. Da Windows 7 keine Unterstützung für UVC 1,5 einschließt, behandelt Skype für Unternehmen UVC 1,5 Kameras als regulären Kameras mit keine Hardware Codierung unterstützt. <br/> |
   
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
|424 x 240  <br/> |424 x 240 (640 x 360 bei 15 fps für Szenarien, bei denen nur empfangen wird)  <br/> |1 Kern und VideoEncodeScore ≥ 4,0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore ≥ 7,3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |-  <br/> |
   
**Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080  <br/> |1 Kern und VideoEncodeScore ≥ 3,0  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |2 Kerne und VideoEncodeScore ≥ 4,5  <br/> |
|960 x 540  <br/> |1920 x 1080  <br/> |2 Kerne und VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore ≥ 6,7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |4 Kerne und VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Die maximale Codierungsfähigkeit für einen Computer ohne hardwarebeschleunigten Codierer kann daher nur unter Windows 8 oder Windows 8.1 erreicht werden, wo der maximale WinSAT-Wert bei 9,9 liegt. 
  
**Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer**

|**Mögliche Codiererauflösung**|**Mögliche Decodiererauflösung**|**Anforderung**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |Alle Intel HD Graphics-Modelle der 2. und 3. Generation  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Videofunktionen für mobile Geräte

In der folgenden Tabelle werden die maximale Auflösung verfügbar auf unterstützten mobilen Geräten beschrieben. Weitere Informationen zur Unterstützung von mobilen Geräten, [mobilen Client Featurevergleich für Skype für Unternehmen](mobile-feature-comparison.md).
  
|**Funktion**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Maximale Auflösung der H.264-Codierung  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad mini 1 und höher  <br/> 720p: iPad Air/iPad mini 2/iPad Pro und höher  <br/> |Bis zu VGA je nach Gerätemodell  <br/> |
|Maximale Auflösung der H.264-Decodierung  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S und höher  <br/> |VGA: iPad 2 und höher/iPad mini 1 und höher  <br/> 720p: iPad Air/iPad mini 2/iPad Pro und höher  <br/> |Bis zu VGA je nach Gerätemodell  <br/> |
   

