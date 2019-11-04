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
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924966"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud

Nachdem Sie alle Benutzer aus der lokalen Umgebung in die Cloud verschoben haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb nehmen. Neben dem Entfernen von Hardware besteht ein wichtiger Schritt darin, die lokale Bereitstellung logisch von Office 365 durch Deaktivieren von Hybrid zu trennen. Das Deaktivieren von Hybriden besteht aus drei Schritten:

1. Aktualisieren Sie die DNS-Einträge so, dass Sie auf Office 365 deuten.
2. Deaktivieren Sie die geteilte Domäne im Office 365 Mandanten.
3. Deaktivieren der Fähigkeit in "on-Prem" zur Kommunikation mit Office 365.


Diese Schritte sollten zusammen als Einheit ausgeführt werden. Details finden Sie weiter unten. Außerdem Richtlinien für die Verwaltung von Telefonnummern für migrierte Benutzer, sobald die lokale Bereitstellung getrennt wurde.

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

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Verwalten von Telefonnummern für Benutzer, die von lokal migriert wurden

Administratoren können Benutzer verwalten, die zuvor von lokalen Skype for Business Server in die Cloud verschoben wurden, auch wenn die lokale Bereitstellung außer Betrieb genommen wurde. Es gibt zwei verschiedene Möglichkeiten:
1.  Wenn der Benutzer vor dem Wechsel eine lokale LineUri hatte (vermutlich weil der Benutzer für Enterprise-VoIP aktiviert war), wenn Sie den LineUri ändern möchten, müssen Sie dies in On-Premise AD durchführen und den Wert auf Aad übertragen lassen. Dies erfordert keine lokale Skype for Business Server. Stattdessen kann dieses Attribut, msRTCSIP-Reihe direkt in der lokalen Active Directory, entweder mithilfe von Active Directory Benutzer und Computer MMC-Snap-in oder über PowerShell bearbeitet werden. Wenn Sie das MMC-Snap-in verwenden, öffnen Sie die Seite Eigenschaften des Benutzers, und klicken Sie auf Attribut-Editor-Registerkarte, und suchen Sie msRTCSIP-Reihe.

2.  Wenn der Benutzer vor dem Wechsel nicht über einen Wert für LineUri on-Prem verfügt, können Sie die LineUri mithilfe der-onpremLineUri-Parameter im Cmdlet "CSUser" im Skype for Business Online PowerShell-Modul ändern.

## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md)
