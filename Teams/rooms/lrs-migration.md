---
title: Migrieren von Lync Room System-Geräten zu Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: In diesem Thema erfahren Sie, wie Sie Lync Room System-Geräte für die Verwendung der Raumsystemsoftware Microsoft Teams-Räume können.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 98604c36a987dde15633e9d9b1a3a283c0f36fa2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608822"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrieren von Geräten des Lync Room System (LRS) zu Microsoft Teams-Räume

Lync Room System (LRS)-Geräte mit Skype Room System Version 1 (SRS v1)-Software haben das Ende des Supportendes am [9. Oktober 2018 erreicht.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Dies bedeutet, dass keine Produktupdates oder -fixes mehr für die Skype Room Systems v1-Software zur Verfügung gestellt werden. Kunden mit Lync Room System-Geräten und Skype Room System v1-Software empfehlen wir, ihre Geräte auf Microsoft Teams-Räume zu aktualisieren.

Microsoft Teams-Räume Software funktioniert mit Microsoft Teams zusätzlich zu Skype for Business Server- und Onlinediensten für Besprechungen und Anrufe auf allen unterstützten Microsoft Teams-Räume Geräten.

Ihre **vorhandenen Geräte können** auch nach dem Ende des Skype Room System v1-Softwareunterstützung weiterhin funktionieren. Wenn diese Software jedoch auf einen Softwarefehler trifft, der von Microsoft zur Veröffentlichung eines Fixes benötigt wird, wird sie nicht unterstützt. SRS v1 verwendet TLS 1.0/ 1.1, das von Microsoft in Zukunft nicht mehr unterstützt wird. Hier finden Sie weitere Informationen zum Vorbereiten für das Veralteten [von TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>Welche Geräte sind betroffen?

Dies ist die Liste der Geräte, die von dieser Änderung betroffen sind:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Room-Systeme](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Upgradeoptionen

Es gibt mehrere Optionen für ein Upgrade von Lync Room Systems auf die nächste Generation von Microsoft Teams-Räume.

### <a name="crestron-hardware-trade-in-program"></a>Crestron-Hardware-Trade-In-Programm

Durch das Crestron wird ein Upgrade auf das [Crestron SR-System](https://www.crestron.com/products/featured-solutions/crestron-sr) oder ein ähnliches Upgrade für alle Kunden des Lync Room System in Non-Lync Room System (z. B. Smart oder Polycom LRS) ermöglicht. Weitere Informationen zu diesem Programm finden [Sie hier oder](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[E-Mail](mailto:lrsupgrade@crestron.com) Unterstützung von Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Upgrade auf das Upgrade auf Microsoft Teams-Räume

Bestehende Kunden von Crestron RL2 (auch als "Crestron RL200" bezeichnet) können ein Upgrade-Kit erwerben, um das aktuelle RL2 auf RL3 zu aktualisieren, und dafür minimale Kosten pro Gerät zu verwenden. Details zu diesem Programm finden [Sie hier.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Upgrade auf SMART Room Systems

Für SMART LRS-Kunden arbeitet SMART neben dem Hardware-Trade-In-Programm "Crestron" auch an der Bereitstellung einer Lösung für das Upgrade auf Microsoft Teams-Räume. Dieses Upgrade wird von SMART Technologies Inc. kunden unter Produktsupport bereitgestellt. Weitere Informationen dazu finden Sie [hier.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Was sollten Sie tun?

Es wird empfohlen, die Lync Room System-Geräte so zu aktualisieren Microsoft Teams-Räume dass TLS 1.0/1.1 nicht mehr unterstützt wird, indem Sie die oben genannten Upgradeoptionen verwenden. Darüber hinaus können Sie auch vorhandene Geräte durch neue Geräte ersetzen, die für die Microsoft Teams-Räume. Details [finden Sie unter](https://aka.ms/roomdevices) Raumgeräte, und sehen Sie sich auch die Microsoft Teams-Räume [an.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Microsoft Teams-Räume-Software unterstützt das TLS 1.2-Protokoll ab dem 14. Dezember 2018 mit App-Version 4.0.64.0. Für lokale Kunden ist für die Aktivierung der Kommunikation über TLS 1.2 für Microsoft Teams-Räume Skype for Business Server 2015 Kumulatives Update 9 (CU9) oder Skype for Business Server 2019 Kumulatives Update 1 (CU1) erforderlich. Die Änderung sollte sich nicht auf Skype for Business Online-Kunden auswirken, da Clientänderungen vorwärts- und abwärtskompatibel sind.