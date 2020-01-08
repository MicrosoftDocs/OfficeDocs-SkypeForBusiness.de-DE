---
title: Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud
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
ms.openlocfilehash: d3420c1bd40bbdeeff25747153210c2600d929f6
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963073"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud

Nachdem Sie alle Benutzer von lokal in die Cloud verschoben haben, können Sie die lokale Skype for Business-Bereitstellung außer Betrieb nehmen. Abgesehen davon, dass Hardware entfernt wird, besteht ein wichtiger Schritt darin, die lokale Bereitstellung von Office 365 durch Deaktivieren der Hybridbereitstellung zu trennen. Das Deaktivieren von Hybriden besteht aus drei Schritten:

1. Aktualisieren Ihrer DNS-Einträge derart, dass sie auf Office 365 verweisen.

2. Deaktivieren der geteilten Domäne im Office 365-Mandanten.

3. Deaktivieren Sie die Möglichkeit in der lokalen Kommunikation mit Office 365.

Diese Schritte sollten zusammen als Einheit ausgeführt werden. Details finden Sie weiter unten. Darüber hinaus werden Richtlinien für die Verwaltung von Telefonnummern für migrierte Benutzer bereitgestellt, sobald die lokale Bereitstellung getrennt wird.

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

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Deaktivieren der Fähigkeit in der lokalen Umgebung zur Kommunikation mit Office 365.*  
Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden:
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Verwalten von Telefonnummern für Benutzer, die von lokal migriert wurden

Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch wenn die lokale Bereitstellung außer Betrieb genommen wurde. Es gibt zwei verschiedene Möglichkeiten:

- Der Benutzer hat vor dem Wechsel keinen Wert für LineURI lokal bereitstellen können. 

  In diesem Fall können Sie die LineURI mithilfe der-onpremLineUri-Parameter im Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) " im Skype for Business Online PowerShell-Modul ändern.

- Der Benutzer hatte eine lokale LineURI vor dem Wechsel (vermutlich, weil der Benutzer für Enterprise-VoIP aktiviert wurde). 

  Wenn Sie das LineURI ändern möchten, müssen Sie dies in der lokalen Active Directory durchführen und den Wert auf Azure AD übernehmen. Dies erfordert keine lokale Skype for Business Server. Dieses Attribut, msRTCSIP, kann vielmehr direkt im lokalen Active Directory bearbeitet werden, indem entweder das MMC-Snap-in Active Directory Benutzer und Computer oder die PowerShell verwendet wird. Wenn Sie das MMC-Snap-in verwenden, öffnen Sie die Seite Eigenschaften des Benutzers, klicken Sie auf Registerkarte Attribut-Editor, und suchen Sie nach msRTCSIP-Reihe.

  ![Tool zum Active Directory von Benutzern und Computern](../media/disable-hybrid-1.png)

## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md)
