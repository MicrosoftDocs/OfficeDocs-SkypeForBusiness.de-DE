---
title: Migrieren von Lync Raum System Geräte zu Microsoft-Teams Räume
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Lesen Sie in diesem Thema erfahren, wie Lync Raum System Geräte zur Verwendung der Microsoft-Teams Chatrooms Software zu migrieren.
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219395"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrieren von Lync Raum System (LRS) Geräte zu Microsoft-Teams Räume

Lync Raum System (LRS) Geräte mit Skype Raum System Version 1 (SRS v1) Software [Ablauf des Supports auf 9 Oktober 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)erreicht hat. Dies bedeutet, dass Skype Raum Systeme v1 Software nicht mehr Produktupdates oder Hotfixes mehr Informationen erhalten. Kunden mit Lync Raum System im Geräte-Skype Raum Systemsoftware v1, sollten ihre Geräte auf Microsoft Teams Räume zu aktualisieren.

Microsoft-Teams Chatrooms Software arbeitet mit Microsoft-Teams, zusätzlich zu Skype für Business Server und Online-Dienste für Besprechungen und Aufrufen von auf allen Microsoft-Teams Chatrooms an unterstützten Geräten.

Ihre vorhandenen Geräte **können** weiterhin funktionsfähig, nach dem Ende des Skype Raum Systemsoftware v1 unterstützen. Jedoch, wenn Sie diese Software ein Fehlers Software besucht, das Microsoft ein Update freigeben benötigt, wird es nicht unterstützt. SRS v1 verwendet TLS 1.0 / 1.1 die von Microsoft in Zukunft veraltet sein wird. Erfahren Sie mehr über die [Vorbereitung auf das Verwerfen der TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Microsoft-Teams Rooms ist das Hinzufügen von Unterstützung für TLS 1.2 und weiterhin ältere 31 Oktober 2018 arbeiten. Skype für Unternehmen in der lokalen Kunden, bis Microsoft Teams Chatrooms Unterstützung für TLS 1.2 unabhängig von der allgemeinen Richtlinien für das Verwerfen der TLS 1.0/1.1 ankündigt nicht in TLS 1.0/1.1 deaktiviert werden sollte.

## <a name="which-devices-are-affected"></a>Welche Geräte betroffen sind?

Hier wird die Liste der Geräte, die von dieser Änderung betroffen sind:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Intelligente Raum-Systeme](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Upgrade-Optionen

Es gibt mehrere Optionen für das Aktualisieren von Lync Raum Systeme auf die nächste Generation der Microsoft-Teams Chatrooms.

### <a name="crestron-hardware-trade-in-program"></a>Crestron Hardware Rückkauf Programm

Crestron wird ein Upgrade der [Crestron SR-System](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) oder einer gleichwertigen für alle nicht-Crestron Lync Raum System Kunden (z. B. Smart oder Polycom LRS) bereitstellen. Finden Sie unter Details dieses Programms [hier](https://support.crestron.com/app/answers/answer_view/a_id/1000220) oder <!-- For details, -->[e-Mail](mailto:lrsupgrade@crestron.com) Crestron LRS-Unterstützung.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 Upgrade auf Microsoft Teams Räume

Bestehende Crestron RL2 (auch als Crestron RL200 bezeichnet) Kunden können ein Upgrade Kit zum Aktualisieren des aktuellen RL2 RL3 Verwendung erwerben eine minimale Kosten pro Gerät. Finden Sie unter Details dieses Programms [hier](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Intelligente Raum Systeme aktualisieren

Intelligente LRS Kunden, ausreichend Abstand zu platzieren Crestron Hardware Rückkauf Programm ist EFFIZIENT auch auf die Bereitstellung einer Lösung für das upgrade auf Microsoft Teams Chatrooms funktionsfähig. Dieses Update wird durch SMART Technologies Inc. an Kunden unter Produktsupport bereitgestellt. Finden Sie weitere Informationen zu diesem [hier](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Was sollten Sie tun?

Es wird empfohlen, dass Sie Lync Raum System Geräte zu Microsoft-Teams Räumen vor TLS 1.0/1.1 das Verwerfen von oben erwähnten Upgradeoptionen aktualisieren möchten. Darüber hinaus sollten Sie Austauschen von vorhandenen Geräten mit neuer Geräte für Microsoft-Teams Chatrooms zertifiziert. Einzelheiten finden Sie unter [Raum Geräte](https://aka.ms/roomdevices) und auch sehen Sie unter [Microsoft Teams Chatrooms Requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Touch und Whiteboard-Funktionalität ist noch nicht in Microsoft Teams Chatrooms unterstützt. Unterstützung von Touch und Whiteboard ist derzeit für Microsoft-Teams Chatrooms geplant und 2019 hinzugefügt werden.

> [!NOTE]
> Microsoft-Teams Chatrooms Software unterstützt das Protokoll TLS 1.2 ab 14 Dezember 2018 mit app-Version 4.0.64.0. Für lokale Kunden erfordert Aktivieren der Kommunikation über TLS 1.2 für Microsoft-Teams Chatrooms Skype für Business Server 2015 das kumulative Update 9 (CU9) oder Skype für Business Server 2019 Kumulatives Update 1 (CU1). Die Änderung sollte keine Auswirkung auf Skype für Business Online-Kunden wie Client geändert und rückwärtsblättern werden kompatibel.
