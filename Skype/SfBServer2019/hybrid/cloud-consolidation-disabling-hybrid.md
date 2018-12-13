---
title: Deaktivieren Sie zum Abschließen der Migration zur Cloud hybrid
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
description: Dieser Anhang enthält ausführliche Schritte zum Deaktivieren von Hybriden als Teil der Cloud Konsolidierung für Teams und Skype für Unternehmen.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247668"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deaktivieren Sie zum Abschließen der Migration zur Cloud hybrid

Nachdem Sie alle Benutzer in die Cloud aus lokalen verschoben haben, können Sie die lokalen Skype für die Business-Bereitstellung außer Betrieb nehmen. Ein wichtiger Schritt darin, neben dem Entfernen von Hardware, logisch der lokalen Bereitstellung von Office 365 getrennt durch Hybrid deaktivieren. Deaktivieren von Hybriden umfasst 3 Schritte:

1. Aktualisieren von DNS-Einträge So zeigen Sie auf Office 365.
2. Geteilte Domäne in Office 365-Mandanten zu deaktivieren.
3. Deaktivieren Sie die Möglichkeit in auf Prem Kommunikation mit Office 365.


Diese Schritte sollten zusammen als Einheit erfolgen. Ausführliche Informationen finden Sie weiter unten.

> [!Note] 
> In seltenen Fällen verursachen ändern DNS aus lokal zu Office 365 für Ihre Organisation verweisen Verbund mit einige andere Organisationen mehr funktionieren erst, dass andere Organisation ihre Verbundkonfiguration aktualisiert werden:<ul><li>
Alle verbundorganisationen, die das ältere direkte Federation-Objektmodell (auch bekannt als zulässige Partnerserver) verwenden, müssen so aktualisieren Sie ihre zulässiger Domäneneinträge für ihre Organisation, um den FQDN-Proxy zu entfernen. Diese Vorversion Federation-Objektmodell basiert nicht auf DNS-SRV-Einträge, damit eine solche Konfiguration veralten wird nach Ihrer Organisation zur Cloud verschoben. </li><li>Alle verbundenen Organisation, die nicht über eine aktivierte Hostinganbieter für sipfed.online.lync verfügt. <span>com, müssen Sie ihre Konfiguration zum Aktivieren, die zu aktualisieren. Dies ist nur möglich, wenn der Partnerorganisation rein lokal ist und wurde noch nie mit allen Hybrid oder online-Mandanten Verbund. In diesem Fall funktioniert einen Verbund mit diesen Organisationen nicht, bis sie ihre Hostinganbieter ermöglichen.</li></ul>Wenn Sie annehmen, dass einige der Partner im Verbund mithilfe von direkter Verbund oder online mit einem Verbund haben oder hybridorganisation, es wird empfohlen, dass Sie dies eine Kommunikation dazu veranlassen Sie bei der Vorbereitung für die Durchführung die Migration zur Cloud.

1.  *So zeigen Sie auf Office 365 DNS zu aktualisieren.*
Die Organisation externe DNS-Server für die lokale Organisation muss aktualisiert werden, sodass Skype für Unternehmensunterlagen zeigen Sie auf Office 365 anstelle der lokalen Bereitstellung. Insbesondere:

    |Eintragstyp|Name|TTL|Wert|
    |---|---|---|---|
    |SRV|_sipfederationtls|3600|100 1 5061 sipfed.online.lync. <span>com|
    |SRV|_sip|3600|100 1 443 sipdir.online.lync. <span>com|
    |CNAME| lyncdiscover|   3600|   WebDir.Online.Lync. <span>com|
    |CNAME| SIP|    3600|   sipdir.Online.Lync. <span>com|
    |CNAME| erfüllen|   3600|   WebDir.Online.Lync. <span>com|
    |CNAME| Dialin  |3600|  WebDir.Online.Lync. <span>com|

2.  *Deaktivieren von freigegebenen SIP-Adressraums in Office 365-Mandanten.*
Geben Sie folgenden Befehl muss über einen Skype für Business Online-PowerShell-Fenster ausgeführt werden.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Deaktivieren Sie die Möglichkeit in auf Prem Kommunikation mit Office 365.*  
Geben Sie folgenden Befehl muss über eine lokale PowerShell-Fenster ausgeführt werden.  Wenn Sie bereits einen Skype für Business Online-Sitzung importiert haben, starten Sie eine neue Skype für Business PowerShell-Sitzung.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype für Unternehmen](cloud-consolidation.md)