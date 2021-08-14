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
localization_priority: Normal
description: Dieser Anhang enthält ausführliche Schritte zum Aktualisieren des Edgezertifikats im Rahmen der Cloudkonsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 7370fe6949c471a6aad9b45ee246f1565b43bdb465eba2110a03f53afa69fe28
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330629"
---
# <a name="update-the-edge-certificate"></a>Aktualisieren des Microsoft Edge-Zertifikats

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Das Aktualisieren des Edgezertifikats ist der wichtigste Schritt, um sicherzustellen, dass eine lokale Umgebung mit SipDomain1 einer Cloudumgebung mit SipDomain2 beitreten und ein ordnungsgemäßes Routing in einer freigegebenen Adressraumumgebung über die beiden SIP-Domänen hinweg sicherstellen kann. In Schritt 14 der [Cloudkonsolidierung finden](cloud-consolidation.md) Sie Teams und Skype for Business für den Kontext, in dem Sie diesen Schritt ausführen können. In unseren Beispielen ist SipDomain1 acquiredCompany. <span> com und SipDomain2 ist OriginalCompany. <span> Com.

Der alternative Antragstellername (Subject Alternate Name, SAN) des Zertifikats auf allen Edgeservern in der lokalen Umgebung muss aktualisiert werden, um alle SIP-Domänen einzuschließen, die im reinen Onlinemandanten vorhanden sind (mit Ausnahme aller Onmicrosoft-Domänen). <span> com domains), in der Form "sip. \<domain> ".  In unserem Beispiel ist dies sip. OriginalCompany. <span> Com. Dieser Schritt ist wichtig, bevor Benutzer in die Cloud migriert werden.

**Schritte:**

1.  Rufen Sie ein neues externes Edgezertifikat für den Edgeserver ab, der alle vorhandenen Einträge sowie zusätzliche Einträge im SAN für alle SIP-Domänen in der Cloudumgebung (mit Ausnahme von *.onmicrosoft.com Domänen) im Format "sip. <DomainName> " enthält.
2.  Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es dem Skype Edgedienst auf jedem Edgedienst zu.  Ausführliche Schritte finden Sie im Abschnitt "Externe Edgeschnittstellenzertifikate" in [Deploy Edge Service in Skype for Business Server 2015.](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)
3.  Starten Sie den Edgedienst auf jedem Edgeserver neu. Sie können dies für ein einzelnes Feld mit den folgenden PowerShell-Befehlen tun:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Weitere Artikel

[Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)