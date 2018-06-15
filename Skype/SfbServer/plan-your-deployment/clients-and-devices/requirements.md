---
title: Anforderungen für Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: In diesem Artikel werden die Anforderungen für die Unterstützung von Skype Raum Systemen v2 zusammengefasst.
ms.openlocfilehash: 1d44178beb69cda78b72bb8d0e599af81be39321
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887877"
---
# <a name="skype-room-systems-v2-requirements"></a>Anforderungen für Skype Room Systems v2
 
In diesem Artikel werden die Anforderungen für die Unterstützung von Skype Raum Systemen v2 zusammengefasst. 
  
Die Bereitstellung planungslösung Kontenerstellung gemäß der Beschreibung unter [Bereitstellen von Skype Raum Systemen v2](../../deploy/deploy-clients/room-systems-v2.md) und Einrichten von einem Meeting-Konsole, wie beschrieben unter [Konfigurieren einer Skype Raum Systemen v2-Konsole](../../deploy/deploy-clients/console.md). Sie müssen auch auf [Skype für Business Add-on Lizenzierung](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)verweisen.
  
## <a name="hardware-requirements"></a>Hardwareanforderungen

Skype-Chatroom-Systemen v2 können anderen Raum Größen über Zubehör je nach Audio- und Videodaten Peripheriegeräte skaliert. Audio und video Peripheriegeräte Verbinden mit Skype Raum Systemen v2 über ein USB- oder HDMI Verbindung auf das docking-Gerät. Sie müssen außerdem:
  
- Eine 32GB oder größeren USB-Laufwerk als startbare Windows-Installationsmedium konfigurieren Sie für Windows 10 Enterprise. 
    
- Einer der folgenden Tablets oder Konsolen:
    
**Unterstützte tablets**
|Tablet|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|Surface Pro 4    |Core i5  |4GB  |128GB  |
|Surface Pro 4    |Core i5  |8GB  |256GB  |    
|Surface Pro (2017)  |Core i5  |4GB  |128GB  |
|Surface Pro (2017)  |Core i5  |8GB  |256GB  |
|Surface Pro (2017)  |Core i7  |8GB  |128GB  |
|Surface Pro (2017)  |Core i7  |16GB  |512GB  |
|Surface Pro (2017) |Core i7  |16GB  |1TB  |
   
> [!NOTE]
> Core M3-Prozessoren werden nicht unterstützt.

