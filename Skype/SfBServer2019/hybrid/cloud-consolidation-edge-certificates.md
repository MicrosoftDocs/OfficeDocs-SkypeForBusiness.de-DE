---
title: Aktualisieren des Edge-Zertifikats
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren der edgezertifikat im Rahmen der Cloud Konsolidierung für Teams und Skype für Unternehmen.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247660"
---
# <a name="update-the-edge-certificate"></a>Aktualisieren des Edge-Zertifikats

Aktualisieren das edgezertifikat ist der wichtigste Schritt zu gewährleisten, dass ordnungsgemäßes routing in einer Umgebung mit gemeinsam genutzten Adresse Speicherplatz auf die zwei SIP-Domänen sicher, dass eine auf Prem-Umgebung mit SipDomain1 eine Cloud-Umgebung mit SipDomain2 teilnehmen kann. Finden Sie in Schritt 14 in der [Cloud Konsolidierung für Teams und Skype für Unternehmen](cloud-consolidation.md) Kontext, in dem Sie diesen Schritt ausführen können. In unseren Beispielen ist SipDomain1 AcquiredCompany. <span>com und SipDomain2 OriginalCompany ist. <span>com.

Der alternative Antragstellername (SAN) des Zertifikats auf allen Edgeservern in der lokalen Umgebung muss aktualisiert werden, in den reinen online Mandanten einbezogen werden alle SIP-Domänen, die vorhanden sind (ausgenommen alle Onmicrosoft.<span> com-Domänen) im Format "Sip. \<Domäne > ".  In unserem Beispiel ist dies Sip. OriginalCompany. <span>com. Dieser Schritt ist wichtig, zu tun, bevor Sie alle Benutzer in die Cloud migrieren.

**Schritte:**

1.  Abrufen ein neues externen Edge-Zertifikats für den Rand, die alle vorhandenen Einträge sowie zusätzliche Einträge im SAN für alle SIP-Domänen in der Cloudumgebung hat (ausgenommen *. onmicrosoft.com Domänen) im Format "Sip. <DomainName>".
2.  Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es des Skype-Edge-Diensts auf jedem der Edge-Dienst.  Ausführliche Schritte finden Sie im Abschnitt "Externer Edge-Schnittstelle Zertifikate" in [Skype für Business Server 2015 Edgedienst bereitstellen](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Starten Sie den Edge-Dienst auf jedem Edgeserver. Hierzu können Sie für ein einzelnes Feld mit den folgenden PowerShell-Befehlen:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype für Unternehmen](cloud-consolidation.md)