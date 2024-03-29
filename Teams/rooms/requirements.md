---
title: Voraussetzungen für Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Erfahren Sie mehr über die Anforderungen für die Unterstützung von Microsoft Teams-Räume, einschließlich der Auswahl des entsprechenden Geräts, Mikrofons, Lautsprechern, Kameras und Displays.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd4376a8d34be2c0184844b015531c7b496c94c4
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706682"
---
# <a name="microsoft-teams-rooms-requirements"></a>Voraussetzungen für Microsoft Teams-Räume

Microsoft Teams-Räume auf unterschiedliche Raumgrößen skalieren. Teams-Räume je nach Größe und Nutzung des Raums eine Vielzahl zertifizierter Audio- und Videoperipheriegeräte verwenden. Durch Die Auswahl des richtigen Kerngeräts und der richtigen Konsole in Kombination mit Mikrofonen, Lautsprechern, Kameras und Bildschirmen, die für den Raum geeignet sind, können Sie Microsoft Teams-Räume in Räumen jeder Größe bereitstellen, von kleinen Gewandräumen bis hin zu großen Konferenzräumen und Sitzungsräumen.  Der vollständige Satz aller verfügbaren zertifizierten Audio- und Videoperipheriegeräte, die zur Konfiguration Ihres Raumes verwendet werden können, ist im [Geräte-Showcase](https://products.office.com/microsoft-teams/across-devices) verfügbar.

Dieser Artikel fasst die Gerätebereitstellungs- und Konfigurationsvoraussetzungen für die Unterstützung von Microsoft Teams-Räume zusammen.

Ihre Bereitstellung umfasst die Erstellung und Einrichtung von Ressourcenkonten Teams-Räume wie unter ["Bereitstellen Microsoft Teams-Räume](rooms-deploy.md)" beschrieben.

Siehe:

- [Lizenzoptionen basierend auf Ihrem Plan: Microsoft Teams-Räume](rooms-licensing.md)

> [!NOTE]
> Microsoft Teams-Räume sich bei Microsoft Teams, Skype for Business Server 2019 oder Skype for Business Server 2015 anmelden und an Besprechungen teilnehmen, die von einem dieser Dienste gehostet werden.
>
> Frühere Plattformen wie Lync Server 2013 werden von Microsoft Teams-Räume nicht unterstützt. Microsoft Teams-Räume wird in Microsoft 365- oder Office 365, die von 21Vianet- oder DoD-Umgebungen betrieben werden, nicht unterstützt.
>
> Wenn Sie über einen lokalen Exchange-Server verfügen, ist die Verwendung von Exchange Server 2013 SP1 oder höher für Microsoft Teams-Räume erforderlich.

## <a name="hardware-requirements"></a>Hardwareanforderungen
Eine Hardwarebereitstellung umfasst eine Auswahl eines Microsoft Teams-Räume-Systems in Kombination mit zertifizierten Audio- und Videoperipheriegeräten sowie eine Verkabelungslösung zur Integration dieser Geräte.  Diese Optionen werden hier beschrieben.

**Unterstützte Microsoft Teams-Räume-Systeme**

Alle aktuellen Microsoft Teams-Räume Geräte und Bundles sind im [Teams-Räume Produkt showcase](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=) verfügbar.

  |Konsole|Prozessor|RAM|Festplattenspeicher|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T mit Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T mit Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T mit Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Crestron Flex UC-C140-T mit Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-M150-T mit Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T mit Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T mit Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T mit Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Crestron Flex UC-MMX30-T mit UC Presentation Transmitter (UC-PR) und ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-BX30-T mit UC Presentation Transmitter (UC-PR) und ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-CX100-T mit UC Presentation Transmitter (UC-PR) und ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-B30-T mit ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-C100-T mit ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M50-T mit ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M70-T mit ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX50-T mit ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX70-T mit ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5/i7|8 GB |128 GB |
   |Crestron FLEX UC-B30-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-Bx30-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MM30-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MMX30-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M50-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX50-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M70-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX70-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-C100-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-CX100-T mit Dell OPTIPLEX|Core i5|8 GB|128 GB|
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 mit Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 GB |128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio bereit für Microsoft Teams-Räume](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP Slice Partner Ready with Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  |[HP Presence Small Space Solution mit Microsoft Teams-Räume](https://www.hp.com/us-en/solutions/presence.html)|Core i5/i7|8 GB/16 GB|256 GB|
  |[HP Presence Small Space Solution Plus AI Camera mit Microsoft Teams-Räume](https://www.hp.com/us-en/solutions/presence.html)|Core i5/i7|8 GB/16 GB|256 GB|
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |Lenovo ThinkSmart Core Kit |Core i5|8 GB|128 GB|
  |[Logitech Tap mit Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Logitech Tap und Intel Tiger Canyon NUC PC |Core i5|8 GB|128 GB|
  |Logitech TAP Console mit Lenovo Core Compute |Core i5|8 GB|128 GB|
  |[Logitech Tap und Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T mit Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Poly G40-T Kit mit Poly Studio USB, mit Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g40) |Core i5| 8 GB | 128 GB|
  |[Poly G85-T Kit mit Poly Eagle Eye Director II, mit Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g85) |Core i5| 8 GB | 128 GB|
  |Poly GC8 Konsole mit Lenovo Thinksmart Core|Core i5|8 GB|128 GB|
  |Poly GC8 Console mit Dell Optiplex 7080|Core i5|8 GB|128 GB|
  |[Yealink MVC300 mit Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 mit Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 mit Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 mit Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  |Yealink MVC340|Core i5|8 GB | 128 GB|
  
  
> [!NOTE]
> - Core M3-Prozessoren werden nicht unterstützt.
> - Sie benötigen ein USB-Laufwerk mit 32 GB oder mehr, das als bootfähiges Windows-Installationsmedium für Windows 10 Enterprise konfiguriert ist.

**Unterstützte Surface Pro-Tablets für Dock-Style-Systeme**

  |Tablet|Prozessor|RAM|Festplattenspeicher|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB oder 8 GB |128 GB oder mehr |
  |Surface Pro </br>(fünfte Generation) |Core i5 |8 GB oder 4 GB |128 GB oder mehr |
  |Surface Pro 4 |Core i5 |8 GB oder 4 GB |128 GB oder mehr |

- Surface Pro Geräte benötigen eine der folgenden Dockingstationsoptionen:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Zertifizierte Firmwareversionen für USB-Audio- und-Videoperipheriegeräte

Diese Geräte sind in der [Produktvitrine Raumsystem-Zubehör](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) und [https://office.com/teamsdevices](https://office.com/teamsdevices)erhältlich.

|Peripheriegeräte für Microsoft Teams-Räume|Zertifizierte Firmwareversion | Unterstützt Inhaltskamera|Intelligente Kamera|
|:--- |:--- | :--- |:--- |
|[Aver VC520 Pro Kamera + Freisprecheinrichtung](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VC520 PRO2-Konferenzsystem](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Aver VB342+ Kamera-Soundleiste](https://www.averusa.com/products/conference-camera/vb342plus) | Soundbar: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 550](https://www.averusa.com/products/conference-camera/cam550) |0.0.8000.51 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Aver VB130 Kamera-Soundleiste](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Audiocodes RXVCAM50L](https://www.audiocodes.com/solutions-products/products/room-experience-rx-suite/rxvcam50lm-video-camera) |1.0.5 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based Konferenzhub mit Deckenmikrofon](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Biamp Devio SCR-20TX Web-Based Conferencing Hub mit Tabletop-Mikrofon](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|HP Presence See Camera| 1.0.23.0 |
|[Knuddeliges Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ Kamera](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Huddly L1](https://www.huddly.com/conference-cameras/l1/) | 1.2.9 |
|Huddly L1 Kamera mit [Crestron UC-C100-T MTR](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T) Kit | Huddly L1 Kamera: 1.2.1 </br> Crestron UC-C100-T mit ASUS Tek Computer INC 9934 compute 1.0.20.246 oder höher |
|Huddly L1 Kamera mit [Crestron UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W Kit | Huddly L1 Kamera: 1.2.9 </br> Crestron UC-CX100-T mit ASUS Tek Computer INC 9934 1.00.20.246 oder höher |
|Huddly L1 Kamera mit Crestron UC-M70-T MTR Kit | Huddly L1 Kamera: 1.2.1 </br> Crestron UC-M70-T mit ASUS Tek Computer INC 9934 compute 1.0.20.246 oder höher |
|Huddly L1 Kamera mit Crestron UC-MX70-T MTR Kit | Huddly L1 Kamera: 1.2.1 </br> Crestron UC-MX70-T mit ASUS Tek Computer INC 9934 compute 1.0.20.246 oder höher |
|[Jabra Panacast3 Kamera](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 Video Bar](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|4.0.15| &#x2714; | &#x2714;|
|[Lenovo ThinkSmart Cam Kamera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rallye](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Meetup von Logitech](https://www.logitech.com/product/meetup-conferencecam)   |Audio – 1.0.172 <br/> Video – 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Group von Logitech](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech-Schreiber](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube Camera](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.md)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://support.polycom.com/content/dam/polycom-support/products/peripherals/eagle-eye-director-ii/user/en/eagleeye-director-ii-admin-guide-2-0.pdf#:~:text=The%20Polycom%C2%AE%20EagleEye%E2%84%A2%20Director%20II%20camera%20is%20a,while%20the%20other%20camera%20tracks%20the%20second%20speaker.)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Poly Studio P15 Videoleiste](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Poly Studio E70 Kamera](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[Poly Studio R30](https://www.poly.com/us/en/products/video-conferencing/studio/studio-r30)|2.0.0.001096|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 Extension Mics](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Freisprecheinrichtung — 4.6.55 <br/> Extension Mic — 0.2.314|
|[EPOS – Aufnahme 5 erweitern](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Extron DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT, DMP 128 Plus C AT, DMP 128 Plus C V, DMP 128 Plus C, DMP 128 Plus AT, DMP 128 Plus, DMP 128 FlexPlus C AT, DMP 128 FlexPlus C V AT)](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Extron DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT, DMP 64 Plus C AT, DMP 64 Plus C V, DMP 64 Plus C)](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Yamaha ADECIA Deckenlösung](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Yamaha ADECIA Tabletop-Lösung](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|E1.2.0 für Tischmikrofon, D1.2.0 für Prozessor (Beide Inhalte wie V1.5.1)|
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC34 All-in-One-Videoleiste](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Yealink UVC40 All-in-One-Videoleiste](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Tabelle Array Mic ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Shure MXA 910 mit Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) +</br>[MXN5W-C Deckenlautsprecher](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA310 Table Array mic: 4.1.41 </br> MXN5W-C Lautsprecher: 1.0.4 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) + </br>[Shure MXA 920 mit Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[MXN5W-C Deckenlautsprecher](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.7.7 </br> MXA920 Ceiling Array mic: 1.1.56 </br> MXN5W-C Lautsprecher: 1.5.6 |
|ANIUSB + </br> [Shure MXA 920 mit Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[MXN5-Deckenlautsprecher](https://www.shure.com/en-US/products/loudspeakers/mxn5)| ANIUSB: 4.4.7 </br> MXA920: 1.1.56 </br> MXN5: 1.5.6|
|[Shure MXA 710 2ft Tisch Linear Array Mikrofon](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[MXN5-C-Deckenlautsprecher](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> MXN5-C-Lautsprecher: 1.1.1 |
|[Shure MXA 710 4ft Wall Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[MXN5-C-Deckenlautsprecher](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> MXN5-C-Lautsprecher: 1.1.1 |
|[Shure MXA 910 mit Intellimix Ceiling Array Microphone](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Raumsoftware](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Raum software: 3.0.4.14 </br> Shure MXA 910 mit Intellimix Ceiling Array Mikrofon: 4.4.11 </br> Shure MXN5-C Lautsprecher: 1.2.1 </br> Crestron UC-C100-T mit ASUS Tek Computer INC 9934 Compute | 
|[Shure MXA 910 mit Intellimix Ceiling Array Microphone](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Raumsoftware](https://www.shure.com/products/software/intellimix_room) +</br>Lenovo ThinkSmart Core | Shure Intellimix Raum software: 3.2.0.52 </br> Shure MXA 910 mit Intellimix Ceiling Array Mikrofon: 4.4.11 </br> Shure MXN5-C Lautsprecher: 1.2.1 |
|[Shure MXA920XX-R Round Ceiling Array Microphone](https://www.shure.com/en-US/products/microphones/mxa920?variant=MXA920AL-R) + </br> [P300-Prozessor](https://www.shure.com/en-US/products/mixers/p300?variant=P300-IMX) + </br> [MXN5-Lautsprecher](https://www.shure.com/en-US/products/loudspeakers/mxn5) | MXA920XX-R: 1.1.56 </br> P300-Prozessor: 4.7.7 </br> MXN5-Lautsprecher: 1.5.6 |
|[Shure MXA 910 mit Intellimix Ceiling Array Microphone](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Raumsoftware](https://www.shure.com/products/software/intellimix_room) +</br>Dell Optiplex 7080 | Shure Intellimix Raum software: 3.2.0.52 </br> Shure MXA 910 mit Intellimix Ceiling Array Mikrofon: 4.4.11 </br> Shure MXN5-C Lautsprecher: 1.2.1 |
|[Sennheiser TeamConnect Intelligent Speaker/TC ISP (T-Rock)](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br>[Sennheiser TeamConnect 2-Deckenmikrofon](https://sennheiser.com/tcc2)+ &Dagger;</br>[Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15 </br> TCC2: 1.3.3 </br>EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+</br>[Biamp Parlé TCM-XA Deckenmikrofon](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Biamp Desono C-IC6 Deckenlautsprecher](https://www.biamp.com/products/tesira-speakers)| Audio FW-Version: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Ex-UBT]() |Audio FW-Version: 3.15|
|[Biamp Devio SCX Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Biamp Parlé TCM-XA Deckenmikrofon](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Biamp Desono C-IC6 Deckenlautsprecher](https://www.biamp.com/products/tesira-speakers) | Devio SCX Serie: 4.2.5 |
|[Biamp Tesira Forte X Series Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Biamp Parlé TCM-XA Deckenmikrofon](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Biamp Desono C-IC6 Deckenlautsprecher](https://www.biamp.com/products/tesira-speakers) | Tesira FORTE X Serie: 4.2.5 |
|[ControlSpace EX-440C DSP von Bose + </br>P2600A AmpLink-Verstärker von Bose +</br> TCC2-Deckenmikrofon von Sennheiser + </br> EdgeMax EM180-Deckenlautsprecher von Bose ](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Verstärker + Sennheiser TCC2 Deckenmikrofon + </br> Bose DesignMax DM2C-P Deckenlautsprecher](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Verstärker +</br> [Sennheiser TCC2 Deckenmikrofon](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Deckenlautsprecher](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Verstärker+</br> [Sennheiser TCC2 Deckenmikrofon](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Deckenlautsprecher EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/), [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/), [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) oder [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Sennheiser TCC2 Deckenmikrofon](https://en-us.sennheiser.com/tcc2) + </br> QSC-Verstärker ([SPA-Serie](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) oder [CX-Q-Serie](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [Lautsprecher der QSC AcousticDesign-Serie](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> QSC IP Kamera ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/), [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) optional + </br> [QSC Q-SYS E/A-USB-Brücke](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) optional | QSC Q-SYS Core, PTZ-IP Kamera und I/O USB Brücke: QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Deckenmikrofon: TCC2 - 1.5.1, Dante 1.2.0 </br> QSC-Verstärker: NV </br> QSC AcousticDesign Serie Lautsprecher: N/A | 


&Dagger;-Kunden können entweder die Dante-Benutzeroberfläche oder den von Biamp/Sennheiser empfohlenen Netzwerkschalter für dieses Paket auswählen.

#### <a name="usb-extenders"></a>USB-Extender

- USB-Anschlüsse auf Tablet-Docks sind USB 3.0-kompatibel. Sie können einen USB 2.x-Extender verwenden, aber Sie sind auf USB 2.x-Geschwindigkeiten am ende beschränkt. Extender werden für USB 3.0-Peripheriegeräte nicht empfohlen.
- Ein Extender muss USB 2.0 oder neuere Spezifikationen erfüllen.
  - Tablet-Docks unterstützen mindestens zwei Phasen der externen USB-Hub-Erweiterung. Wenn Sie mehr als zwei USB-Hubs in Reihe anschließen, erkundigen Sie sich beim Hersteller der Docks, ob diese eine Reihenschaltung unterstützen.
  - Kabelgebundene GbE-Verbindung in den Raum. Ethernet-Kabel mit geeigneter Länge.
  - Bis zu zwei 1080p-Displays mit HDMI-Anschlüssen. HDMI-Kabel mit geeigneter Länge.

> [!NOTE]
> Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist. Dieses Feature wird nicht auf allen TVs unterstützt.
>
> Microsoft Teams-Räume verwendet keine Tastatur. Bei Bedarf sollte der Administrator die Bildschirmtastatur verwenden. Eine USB-Tastatur oder -Maus ist erforderlich, wenn Sie Bilder des Geräts für Microsoft Teams-Räume verarbeiten.

In den folgenden Tabellen finden Sie Empfehlungen für Peripheriegeräte basierend auf der Raumgröße:

**Für Microsoft Teams-Räume zertifizierte Audio-Peripheriegeräte**

|Raumtyp|Anzahl der Personen|Empfohlene maximale Entfernung von Mikrofon zu Lautsprecher|
|:-----|:-----|:-----|
|**Fokus** <br/> 3,01 m x 2,74 m   |2–4  |1,5 m  |
|**Klein** <br/> 4,88 m x 4,88 m  |4–6  |2,0 m  |
|**Mittel** <br/> 5,49 m x 6,10 m  |6–12  |2,4 m  |
|**Groß** <br/> 4,57 m x 9,75 m  |12–16  |3 m <br/> Diese Entfernung gilt auch für den Bereich, der von jedem angeschlossenen Satellitenmikrofon abgedeckt wird.  |

**Für Microsoft Teams-Räume zertifizierte Video-Peripheriegeräte**

|Raumtyp|Anzahl der Personen|
|:-----|:-----|
|**Fokus** <br/> 3,01 m x 2,74 m  |2–4  |
|**Klein** <br/> 4,88 m x 4,88 m  |4–6  |
|**Mittel** <br/> 5,49 m x 6,10 m  |6–12  |
|**Groß** <br/> 4,57 m x 9,75 m  |12–16  |

 > [!NOTE]
 > Die Auflösung für die Anzeige vorn im Raum sollte auf nicht mehr als 1920 x 1080 p eingestellt werden.


## <a name="see-also"></a>Siehe auch

[Alle Pakete auflisten](https://products.office.com/microsoft-teams/across-devices/devices)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)
