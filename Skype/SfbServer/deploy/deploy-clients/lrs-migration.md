---
title: Migrieren von Lync Raum System Geräte zu Skype Raum System, Version 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Lesen Sie in diesem Thema erfahren, wie Lync Raum Systemkomponenten Verwendung die Systemsoftware Skype Raum v2 migrieren.
ms.openlocfilehash: b2d748a37e7e060e19d0708b6979f9254af13682
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772903"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Migrieren von Lync Raum System (LRS) Geräte zu Skype Raum System v2 
Lync Raum System (LRS) Geräte mit Skype Raum System Version 1 (SRS v1) Software [Ablauf des Supports auf 9 Oktober 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)erreicht hat. Dies bedeutet, dass Skype Raum Systeme v1 Software nicht mehr Produktupdates oder Hotfixes mehr Informationen erhalten. Kunden mit Lync Raum System im Geräte-Skype Raum Systemsoftware v1, sollten ihre Geräte auf Skype Raum System, Version 2 (SRS v2) zu aktualisieren.

Skype Raum System Version 2 (SRS v2) Software arbeitet mit Microsoft-Teams, zusätzlich zu Skype Business Server und Online-Dienste für Besprechungen und Aufrufen von auf allen Geräten von SRS v2 unterstützt.

Ihre vorhandenen Geräte **können** weiterhin funktionsfähig, nach dem Ende des Skype Raum Systemsoftware v1 unterstützen. Jedoch, wenn Sie diese Software ein Fehlers Software besucht, das Microsoft ein Update freigeben benötigt, wird es nicht unterstützt. SRS v1 verwendet TLS 1.0 / 1.1 die von Microsoft in Zukunft veraltet sein wird. Erfahren Sie mehr über die [Vorbereitung auf das Verwerfen der TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Skype Raum System V2 ist das Hinzufügen von Unterstützung für TLS 1.2 und weiterhin ältere 31 Oktober 2018 arbeiten. Skype für Unternehmen für lokale Kunden sollten nicht TLS 1.0/1.1 deaktivieren, unabhängig von der allgemeinen Richtlinien für das Verwerfen der TLS 1.0/1.1 Skype Raum System V2 Annouces für TLS 1.2 nicht unterstützt.

## <a name="which-devices-are-affected"></a>Welche Geräte betroffen sind?
Hier wird die Liste der Geräte, die von dieser Änderung betroffen sind:
- [Intelligente Raum-Systeme](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- Crestron RL

## <a name="upgrade-options"></a>Upgrade-Optionen
Es gibt mehrere Optionen für das Upgrade von Lync Raum Systeme auf die nächste Generation von Skype Raum Systeme (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Crestron Hardware Rückkauf Programm
Crestron wird ein Upgrade der [Crestron SR-System](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) oder einer gleichwertigen für alle nicht-Crestron Lync Raum System Kunden bereitstellen. Finden Sie unter Details dieses Programms [hier](https://support.crestron.com/app/answers/answer_view/a_id/1000220) oder <!-- For details, --> [e-Mail](mailto:lrsupgrade@crestron.com) Crestron LRS Support.  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a>Crestron RL2 Upgrade auf SRS V2
Bestehende Crestron RL2 (auch als Crestron RL200 bezeichnet) Kunden können ein Upgrade Kit zum Aktualisieren des aktuellen RL2 RL3 Verwendung erwerben eine minimale Kosten pro Gerät. Finden Sie unter Details dieses Programms [hier](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT). 


### <a name="smart-room-systems-upgrade"></a>Intelligente Raum Systeme aktualisieren 
SMART LRS Kunden, ausreichend Abstand zu platzieren Crestron Hardware Rückkauf Programm arbeiten Microsoft und EFFIZIENT auch auf die Bereitstellung einer Lösung für das upgrade auf Skype Raum System v2. Dieses Update wird von SMART Technologies Inc. bereitgestellt werden Finden Sie weitere Informationen zu diesem [hier](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a>Was sollten Sie tun?
Es wird empfohlen, dass Sie Lync Raum Systemkomponenten Skype Raum Systemen V2 vor TLS 1.0/1.1 das Verwerfen von oben erwähnten Upgradeoptionen aktualisieren möchten. Darüber hinaus können Sie auch bedenken, Austauschen von vorhandenen Geräten mit neuer für SRS v2 zertifizierte Geräte. Einzelheiten finden Sie unter [Raum Geräte](https://aka.ms/roomdevices) und auch betrachten Sie [Skype Raum Systemen v2 Anforderungen](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Fingereingabe und Whiteboard-Funktionalität ist in Skype Raum System v2 noch nicht unterstützt. Unterstützung von Touch und Whiteboard ist noch nicht verarbeiteten für Skype Raum System v2 und H1 CY2019 hinzugefügt werden.

> [!NOTE]
> Skype Raum System V2 Software unterstützt derzeit nicht 1.2 TLS-Protokoll. Unterstützung für TLS 1.2 ist, die bearbeitet und wird ausgeführt werden, bevor das Verwerfen der TLS 1.0/1.1. Kunden Upgradging SRS v2 wird Auswirkung von TLS 1.0/1.1 das verwerfen auf Raum-Geräten mit dem neuesten Version von SRS v2 app nicht angezeigt. Skype für Unternehmen für lokale Kunden sollten nicht TLS 1.0/1.1 deaktivieren, Skype Raum System V2 Annouces für TLS 1.2 nicht unterstützt. 
