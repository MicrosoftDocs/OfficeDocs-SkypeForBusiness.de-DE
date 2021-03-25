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
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren des Edgezertifikats im Rahmen der Cloudkonsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120344"
---
# <a name="update-the-edge-certificate"></a>Aktualisieren des Microsoft Edge-Zertifikats

Das Aktualisieren des Edgezertifikats ist der wichtigste Schritt, um sicherzustellen, dass eine umgebungsbasierte Umgebung mit SipDomain1 einer Cloudumgebung mit SipDomain2 beitreten und ein ordnungsgemäßes Routing in einer freigegebenen Adressraumumgebung über die beiden SIP-Domänen hinweg sicherstellen kann. In Schritt 14 unter [Cloudkonsolidierung für Teams](cloud-consolidation.md) und Skype for Business finden Sie Einen Kontext, in dem Sie diesen Schritt ausführen können. In unseren Beispielen ist SipDomain1 AcquiredCompany. <span> com und SipDomain2 ist OriginalCompany. <span> com.

Der alternative Subject Name (SAN) des Zertifikats auf allen Edgeservern in der lokalen Umgebung muss so aktualisiert werden, dass er alle SIP-Domänen enthält, die im reinen Online-Mandanten vorhanden sind (mit Ausnahme von onmicrosoft. <span> com domains) in der Form "sip. \<domain> ".  In unserem Beispiel ist dies sip. OriginalCompany. <span> com. Dieser Schritt ist wichtig, bevor Benutzer in die Cloud migriert werden.

**Schritte:**

1.  Rufen Sie ein neues externes Edgezertifikat für den Edge mit allen vorhandenen Einträgen sowie zusätzlichen Einträgen im SAN für alle #A0 in der Cloudumgebung (ohne *.onmicrosoft.com-Domänen) im Format "sip. <DomainName> " ab.
2.  Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es dem Skype-Edgedienst für jeden Edgedienst zu.  Ausführliche Schritte finden Sie im Abschnitt "Externe Edgeschnittstellenzertifikate" unter [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Starten Sie den Edgedienst auf jedem Edgeserver neu. Sie können dies für ein einzelnes Feld mit den folgenden PowerShell-Befehlen tun:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Siehe auch

[Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)