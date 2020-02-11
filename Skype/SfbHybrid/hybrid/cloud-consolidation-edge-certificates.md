---
title: Aktualisieren des Edge-Zertifikats
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
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren des Edge-Zertifikats im Rahmen der Cloud-Konsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888604"
---
# <a name="update-the-edge-certificate"></a>Aktualisieren des Edge-Zertifikats

Das Aktualisieren des Edge-Zertifikats ist der wichtigste Schritt, um sicherzustellen, dass eine on-Prem-Umgebung mit SipDomain1 einer Cloud-Umgebung mit SipDomain2 beitreten kann und dass das ordnungsgemäße Routing in einer freigegebenen Adressraum Umgebung über die beiden SIP-Domänen hinweg gewährleistet ist. Weitere Informationen finden Sie unter Schritt 14 bei der [Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md) für den Kontext, in dem Sie diesen Schritt ausführen können. In unseren Beispielen ist SipDomain1 AcquiredCompany. <span>com und SipDomain2 ist OriginalCompany. <span>com.

Der Alternative Antragstellername (San) des Zertifikats auf allen Edge-Servern in der lokalen Umgebung muss so aktualisiert werden, dass er alle SIP-Domänen enthält, die im reinen Online Mandanten vorhanden sind<span> (ohne onmicrosoft. com-Domänen) im Format "SIP. \<Domänen> ".  In unserem Beispiel ist dies SIP. OriginalCompany. <span>com. Dieser Schritt ist wichtig, bevor Sie alle Benutzer in die Cloud migrieren.

**Schritte**

1.  Beziehen Sie ein neues externes Edge-Zertifikat für den Edge mit allen vorhandenen Einträgen sowie zusätzliche Einträge im San für alle SIP-Domänen in der Cloud-Umgebung (außer *. onmicrosoft.com Domänen) im Format "SIP. <DomainName>".
2.  Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es dem Skype-Edgedienst auf jedem Edge-Dienst zu.  Ausführliche Anweisungen finden Sie im Abschnitt "externe Edge-Schnittstellen Zertifikate" unter [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).
3.  Starten Sie den Edgedienst auf jedem Edgeserver neu. Sie können dies für ein einzelnes Feld mit den folgenden PowerShell-Befehlen ausführen:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md)