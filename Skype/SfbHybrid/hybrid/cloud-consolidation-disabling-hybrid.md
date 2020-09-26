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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Deaktivieren von Hybriden im Rahmen der Cloud-Konsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277258"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud

Nachdem Sie alle Benutzer von lokal in die Cloud verschoben haben, können Sie die lokale Skype for Business-Bereitstellung außer Betrieb nehmen. Neben dem Entfernen von Hardware besteht ein wichtiger Schritt darin, die lokale Bereitstellung von Microsoft 365 oder Office 365 durch Deaktivieren von Hybridität logisch voneinander zu trennen. Das Deaktivieren von Hybriden besteht aus drei Schritten:

1. Aktualisieren Sie die DNS-Einträge so, dass Sie auf Microsoft 365 oder Office 365 verweist.

2. Deaktivieren Sie die geteilte Domäne in der Microsoft 365-oder Office 365-Organisation.

3. Deaktivieren Sie die Möglichkeit in der lokalen Kommunikation mit Microsoft 365 oder Office 365.

Diese Schritte sollten zusammen als Einheit ausgeführt werden. Details finden Sie weiter unten. Darüber hinaus werden Richtlinien für die Verwaltung von Telefonnummern für migrierte Benutzer bereitgestellt, sobald die lokale Bereitstellung getrennt wird.

Sobald diese Schritte abgeschlossen sind, werden die lokalen Skype for Business Server nicht mehr verwendet, und diese Server können neu abbildet werden.

> [!Important] 
>Sie sollten weiterhin die msRTCSIP-Attribute in Active Directory Sync über Azure AD Connect in Azure Ad lassen.  Löschen Sie keines dieser Attribute, es sei denn, Sie werden durch den Support geleitet.  Führen Sie disable-CsUser nicht in der lokalen Umgebung aus. Wenn Sie die SIP-Adresse eines Benutzers ändern müssen, führen Sie dies in Ihrem lokalen Active Directory aus, und lassen Sie diese Änderung über Azure AD Connect wie unten beschrieben in Azure AD synchronisieren. Wenn Sie eine Telefonnummer ändern müssen und die LineURI des Benutzers lokal bereits definiert ist, sollten Sie dies entsprechend in der lokalen Active Directory ändern.
>Wenn Sie die lokalen msRTCSIP-Attribute löschen, nachdem Sie von einem lokalen Standort migriert haben, kann dies zu einem Verlust des Diensts für Benutzer führen.


1.  *Aktualisieren Sie DNS so, dass es auf Microsoft 365 oder Office 365 verweist.*
Das externe DNS der Organisation für die lokale Organisation muss so aktualisiert werden, dass Skype for Business Datensätze auf Microsoft 365 oder Office 365 anstatt auf die lokale Bereitstellung deuten. Insbesondere gilt:

    |Eintragstyp|Name|TTL|Wert|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. online. lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. lync. <span> com|
    |CNAME| lyncdiscover|   3600|   WebDir. online. lync. <span> com|
    |CNAME| sip|    3600|   sipdir. online. lync. <span> com|
    |CNAME| erfüllen|   3600|   WebDir. online. lync. <span> com|
    |CNAME| Dialin  |3600|  WebDir. online. lync. <span> com|

    Außerdem können CNAME-Einträge für Meet oder Dialin (sofern vorhanden) gelöscht werden. Schließlich sollten alle DNS-Einträge für Skype for Business im internen Netzwerk entfernt werden.

    > [!Note] 
    > In seltenen Fällen kann es dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktionsfähig ist, wenn das Ändern von DNS von einem Standort auf einen Office 365 für Ihre Organisation erfolgt, bis eine andere Organisation ihre Verbund Konfiguration aktualisiert:
    >
    > - Alle Verbundorganisationen, die das ältere direkte Verbundmodell (auch als zulässiger Partner Server bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für Ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Legacy-Verbundmodell basiert nicht auf DNS-SRV-Einträgen, daher wird eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud wechselt.
    > 
    > - Jede Partnerorganisation, die über keinen aktivierten Hostinganbieter für sipfed. online. lync verfügt. <span> com muss Ihre Konfiguration aktualisieren, um dies zu ermöglichen. Diese Situation ist nur möglich, wenn die Verbundorganisation lediglich lokal ist und nie mit einem hybriden oder Online Mandanten verbunden ist. In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn er seinen Hostinganbieter aktiviert.
    >
    > Wenn Sie vermuten, dass einer ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder nicht mit einer Online-oder Hybrid Organisation verbunden ist, empfehlen wir Ihnen, Ihnen beim Vorbereiten der Migration zur Cloud eine entsprechende Mitteilung zu senden.


2.  *Deaktivieren Sie den freigegebenen SIP-Adressraum in Microsoft 365 oder Office 365 Organisation.*
Der folgende Befehl muss in einem Skype for Business Online PowerShell-Fenster ausgeführt werden.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Deaktivieren der Fähigkeit in der lokalen Umgebung zur Kommunikation mit Microsoft 365 oder Office 365.*  
Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Verwalten von SIP-Adressen und Telefonnummern für Benutzer, die von einem lokalen Standort aus migriert wurden

Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch wenn die lokale Bereitstellung außer Betrieb genommen wurde. Wenn Sie Änderungen an der SIP-Adresse eines Benutzers oder an dem Anschluss-URI eines Benutzers vornehmen möchten (und die SIP-Adresse oder der Anschluss-URI bereits in der lokalen Active Directory definiert ist), müssen Sie dies in der lokalen Active Directory tun und den Wert (en) bis Azure AD fließen lassen. Dies erfordert keine lokale Skype for Business Server. Sie können diese Attribute vielmehr direkt im lokalen Active Directory ändern, indem Sie entweder das MMC-Snap-in Active Directory Benutzer und Computer oder mithilfe von PowerShell verwenden. Wenn Sie das MMC-Snap-in verwenden, öffnen Sie die Eigenschaftenseite des Benutzers, klicken Sie auf Registerkarte Attribut-Editor, und suchen Sie nach den entsprechenden Attributen, die Sie ändern möchten:

- Um die SIP-Adresse eines Benutzers zu ändern, ändern Sie die `msRTCSIP-PrimaryUserAddress` . Wenn das `ProxyAddresses` Attribut einen SIP-Wert enthält, aktualisieren Sie außerdem diesen SIP-Wert so, dass er dem neuen Wert von entspricht `msRTCSIP-PrimaryUserAddress` . Wenn er keinen SIP-Wert enthält, können Sie ihn leer lassen.

- Um die Telefonnummer eines Benutzers zu ändern, ändern `msRTCSIP-Line` *Sie ihn, wenn er bereits einen Wert aufweist*.

  ![Tool zum Active Directory von Benutzern und Computern](../media/disable-hybrid-1.png)
  
Wenn der Benutzer ursprünglich keinen Wert für `LineURI` lokal vor dem Wechsel hat, können Sie die LineURI mithilfe des- `onpremLineUri` Parameters im [Cmdlet "CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) " im PowerShell-Modul Skype for Business Online ändern.


## <a name="see-also"></a>Siehe auch

[Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md)
