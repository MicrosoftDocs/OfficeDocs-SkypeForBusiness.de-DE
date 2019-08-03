---
title: Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Deaktivieren von Hybriden im Rahmen der Cloud-Konsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160586"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud

Nachdem Sie alle Benutzer aus der lokalen Umgebung in die Cloud verschoben haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb nehmen. Neben dem Entfernen von Hardware besteht ein wichtiger Schritt darin, die lokale Bereitstellung logisch von Office 365 durch Deaktivieren von Hybrid zu trennen. Das Deaktivieren von Hybriden besteht aus drei Schritten:

1. Aktualisieren Sie die DNS-Einträge so, dass Sie auf Office 365 deuten.
2. Deaktivieren Sie die geteilte Domäne im Office 365 Mandanten.
3. Deaktivieren der Fähigkeit in "on-Prem" zur Kommunikation mit Office 365.


Diese Schritte sollten zusammen als Einheit ausgeführt werden. Details finden Sie weiter unten.

> [!Note] 
> In seltenen Fällen kann es dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktionsfähig ist, wenn das Ändern von DNS von einem Standort auf einen Office 365 für Ihre Organisation erfolgt, bis eine andere Organisation ihre Verbund Konfiguration aktualisiert:<ul><li>
Alle Verbundorganisationen, die das ältere direkte Verbundmodell (auch als zulässiger Partner Server bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für Ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Legacy-Verbundmodell basiert nicht auf DNS-SRV-Einträgen, daher wird eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud wechselt. </li><li>Jede Partnerorganisation, die über keinen aktivierten Hostinganbieter für sipfed. online. lync verfügt. <span>com muss Ihre Konfiguration aktualisieren, um dies zu ermöglichen. Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und nie mit einem hybriden oder Online-Mandanten verbunden ist. In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn er seinen Hostinganbieter aktiviert.</li></ul>Wenn Sie vermuten, dass einer ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder mit einer Online-oder Hybrid Organisation verbunden ist, empfehlen wir Ihnen, Ihnen beim Vorbereiten der Migration zur Cloud eine entsprechende Mitteilung zu senden.

1.  *Aktualisieren Sie DNS so, dass es auf Office 365 zeigt.*
Das externe DNS der Organisation für die lokale Organisation muss so aktualisiert werden, dass Skype for Business Datensätze auf Office 365 statt auf die lokale Bereitstellung deuten. Insbesondere gilt:

    |Eintragstyp|Name|TTL|Wert|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. online. lync. <span>com-|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. lync. <span>com-|
    |CNAME| lyncdiscover|   3600|   WebDir. online. lync. <span>com-|
    |CNAME| sip|    3600|   sipdir. online. lync. <span>com-|
    |CNAME| erfüllen|   3600|   WebDir. online. lync. <span>com-|
    |CNAME| Dialin  |3600|  WebDir. online. lync. <span>com-|

2.  *Deaktivieren Sie den freigegebenen SIP-Adressraum in Office 365 Mandanten.*
Der folgende Befehl muss in einem Skype for Business Online PowerShell-Fenster ausgeführt werden.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Deaktivieren der Fähigkeit in "on-Prem" zur Kommunikation mit Office 365.*  
Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden.  Wenn Sie zuvor eine Skype for Business Online Sitzung importiert haben, starten Sie eine neue Skype for Business PowerShell-Sitzung.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md)