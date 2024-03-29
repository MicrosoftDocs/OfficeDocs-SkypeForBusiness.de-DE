---
title: Aktualisieren des Microsoft Edge-Zertifikats
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: Dieser Anhang enthält ausführliche Schritte zum Aktualisieren des Edgezertifikats im Rahmen der Cloudkonsolidierung für Teams und Skype for Business.
ms.openlocfilehash: bb8d2eabf17d83546737d3d94fb4add5dc0a892e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857112"
---
# <a name="update-the-edge-certificate"></a>Aktualisieren des Microsoft Edge-Zertifikats

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Das Aktualisieren des Edgezertifikats ist der wichtigste Schritt, um sicherzustellen, dass eine lokale Umgebung mit SipDomain1 einer Cloudumgebung mit SipDomain2 beitreten und ein ordnungsgemäßes Routing in einer freigegebenen Adressraumumgebung über die beiden SIP-Domänen hinweg sicherstellen kann. In Schritt 14 der [Cloudkonsolidierung finden](cloud-consolidation.md) Sie Teams und Skype for Business für den Kontext, in dem Sie diesen Schritt ausführen können. In unseren Beispielen ist SipDomain1 acquiredCompany. <span> com und SipDomain2 ist OriginalCompany. <span> Com.

Der alternative Antragstellername (Subject Alternate Name, SAN) des Zertifikats auf allen Edgeservern in der lokalen Umgebung muss aktualisiert werden, um alle SIP-Domänen einzuschließen, die im reinen Onlinemandanten vorhanden sind (mit Ausnahme aller Onmicrosoft-Domänen). <span> com domains), in der Form "sip. \<domain> ".  In unserem Beispiel ist dies sip. OriginalCompany. <span> Com. Dieser Schritt ist wichtig, bevor Benutzer in die Cloud migriert werden.

**Schritte:**

1.  Rufen Sie ein neues externes Edgezertifikat für den Edge ab, der alle vorhandenen Einträge sowie zusätzliche Einträge im SAN für alle SIP-Domänen in der Cloudumgebung (mit Ausnahme von *.onmicrosoft.com Domänen) im Formular `sip.<DomainName>` enthält.
2.  Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es dem Skype Edgedienst auf jedem Edgedienst zu.  Ausführliche Schritte finden Sie im Abschnitt "Externe Edgeschnittstellenzertifikate" in [Deploy Edge Service in Skype for Business Server 2015.](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)
3.  Starten Sie den Edgedienst auf jedem Edgeserver neu. Sie können dies für ein einzelnes Feld mit den folgenden PowerShell-Befehlen tun:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Siehe auch

[Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)