**Unterstützte Konsolen**
|Konsole|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|[Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |8GB  |128GB  |  
 <!-- HP dock is still pending  -->  
    
- Eine der folgenden docking Station Optionen auf einen Tablet zur Besprechung sichere Raum Tabelle. 
    
  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)
    
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Polycom MSR Datenreihe](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


 
**Certified-Firmware-Versionen für USB-audio und video Peripheriegeräte**
|**Skype-Chatroom-Systemen v2 Peripheriegeräte**|**Firmwareversion zertifiziert für Skype Raum Systemen v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Video - 1.0.156  <br/> |
|[Logitech ConferenceCam verbinden](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech Gruppe](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Polycom RealPresence Trio](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |
   
- **USB-Extender**:
    
  - USB-Anschlüsse auf Tablet Docking-Stationen sind USB 3.0 kompatibel. Einen USB-2.x Extender können jedoch dadurch so wird Sie auf beschränken USB 2.x kumulativ auf weit Ende und dadurch ist also nicht für USB-3.0 Peripheriegeräte empfohlen.
    
  - Ein Extender muss USB 2.0 oder neuere Spezifikationen erfüllen.
    
  - Tablet Docking-Stationen unterstützt mindestens zwei Stufen der externen USB-Hub-Erweiterung. Wenn müssen eine Verbindung herstellen mit mehr als zwei USB-Hubs in Reihe, müssen Sie die wenden Sie sich beim Hersteller Andocken zu bestätigen, dadurch wird daher unterstützt.
    
- Kabelverbindung Gigabit im Raum. Ethernet-Kabel mit entsprechender Länge.
    
- Bis zu zwei 1080p zeigt mit HDMI Verbindungen. HDMI-Kabel entsprechender Länge.
    
    > [!NOTE]
    > Ein Consumer TV als Front Raum Anzeige Anforderungen für den Support/HDMI das Consumer Electronics Steuerelement (CEC)-Feature aktivieren, damit er automatisch an eine aktive Bildquelle aus dem Standbymodus wechseln kann. Dieses Feature wird auf alle TV-Geräte nicht unterstützt. 
  
> [!NOTE]
> Skype-Chatroom-Systemen v2 wird Tastatur nicht verwendet werden. Bei Bedarf muss der Administrator die Bildschirmtastatur verwenden. USB-Tastatur oder Maus ist erforderlich, wenn das Skype Raum Systemen v2 Gerät imaging. 
  
In den folgenden Tabellen enthalten Empfehlungen für Peripheriegeräte basierend auf Raumgröße:
  
**Skype-Raum Systemen v2 Certified Audio Peripheriegeräte**

|**Raum-Typ**|**Anzahl der Personen**|**Empfohlene maximale Abstand zwischen Mikrofon Person sprechen**|**Gerät nach maximale Raumgröße**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10' x 9'  <br/> |2 bis 4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |Die Geräte Logitech verbinden enthalten eine Kamera müssen sie am Anfang des Raums (nicht Mitte der Tabelle) zum Erfassen von lokalen Besprechungsteilnehmer positioniert werden.  <br/> |
|**Kleine** <br/> 16' x 16'  <br/> |4 bis 6  <br/> |2,0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |Die Wiedergabelautstärke kann für größere Räume begrenzt sein.  <br/> |
|**Mittel** <br/> 18' x 20'  <br/> |6 bis 12  <br/> |2,4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 MS  <br/> |Die Logitech MeetUp enthält eine Kamera, damit es am Anfang der Raum (nicht Mitte der Tabelle zum Erfassen von lokalen Besprechungsteilnehmer) positioniert werden muss.  <br/> Im Allgemeinen können Chatrooms mit Tabellen lange rechteckigen oder u-Form von zusätzlichen Satelliten Mikrofone profitieren.  <br/> SP 220 MS muss in einer Daisy-Chain-Konfiguration verwendet werden.  <br/> |
|**Große** <br/> 15' x 32'  <br/> |12-16  <br/> |3m  <br/> Diese Entfernung gilt auch für den Bereich, der von jedem weiteren Satellitenmikrofon abgedeckt wird, das mit dem entsprechenden Audiogerät verbunden ist.   <br/> |Logitech Gruppe + Satelliten Mikrofone  <br/> Polycom Trio + Satelliten Mikrofone  <br/> Polycom CX5100 + Satelliten Mikrofone  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 MS + Satelliten Mikrofone  <br/> |Alle in dieser Zeile aufgeführten Audiogeräte unterstützen Optionen für Satellitenmikrofone.  <br/> CX5100 umfasst eine integrierte 360-Grad-Kamera, sodass das Gerät in der Tischmitte positioniert werden kann.  <br/> SP 220 MS muss in einer Daisy-Chain-Konfiguration verwendet werden.  <br/> |
   
**Skype-Raum Systemen v2 Certified Video Peripheriegeräte**

|Raumart|Anzahl der Personen|Gerät nach optimale Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10' x 9'  <br/> |2 bis 4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Kleine** <br/> 16' x 16'  <br/> |4 bis 6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro häufig gebündelt mit Logitech Gruppe  <br/> |
|**Mittel** <br/> 18' x 20'  <br/> |6 bis 12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**Große** <br/> 15' x 32'  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
   
 > [!NOTE]
 > Am Anfang Raum Auflösung sollte nicht mehr als 1920x1080p festgelegt werden.

## <a name="required-software-downloads"></a>Erforderliche Softwaredownloads

Sie benötigen ein eigenes Bild Skype Raum Systemen v2 erstellen die folgenden Downloads:
  
- Das [Skype Raum Systemen v2-Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Eine Kopie der 64-Bit-Version von Windows 10 Enterprise Creator Update (englische, Build 1703) zu erhalten. 
    
    > [!NOTE]
    > Die 64-Bit-Version von Windows 10 Enterprise Jahrestag Edition (englische, Version 1607) wird nicht mehr Skype Raum Systemen v2 Version 3.0.12.0 (Update 3) unterstützt. 
  
- Die unterstützten [Surface Pro 4 Treiber](https://go.microsoft.com/fwlink/?linkid=856887) oder [Surface Pro Treiber](https://go.microsoft.com/fwlink/?linkid=856888).
    
Diese Downloads müssen in einer startbare Windows Media-Installationsdatenträger auf eine bestimmte Weise kombiniert werden in [Configure Skype Raum Systemen v2 Konsole](../../deploy/deploy-clients/console.md)beschrieben. 
  
Darüber hinaus sollten Sie wahrscheinlich eine Kopie der [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), häufig zum Bereitstellen von Skype Raum Systemen v2 Konten verwendet.
  
## <a name="see-also"></a>Siehe auch

[Planen von Skype Raum Systemen v2](skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Raum Systemen v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Konfigurieren einer Skype Raum Systemen v2-Konsole](../../deploy/deploy-clients/console.md)
  
[Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Skype für Business Add-on Lizenzierung](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)