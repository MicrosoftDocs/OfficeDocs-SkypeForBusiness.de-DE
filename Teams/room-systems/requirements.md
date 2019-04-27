---
title: Microsoft-Teams Chatrooms Anforderungen
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: In diesem Artikel werden die Anforderungen für die Unterstützung von Microsoft-Teams Chatrooms zusammengefasst.
ms.openlocfilehash: c7923948dcfc989375c7fb5de30ff6c52b54d487
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362808"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft-Teams Chatrooms Anforderungen

In diesem Artikel werden die Anforderungen für die Unterstützung von Microsoft-Teams Chatrooms zusammengefasst. 

Die Bereitstellung planungslösung Kontenerstellung gemäß der Beschreibung unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md) und Einrichten von einem Meeting-Konsole wie beschrieben unter [Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md). 

Sie müssen auch auf verweisen:

- [Lizenzierung des Skype for Business-Add-Ons](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Optionen, die basierend auf Ihrem Plan zu lizenzieren: Microsoft-Teams Räume](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft-Teams Chatrooms ist für die Verwendung mit Microsoft-Teams, Skype für Business Server 2019, Skype für Business Server 2015 oder Skype für Business Online vorgesehen. <br><br>Frühere Plattformen wie Lync Server 2013 sind nicht entwickelt Microsoft Teams Chatrooms erwartet.

> [!NOTE]
> Wenn Sie einen Exchange-Server auf Prem verwenden, ist Microsoft Teams Chatrooms die Verwendung von Exchange Server 2013 SP1 oder höher erforderlich.

## <a name="hardware-requirements"></a>Hardwareanforderungen

Microsoft-Teams Chatrooms können anderen Raum Größen über Zubehör je nach Audio- und Videodaten Peripheriegeräte skaliert. Die in diesem Artikel aufgeführten Hardware unterstützt Skype und Teams Besprechung Modi.  Audio und video Peripheriegeräte Verbinden mit Microsoft-Teams Räume über ein USB- oder HDMI Verbindung auf das docking-Gerät. Sie müssen außerdem:

- Eine 32GB oder größeren USB-Laufwerk als startbare Windows-Installationsmedium konfigurieren Sie für Windows 10 Enterprise. 

- Einer der folgenden Tablets oder Konsolen:

**Unterstützte tablets**

|Tablet|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |Core i5  |16GB oder 8GB |128GB und mehr  |
|Surface Pro (5. Gen)  |Core i5  |8GB oder 4GB  |128GB und mehr  |
|Surface Pro 4          |Core i5  |8GB oder 4GB  |128GB und mehr  |

> [!NOTE]
> Core M3-Prozessoren werden nicht unterstützt.

**Unterstützte Konsolen**

|Konsole|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |8GB  |128GB  |  
|[HP Elite Segments zur Erfüllung G2 Räume](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5  |8GB  |128GB  |  

- Eine der folgenden docking Station Optionen auf einen Tablet zur Besprechung sichere Raum Tabelle. 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR Datenreihe](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**Certified-Firmware-Versionen für USB-audio und video Peripheriegeräte**

|Microsoft-Teams Chatrooms Peripheriegeräte|Zertifizierung für Microsoft-Teams Chatrooms Firmwareversion|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Video - 1.0.156  <br/> |
|[Logitech ConferenceCam verbinden](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech Gruppe](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
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

- Kabelverbindung Gigabit im Raum. Ethernet-Kabel entsprechender Länge.

- Bis zu zwei 1080p zeigt mit HDMI Verbindungen. HDMI-Kabel entsprechender Länge.

    > [!NOTE]
    > Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist. Dieses Feature wird nicht auf allen TVs unterstützt. 

> [!NOTE]
> Microsoft-Teams Chatrooms wird Tastatur nicht verwendet werden. Der Administrator sollte verwenden Sie bei Bedarf die Bildschirmtastatur. USB-Tastatur oder Maus ist erforderlich, wenn das Gerät Microsoft Teams Chatrooms imaging. 

In den folgenden Tabellen enthalten Empfehlungen für Peripheriegeräte basierend auf Raumgröße:

**Microsoft-Teams, Räume Certified Audio Peripheriegeräte**

|Raum-Typ|Anzahl der Personen|Empfohlene maximale Abstand zwischen Mikrofon Person sprechen|Gerät nach maximale Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10' x 9'  <br/> |2 bis 4  <br/> |1,5 m  <br/> |Logitech verbinden  <br/> |Die Geräte Logitech verbinden enthalten eine Kamera müssen sie am Anfang des Raums (nicht Mitte der Tabelle) zum Erfassen von lokalen Besprechungsteilnehmer positioniert werden.  <br/> |
|**klein** <br/> 16' x 16'  <br/> |4 bis 6  <br/> |2,0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |Lautstärke kann für größere Räume beschränkt werden.  <br/> |
|**Mittel** <br/> 18' x 20'  <br/> |6 bis 12  <br/> |2,4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Gruppe  <br/> Polycom Trio  <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 MS  <br/> |Die Logitech MeetUp enthält eine Kamera, damit es am Anfang der Raum (nicht Mitte der Tabelle zum Erfassen von lokalen Besprechungsteilnehmer) positioniert werden muss.  <br/> Im Allgemeinen können Chatrooms mit Tabellen lange rechteckigen oder u-Form von zusätzlichen Satelliten Mikrofone profitieren.  <br/> SP 220 MS muss in zusammengeschlossen Konfiguration verwendet werden.  <br/> |
|**Große** <br/> 15' x 32'  <br/> |12-16  <br/> |3m  <br/> Dieser Abstand gilt auch für den Bereich jedes zusätzliche Satelliten Mikrofon an das betreffende Audiogerät angeschlossen.  <br/> |Logitech Gruppe + Satelliten Mikrofone  <br/> Polycom Trio + Satelliten Mikrofone  <br/> Polycom CX5100 + Satelliten Mikrofone  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 MS + Satelliten Mikrofone  <br/> |Alle Audiogeräte, die in dieser Zeile Satelliten-Mikrofon Supportoptionen aufgelistet.  <br/> CX5100 umfasst eine integrierte 360-Grad-Kamera, damit das Gerät in der Mitte der Tabelle positioniert werden kann.  <br/> SP 220 MS muss in zusammengeschlossen Konfiguration verwendet werden.  <br/> |

**Microsoft-Teams, Räume Certified Video Peripheriegeräte**

|Raum-Typ|Anzahl der Personen|Gerät nach optimale Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10' x 9'  <br/> |2 bis 4  <br/> |Logitech verbinden  <br/> Logitech MeetUp  <br/> Polycom CX5100  <br/> ||
|**klein** <br/> 16' x 16'  <br/> |4 bis 6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech PTZ Pro häufig gebündelt mit Logitech Gruppe  <br/> |
|**Mittel** <br/> 18' x 20'  <br/> |6 bis 12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**Große** <br/> 15' x 32'  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||

 > [!NOTE]
 > Am Anfang Raum Auflösung sollte nicht mehr als 1920x1080p festgelegt werden.

## <a name="required-software-downloads"></a>Erforderliche Software-downloads

Um Ihr eigenes Bild Microsoft Teams Chatrooms erstellen, befolgen Sie die Anweisungen unter [Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md). Diese Anleitung führt Sie durch alle erforderliche Software für den Installationsvorgang herunterladen. 

> [!NOTE]
> IT-Spezialisten benötigen Zugriff auf Windows 10 Enterprise ISO-Dateien über ihren Volumenlizenzvertrag.

Darüber hinaus möchten Sie höchstwahrscheinlich eine Kopie der [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), die Sie zum Bereitstellen von Microsoft-Teams Chatrooms Konten verwenden können.

## <a name="see-also"></a>Siehe auch

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)

[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)

[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

[Lizenzierung des Skype for Business-Add-Ons](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
