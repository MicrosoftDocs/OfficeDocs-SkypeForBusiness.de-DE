---
title: Anforderungen für Microsoft Teams-Räume
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: In diesem Artikel werden die Voraussetzungen für die Unterstützung von Microsoft Teams-Räumen zusammengefasst.
ms.openlocfilehash: ee2f60fbf638613eb296bc24b1bebd1dfc66553a
ms.sourcegitcommit: 26b3d786da07fde20878b0f4a1656070fe01d918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "36645270"
---
# <a name="microsoft-teams-rooms-requirements"></a>Anforderungen für Microsoft Teams-Räume

In diesem Artikel werden die Voraussetzungen für die Unterstützung von Microsoft Teams-Räumen zusammengefasst.

Ihre Bereitstellung umfasst die Kontoerstellung, wie unter [Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md) und Einrichten von Besprechungskonsolen beschrieben, wie unter [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)beschrieben.

Weitere Informationen finden Sie unter:

- [Lizenzierung des Skype for Business-Add-Ons](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Lizenzoptionen auf Grundlage Ihres Plans: Microsoft Teams-Chatrooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams Rooms ist für die Verwendung mit Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015 oder Skype for Business Online vorgesehen.
>
> Frühere Plattformen wie lync Server 2013 funktionieren nicht mit Microsoft Teams-Räumen.
>
> Wenn Sie über einen auf-Prem Exchange-Server verfügen, erfordert Microsoft Teams rooms die Verwendung von Exchange Server 2013 SP1 oder höher.

## <a name="hardware-requirements"></a>Hardwareanforderungen

Microsoft Teams-Räume werden durch Zubehör je nach Audio-und Videoperipherie auf unterschiedliche Raumgrößen skaliert. Die in diesem Artikel aufgelistete Hardware unterstützt Skype-und Teams-Besprechungs Modi. Audio-und Video-Peripheriegeräte werden über einen USB-oder HDMI-Anschluss auf dem Docking-Gerät mit Microsoft Teams-Räumen verbunden. Sie benötigen außerdem:

- Ein 32 GB-oder größeres USB-Laufwerk, das Sie als startfähige Windows-Installationsmedien für Windows 10 Enterprise konfigurieren.

- Eine der folgenden Tablets oder Konsolen:

**Unterstützte Tablets**

|Tablet|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|Surface pro 6| Core i5 |16 GB oder 8 GB |128 GB oder mehr |
|Surface pro (fünfte Generation) |Core i5 |8 GB oder 4 GB |128 GB oder mehr |
|Surface pro 4 |Core i5 |8 GB oder 4 GB |128 GB oder mehr |

- Eine der folgenden Optionen für die Docking-Station, um ein Tablet auf die Besprechungsraum Tabelle zu sichern.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR-Serie](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

**Andere unterstützte Microsoft Teams rooms-Konsolen**

|Konsole|Prozessor|RAM|Festplatte|
|:-----|:-----|:-----|:-----|
|[Crestron Flex UC-M130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
|[Crestron Flex UC-B130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
|[Crestron Flex UC-B140-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
|[Crestron Flex UC-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Core i7|8 GB |128 GB |
[Crestron Flex UC-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
|[Crestron Flex UC-C160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
|[HP Elite-Slice für Besprechungsräume G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
|[HP Elite Slice G2-Audio bereit mit Microsoft Teams-Räumen](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
|[Logitech Tap](https://www.logitech.com/en-us/product/microsoft-rooms)|Core i5|8 GB |128 GB |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
|[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
|||||

> [!NOTE]
> Core M3-Prozessoren werden nicht unterstützt.

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>**Zertifizierte Firmware-Versionen für USB-Audio-und Video-Peripheriegeräte**

Diese Geräte sind unter [aka.ms/teamsdevices](https://aka.ms/teamsdevices)erhältlich.

|Microsoft Teams rooms-Peripheriegeräte|Für Microsoft Teams-Chatrooms zertifizierte Firmware-Version| Kamera unterstützt die Verwendung von Kamera Inhalten|
|:--- |:--- | :--- |
|[Crestron-Kuschel-IQ](https://www.crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | &#x2714; |
|[Logitech Brio](https://www.logitech.com/en-us/product/brio)   |V240| &#x2714; |
|[Logitech 930E](http://www.logitech.com/en-us/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech-Rallye](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Meetup zu Logitech](http://www.logitech.com/en-us/product/meetup-conferencecam)   |Audio – 1.0.172 <br/> Video – 1.0.156  |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech-Gruppe](http://www.logitech.com/en-us/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2)   |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 ms](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser sp20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100C   |
| |  | |

- **USB-Extender**:

  - USB-Anschlüsse an Tablet-Docks sind USB-3,0-kompatibel. Sie können einen USB 2. x-Extender verwenden, der Sie jedoch auf USB 2. x-Geschwindigkeiten am anderen Ende beschränkt, und dies wird für USB 3,0-Peripheriegeräte nicht empfohlen.

  - Ein Extender muss USB 2,0 oder neuere Spezifikationen erfüllen.

  - Tablet-Docks unterstützen mindestens zwei Phasen der externen USB-Hub-Erweiterung. Wenn Sie mehr als zwei USB-Hubs in Serie anschließen müssen, erkundigen Sie sich beim Hersteller des Docks, ob dies unterstützt wird.

- Kabelgebundene GbE-Verbindung im Raum. Ethernet-Kabel mit geeigneter Länge.

- Bis zu 2 1080-p-Displays mit HDMI-Anschlüssen. HDMI-Kabel mit geeigneter Länge.

> [!NOTE]
> Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist. Dieses Feature wird nicht auf allen TVs unterstützt.

> [!NOTE]
> In Microsoft Teams-Räumen wird keine Tastatur verwendet. Falls erforderlich, sollte der Administrator die Bildschirmtastatur verwenden. Beim Imaging des Microsoft Teams rooms-Geräts wird eine USB-Tastatur oder-Maus benötigt.

Die folgenden Tabellen enthalten Empfehlungen für Peripheriegeräte auf der Grundlage der Raumgröße:

**Microsoft Teams rooms Certified Audio-Peripheriegeräte**

|Zimmerkategorie|Anzahl der Personen|Empfohlene maximale Entfernung vom Mikrofon zum Lautsprecher|Gerät nach maximaler Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10 ' x 9 '   |2 – 4  |1,5 m  |Logitech Connect  |Die Logitech Connect-Geräte umfassen eine Kamera, damit Sie an der Vorderseite des Raums (nicht in der Mitte der Tabelle) positioniert werden muss, um lokale Besprechungsteilnehmer zu erfassen.  |
|**Kleine** <br/> 16 ' x 16 '  |4 – 6  |2,0 m  |Jabra 510 <br/> Sennheiser sp20  |Die Lautstärke der Wiedergabe kann für größere Räume limitiert sein.  |
|**Mittel** <br/> 18 cm x 20 cm  |6 – 12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Meetup zu Logitech <br/> Logitech-Gruppe <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 ms <br/> Yamaha YVC-1000ms  |Das Logitech-Meetup enthält eine Kamera, damit es an der Vorderseite des Chatrooms positioniert werden muss (nicht in der Mitte der Tabelle, um lokale Besprechungsteilnehmer zu erfassen). <br/> Im Allgemeinen können Räume mit langen rechteckigen oder u-förmigen Tischen von Satelliten Mikrofonen profitieren. <br/> SP 220 ms muss in der Konfiguration der Daisy-Chain-Konfiguration verwendet werden.  |
|**Große** <br/> 15 ' x 32 '  |12 – 16  |3 m <br/> Dieser Abstand bezieht sich auch auf den Bereich, der von jedem Satelliten Mikrofon, das mit dem Audiogerät verbunden ist, abgedeckt wird.  |Logitech Group + Satelliten Mikrofone <br/> Polycom Trio + Satelliten Mikrofone <br/> Polycom CX5100 + Satelliten Mikrofone <br/> Sennheiser SP 220 ms <br/> Yamaha YVC-1000ms + Satelliten Mikrofone  |Alle in dieser Zeile aufgeführten Audiogeräte unterstützen Satelliten Mikrofon-Optionen. <br/> CX5100 enthält eine integrierte 360-Grad-Kamera, damit das Gerät in der Mitte des Tischs positioniert werden kann. <br/> SP 220 ms muss in der Konfiguration der Daisy-Chain-Konfiguration verwendet werden.  |

**Microsoft Teams rooms Certified-Video-Peripheriegeräte**

|Zimmerkategorie|Anzahl der Personen|Gerät nach optimaler Raumgröße|Kommentare|
|:-----|:-----|:-----|:-----|
|**Fokus** <br/> 10 ' x 9 '  |2 – 4  |Logitech Connect <br/> Meetup zu Logitech <br/> Polycom CX5100  ||
|**Kleine** <br/> 16 ' x 16 '  |4 – 6  |Logitech C930e <br/> Meetup zu Logitech <br/> Logitech Brio <br/> Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ pro, häufig gebündelt mit der Logitech Group  |
|**Mittel** <br/> 18 cm x 20 cm  |6 – 12  |Meetup zu Logitech <br/> Logitech Brio <br/> Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Große** <br/> 15 ' x 32 '  |12 – 16  |Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > Die Bildschirmauflösung für die Vorderseite sollte auf "nicht größer als 1920x1080p" festgesetzt werden.

## <a name="required-software-downloads"></a>Erforderliche Software Downloads

Wenn Sie Ihr eigenes Microsoft Teams rooms-Bild erstellen möchten, folgen Sie den Anweisungen unter [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md). Diese Anleitung führt Sie durch den Download der erforderlichen Software für den Installationsprozess.

> [!NOTE]
> IT-Experten benötigen Zugriff auf Windows 10 Enterprise ISO-Dateien über deren Volumenlizenz Vertrag.

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) ist ein optionaler Download, mit dem Sie Microsoft Teams rooms-Konten bereitstellen können.

## <a name="see-also"></a>Siehe auch

[Alle Bundles durchsuchen](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Planen von Microsoft Teams-Räumen](skype-room-systems-v2-0.md)

[Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)

[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

[Lizenzierung des Skype for Business-Add-Ons](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
