---
title: Anforderungen für Microsoft Teams-Räume
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: In diesem Artikel werden die Voraussetzungen für die Unterstützung von Microsoft Teams-Räumen zusammengefasst.
ms.openlocfilehash: 44f077bde6ec767b3897b25bfe8d0cbf05b6ac37
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418217"
---
# <a name="microsoft-teams-rooms-requirements"></a>Anforderungen für Microsoft Teams-Räume

In diesem Artikel werden die Voraussetzungen für die Unterstützung von Microsoft Teams-Räumen zusammengefasst. 

Ihre Bereitstellung umfasst die Kontoerstellung, wie unter [Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md) und Einrichten einer Besprechungskonsole beschrieben wird, wie unter [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)beschrieben. 

Möglicherweise müssen Sie sich auch an folgende Personen wenden:

- [Lizenzierung des Skype for Business-Add-Ons](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Lizenzoptionen auf Grundlage Ihres Plans: Microsoft Teams-Chatrooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams Rooms ist für die Verwendung mit Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015 oder Skype for Business Online vorgesehen. <br><br>Frühere Plattformen wie lync Server 2013 funktionieren nicht mit Microsoft Teams-Räumen.

> [!NOTE]
> Bei Verwendung eines auf-Prem Exchange-Servers erfordert Microsoft Teams rooms die Verwendung von Exchange Server 2013 SP1 oder höher.

## <a name="hardware-requirements"></a>Hardwareanforderungen

Microsoft Teams-Räume können durch Zubehör je nach Audio-und Videoperipherie auf unterschiedliche Raumgrößen skaliert werden. Die in diesem Artikel aufgelistete Hardware unterstützt Skype-und Teams-Besprechungs Modi.  Audio-und Video-Peripheriegeräte werden über einen USB-oder HDMI-Anschluss auf dem Docking-Gerät mit Microsoft Teams-Räumen verbunden. Sie benötigen außerdem:

- Ein 32GB oder ein größeres USB-Laufwerk, das Sie als startfähige Windows-Installationsmedien für Windows 10 Enterprise konfigurieren. 

- Eine der folgenden Tablets oder Konsolen:

**Unterstützte Tablets**

|Tablet|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|Surface pro 6          |Core i5  |16GB oder 8 GB |128 GB oder mehr  |
|Surface pro (fünfte Generation)  |Core i5  |8 GB oder 4 GB  |128 GB oder mehr  |
|Surface pro 4          |Core i5  |8 GB oder 4 GB  |128 GB oder mehr  |

- Eine der folgenden Optionen für die Docking-Station, um ein Tablet auf die Besprechungsraum Tabelle zu sichern. 

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR-Serie](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


**Andere unterstützte Microsoft Teams-Raum Konsolen**

|Konsole|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|[Crestron Flex-M150](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Core i7|8GB |128GB|
|[Crestron Flex UC-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/All-In-One-Meeting-Solutions/Crestron-Mercury-Accessories/CCS-UC-1-T)|Core i7|8GB |128GB |
[Crestron Flex UC-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8GB |128GB|
|[HP Elite-Slice für Besprechungsräume G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5  |8GB  |128GB  | 
|[HP Elite Slice G2-Audio bereit mit Microsoft Teams-Räumen](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8GB |128GB | 
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |8GB  |128GB  |  
|[Logitech Tap + NUC](https://www.logitech.com/en-us/product/tap?crid=1691)|Core i5|8GB |128GB |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8GB|128GB|
|[Logitech Tap Touch-Controller für Video Konferenzräume](https://www.logitech.com/en-us/product/tap) |Core i5  |8GB  |240 GB  |  
|||||

> [!NOTE]
> Core M3-Prozessoren werden nicht unterstützt.

**Zertifizierte Firmware-Versionen für USB-Audio-und Video-Peripheriegeräte**

|Microsoft Teams rooms-Peripheriegeräte|Für Microsoft Teams-Chatrooms zertifizierte Firmware-Version|
|:-----|:-----|
|[Logitech-Rallye](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam) <br/> |1.2.4 |
|[Logitech Brio](https://www.logitech.com/en-us/product/brio) <br/> |V240|
|[Meetup zu Logitech](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio-1.0.172  <br/> Video-1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech-Gruppe](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930E](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html) <br/> |5.7.2.3205|
|[Sennheiser SP 220 ms](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser sp20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100C  <br/> |

- **USB-Extender**:

  - USB-Anschlüsse an Tablet-Docks sind USB-3,0-kompatibel. Sie können einen USB 2. x-Extender verwenden, doch dies wird Sie auf USB 2. x-Geschwindigkeiten am anderen Ende begrenzen, und dies wird für USB 3,0-Peripheriegeräte nicht empfohlen.

  - Ein Extender muss USB 2,0 oder neuere Spezifikationen erfüllen.

  - Tablet-Docks unterstützen mindestens zwei Phasen der externen USB-Hub-Erweiterung. Wenn Sie mehr als zwei USB-Hubs in Serie anschließen müssen, müssen Sie sich beim Hersteller des Docks erkundigen, ob dies unterstützt wird.

- Kabelgebundene GbE-Verbindung im Raum. Ethernet-Kabel mit geeigneter Länge.

- Bis zu zwei 1080p-Displays mit HDMI-Anschlüssen. HDMI-Kabel mit geeigneter Länge.

> [!NOTE]
> Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist. Dieses Feature wird nicht auf allen TVs unterstützt. 

> [!NOTE]
> In Microsoft Teams-Räumen wird keine Tastatur verwendet. Falls erforderlich, sollte der Administrator die Bildschirmtastatur verwenden. Beim Imaging des Microsoft Teams rooms-Geräts wird eine USB-Tastatur oder-Maus benötigt. 

Die folgenden Tabellen enthalten Empfehlungen für Peripheriegeräte auf der Grundlage der Raumgröße:

**Microsoft Teams rooms Certified Audio-Peripheriegeräte**

|Zimmerkategorie|Anzahl der Personen|Empfohlene maximale Entfernung vom Mikrofon zur sprechenden Person|Gerät nach maximaler Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10 ' x 9 '  <br/> |2-4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |Die Logitech Connect-Geräte umfassen eine Kamera, damit Sie an der Vorderseite des Raums (nicht in der Mitte der Tabelle) positioniert werden muss, um lokale Besprechungsteilnehmer zu erfassen.  <br/> |
|**Kleine** <br/> 16 ' x 16 '  <br/> |4-6  <br/> |2,0 m  <br/> |Jabra 510  <br/> Sennheiser sp20  <br/> |Die Lautstärke der Wiedergabe kann für größere Räume limitiert sein.  <br/> |
|**Mittel** <br/> 18 cm x 20 cm  <br/> |6-12  <br/> |2,4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Meetup zu Logitech  <br/> Logitech-Gruppe  <br/> Polycom Trio  <br/> Polycom CX5100  <br/> Sennheiser SP 220 ms  <br/> Yamaha YVC-1000ms  <br/> |Das Logitech-Meetup enthält eine Kamera, damit es an der Vorderseite des Chatrooms positioniert werden muss (nicht in der Mitte der Tabelle, um lokale Besprechungsteilnehmer zu erfassen).  <br/> Im Allgemeinen können Räume mit langen rechteckigen oder u-förmigen Tischen von zusätzlichen Satelliten Mikrofonen profitieren.  <br/> SP 220 ms muss in der Konfiguration der Daisy-Chain-Konfiguration verwendet werden.  <br/> |
|**Große** <br/> 15 ' x 32 '  <br/> |12-16  <br/> |3M  <br/> Dieser Abstand bezieht sich auch auf den Bereich, der von jedem zusätzlichen Satelliten Mikrofon, das mit dem fraglichen Audiogerät verbunden ist, abgedeckt wird.  <br/> |Logitech Group + Satelliten Mikrofone  <br/> Polycom Trio + Satelliten Mikrofone  <br/> Polycom CX5100 + Satelliten Mikrofone  <br/> Sennheiser SP 220 ms  <br/> Yamaha YVC-1000ms + Satelliten Mikrofone  <br/> |Alle in dieser Zeile aufgeführten Audiogeräte unterstützen Satelliten Mikrofon-Optionen.  <br/> CX5100 enthält eine integrierte 360-Grad-Kamera, damit das Gerät in der Mitte des Tischs positioniert werden kann.  <br/> SP 220 ms muss in der Konfiguration der Daisy-Chain-Konfiguration verwendet werden.  <br/> |

**Microsoft Teams rooms Certified-Video-Peripheriegeräte**

|Zimmerkategorie|Anzahl der Personen|Gerät nach optimaler Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10 ' x 9 '  <br/> |2-4  <br/> |Logitech Connect  <br/> Meetup zu Logitech  <br/> Polycom CX5100  <br/> ||
|**Kleine** <br/> 16 ' x 16 '  <br/> |4-6  <br/> |Logitech C930e  <br/> Meetup zu Logitech  <br/> Logitech Brio  <br/> Logitech PTZ pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech PTZ pro, häufig gebündelt mit der Logitech Group  <br/> |
|**Mittel** <br/> 18 cm x 20 cm  <br/> |6-12  <br/> |Meetup zu Logitech  <br/> Logitech Brio  <br/> Logitech PTZ pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**Große** <br/> 15 ' x 32 '  <br/> |12-16  <br/> |Logitech PTZ pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||

 > [!NOTE]
 > Die Bildschirmauflösung für die Vorderseite sollte auf "nicht größer als 1920x1080p" festgesetzt werden.

## <a name="required-software-downloads"></a>Erforderliche Software Downloads

Wenn Sie Ihr eigenes Microsoft Teams rooms-Bild erstellen möchten, folgen Sie den Anweisungen unter [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md). Diese Anleitung führt Sie durch das Herunterladen der erforderlichen Software für den Installationsprozess. 

> [!NOTE]
> IT-Experten benötigen Zugriff auf Windows 10 Enterprise ISO-Dateien über deren Volumenlizenz Vertrag.

Darüber hinaus benötigen Sie wahrscheinlich eine Kopie von [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), die Sie zum Bereitstellen von Microsoft Teams rooms-Konten verwenden können.

## <a name="see-also"></a>Siehe auch
[Alle Bundles durchsuchen](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Planen von Microsoft Teams-Räumen](skype-room-systems-v2-0.md)

[Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)

[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

[Lizenzierung des Skype for Business-Add-Ons](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
