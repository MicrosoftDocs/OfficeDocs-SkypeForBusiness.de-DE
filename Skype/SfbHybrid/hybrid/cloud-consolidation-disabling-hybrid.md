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
description: Dieser Artikel enthält detaillierte Schritte zum Deaktivieren von Hybrid als Teil der Cloudkonsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 08d305fa2650cffbadb0ec3122458f4a57e052a4
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899106"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a>Deaktivieren Der Hybridkonfiguration zum Abschließen der Migration in die Cloud

In diesem Artikel wird beschrieben, wie Sie Ihre Hybridkonfiguration deaktivieren, bevor Sie Ihre lokale Skype for Business-Umgebung außer Betrieb gesetzt haben. Dies ist Schritt 2 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben Sie alle erforderlichen Benutzer von lokal in online.](decommission-move-on-prem-users.md)

- **Schritt 2. Deaktivieren Sie die Hybridkonfiguration.** (Dieser Artikel)

- Schritt 3. [Verschieben von Hybridanwendungsendpunkten von lokal in online](decommission-move-on-prem-endpoints.md).

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.](decommission-remove-on-prem.md)


## <a name="overview"></a>Übersicht

Nachdem Sie alle Benutzer von Skype for Business lokal auf Teams Only in Microsoft 365 aktualisiert haben, können Sie die lokale Skype for Business-Bereitstellung außer Betrieb lassen. Bevor Sie die lokale Skype for Business-Bereitstellung außer Betrieb nehmen und Hardware entfernen, müssen Sie die lokale Bereitstellung logisch von Microsoft 365 trennen, indem Sie die Hybridbereitstellung deaktivieren. Das Deaktivieren der Hybridbereitstellung besteht aus den folgenden drei Schritten:

1. Aktualisieren der DNS-Einträge, um auf Microsoft 365 zu verweisen.

2. Deaktivieren des freigegebenen Sip-Adressraums (auch als "geteilte Domäne" bezeichnet) in der Microsoft 365-Organisation.

3. Deaktivieren Sie die Lokale Kommunikation mit Microsoft 365.

Diese Schritte trennen ihre lokale Bereitstellung von Skype for Business Server logisch von Microsoft 365 und sollten als Einheit durchgeführt werden. Details zu jedem Schritt finden Sie in diesem Artikel. Sobald dies abgeschlossen ist, können Sie Ihre lokale Skype for Business-Bereitstellung mithilfe einer der beiden unten aufgeführten Methoden außer Betrieb nehmen.

> [!Important] 
> Sobald diese logische Trennung abgeschlossen ist, besitzen msRTCSIP-Attribute aus Ihrem lokalen Active Directory weiterhin Werte und werden weiterhin über Azure AD Connect mit Azure AD synchronisiert. Wie Sie die lokale Umgebung außer Betrieb setzen, hängt davon ab, ob Sie diese Attribute erhalten oder zunächst aus Ihrem lokalen Active Directory löschen möchten. Beachten Sie, dass das Löschen der lokalen msRTCSIP-Attribute nach der Migration von der lokalen Migration zu einem Dienstverlust für Benutzer führen kann. Details und Tradeoffs der beiden Außerbetriebnahmeansätze werden später beschrieben.

## <a name="detailed-steps"></a>Detaillierte Schritte

1. *Aktualisieren Sie DNS, um auf Microsoft 365 zu verweisen.* Das externe DNS der Organisation für die lokale Organisation muss aktualisiert werden, damit Skype for Business-Einträge auf Microsoft 365 anstelle der lokalen Bereitstellung verweisen. Insbesondere gilt:

    |Eintragstyp|Name|TTL|Wert|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    Darüber hinaus können #A0 für Meet oder Dialin (sofern vorhanden) gelöscht werden. Schließlich sollten alle DNS-Einträge für Skype for Business in Ihrem internen Netzwerk entfernt werden.

    > [!Note] 
    > In seltenen Fällen kann das Ändern von DNS vom lokalen Verweisen auf Microsoft 365 für Ihre Organisation dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktioniert, bis die andere Organisation ihre Verbundkonfiguration aktualisiert:
    >
    > - Alle Verbundorganisationen, die das ältere Modell für den direkten Partnerverbund (auch als Zugelassener Partnerserver bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Ältere Verbundmodell basiert nicht auf DNS-SRV-Einträgen, daher ist eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud wechselt.
    > 
    > - Jede Verbundorganisation, die keinen aktivierten Hostinganbieter für sipfed.online.lync hat. <span> com muss die Konfiguration aktualisieren, um dies zu ermöglichen. Diese Situation ist nur möglich, wenn die Verbundorganisation rein lokal ist und noch nie eine Partnerorganisation mit einem Hybrid- oder Online-Mandanten besteht. In diesem Fall funktioniert der Verbund mit diesen Organisationen erst, wenn sie ihren Hostinganbieter aktivieren.
    >
    > Wenn Sie vermuten, dass einer Ihrer Verbundpartner den direkten Partnerverbund verwendet oder keinen Partnerverbund mit einer Online- oder Hybridorganisation erstellt hat, empfehlen wir Ihnen, ihnen eine Kommunikation dazu zu senden, während Sie sich auf die Migration in die Cloud vorbereiten.


2.  *Deaktivieren sie den freigegebenen Sip-Adressraum in Microsoft 365-Organisation.* Der folgende Befehl muss über ein Skype for Business Online PowerShell-Fenster ausgeführt werden.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Deaktivieren Sie die Lokale Kommunikation mit Microsoft 365.* Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Verwalten von Attributen nach dem Verschieben von Benutzern aus der lokalen Cloud in die Cloud

Standardmäßig sind für alle Benutzer, die zuvor für Skype for Business Server aktiviert und anschließend in die Cloud verschoben wurden, weiterhin msRTCSIP-Attribute in Ihrem lokalen Active Directory konfiguriert. Diese Attribute, insbesondere die sip-Adresse (msRTCSIP-PrimaryUserAddress) und die potenziell telefonnummer (msRTCSIP-Line), werden weiterhin mit Azure AD synchronisiert. Wenn Änderungen an einem der msRTCSIP-Attribute erforderlich sind, müssen diese Änderungen im lokalen Active Directory vorgenommen und dann mit Azure AD synchronisiert werden. Nachdem die Skype for Business Server-Bereitstellung entfernt wurde, stehen die Skype for Business Server-Tools jedoch nicht mehr zur Verfügung, um diese Attribute zu verwalten.

Es stehen zwei Optionen zur Behandlung dieser Situation zur Verfügung:

1. Lassen Sie Benutzer, die für Skype for Business-Serverkonten aktiviert waren, wie sie sind, und verwalten Sie die msRTCSIP-Attribute mithilfe von Active Directory-Tools. Dadurch wird kein Dienstverlust für migrierte Benutzer sichergestellt, und Sie können die Skype for Business Server-Bereitstellung problemlos entfernen, indem Sie die Server ohne vollständige Außerbetriebnahme entfernen (z. B. zurücksetzen). Neu lizenzierte Benutzer haben diese Attribute jedoch nicht in Ihrem lokalen Active Directory aufgefüllt und müssen online verwaltet werden.

2.  Löschen Sie alle msRTCSIP-Attribute von migrierten Benutzern in Ihrem lokalen Active Directory, und verwalten Sie diese Attribute mithilfe von Onlinetools. Diese Methode ermöglicht einen konsistenten Verwaltungsansatz für vorhandene und neue Benutzer, kann jedoch möglicherweise zu einem vorübergehenden Ausfall des Diensts während des lokalen Außerbetriebsetzungsprozesses führen.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Methode 1 : Verwalten von Sipadressen und Telefonnummern für Benutzer in Active Directory

Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch nach der Außerbetriebnahme der lokalen Bereitstellung. Wenn Sie Änderungen an der Sipadresse eines Benutzers oder an der Telefonnummer eines Benutzers vornehmen möchten (und die Sipadresse oder Telefonnummer bereits einen Wert im lokalen Active Directory hat), müssen Sie dies im lokalen Active Directory tun und die Werte in Azure AD fließen lassen. Dies erfordert KEINEN lokalen Skype for Business Server. Stattdessen können Sie diese Attribute direkt im lokalen Active Directory ändern, indem Sie entweder das MMC-Snap-In Active Directory Users and Computers (wie unten gezeigt) oder PowerShell verwenden. Wenn Sie das MMC-Snap-In verwenden, öffnen Sie die Eigenschaftenseite des Benutzers, klicken Sie auf Registerkarte Attribut-Editor, und suchen Sie nach den entsprechenden Attributen zum Ändern:

- Um die Sipadresse eines Benutzers zu ändern, ändern Sie die `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Wenn das `ProxyAddresses` Attribut eine SIP-Adresse enthält, aktualisieren Sie diesen Wert ebenfalls als bewährte Methode. Obwohl die sip-Adresse in von O365 ignoriert wird, wenn aufgefüllt wird, kann sie von anderen lokalen `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` Komponenten verwendet werden.

- Wenn Sie die Telefonnummer eines Benutzers ändern möchten, ändern Sie, `msRTCSIP-Line` *ob sie bereits über einen Wert verfügt.*

  ![Active Directory-Benutzer- und -Computertool](../media/disable-hybrid-1.png)
  
-  Wenn der Benutzer vor dem Verschieben ursprünglich keinen Wert für lokal hatte, können Sie die Telefonnummer mithilfe des `msRTCSIP-Line` --Parameters im `onpremLineUri` [Cmdlet Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) im Skype for Business Online PowerShell-Modul ändern.

Diese Schritte sind für neue Benutzer, die nach der Deaktivierung der Hybridbereitstellung erstellt wurden, nicht erforderlich, und diese Benutzer können direkt in der Cloud verwaltet werden. Wenn Sie die Kombination dieser Methode verwenden und die msRTCSIP-Attribute in Ihrem lokalen Active Directory nicht mehr verwenden möchten, können Sie die lokalen Skype for Business-Server einfach neu abbilden. Wenn Sie es jedoch vorziehen, alle msRTCSIP-Attribute zu löschen und eine herkömmliche Deinstallation von Skype for Business Server zu unternehmen, verwenden Sie Methode 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Methode 2 : Löschen von Skype for Business-Attributen für alle lokalen Benutzer in Active Directory

Diese Option erfordert zusätzlichen Aufwand und eine ordnungsgemäße Planung, da Benutzer, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, erneut bereitgestellt werden müssen. Diese Benutzer können in zwei verschiedene Kategorien unterteilt werden: Benutzer ohne Telefonsystem und Benutzer mit Telefonsystem. Bei Benutzern mit Telefonsystem wird der Telefondienst vorübergehend verloren, wenn die Telefonnummer nicht mehr in lokalem Active Directory in die Cloud verwaltet wird. **Es wird empfohlen, ein Pilotprojekt mit einer kleinen Anzahl von Benutzern mit Telefonsystem durchzuführen, bevor Massenbenutzervorgänge gestartet werden.** Bei großen Bereitstellungen können Benutzer in kleineren Gruppen in unterschiedlichen Zeitfenstern verarbeitet werden. 

> [!NOTE] 
> Dieser Vorgang ist für Benutzer mit einer übereinstimmenden SIP-Adresse und UserPrincipalName am einfachsten. Für Organisationen, in denen Benutzer mit nicht übereinstimmenden Werten über diese beiden Attribute verfügen, muss wie unten erwähnt besondere Vorsicht für einen reibungslosen Übergang verwendet werden.

> [!NOTE]
> Wenn Sie lokale Hybridanwendungsendpunkte für automatische Telefonanten oder Anrufwarteschlangen konfiguriert haben, müssen Sie diese Endpunkte vor dem Außerbetriebsetzen von Skype for Business Server nach Microsoft 365 verschieben.


1. Bestätigen Sie, dass das folgende lokale Skype for Business PowerShell-Cmdlet ein leeres Ergebnis zurückgibt. Ein leeres Ergebnis bedeutet, dass keine Benutzer lokal heimgeheimt werden und entweder zu Microsoft 365 verschoben oder deaktiviert wurden:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Notieren Sie die aktuelle Telefonnummer (LineUri), UserPrincipalName und zugehörige Informationen der Benutzer, indem Sie das folgende lokale Skype for Business Server PowerShell-Cmdlet zum Exportieren von Benutzerdaten ausführen:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Bevor Sie das Öffnen SfbUserSettings.csv, und vergewissern Sie sich, dass alle Benutzerdaten erfolgreich exportiert wurden. Es wird empfohlen, eine Kopie dieser Datei zu behalten.  Verwenden Sie diese Datei nicht in den folgenden Schritten für die Verarbeitung von Benutzern. 

3. Erstellen Sie eine Datei mit einer Gruppe von Benutzern, die in den folgenden Schritten verwendet werden soll. Nachdem die erste Gruppe von Benutzern erfolgreich abgeschlossen wurde, fahren Sie mit der nächsten Gruppe von Benutzern fort. Im folgenden Beispiel werden die Benutzergruppen alphabetisch ausgewählt, Sie können jedoch nach Benutzern basierend auf Kriterien filtern, die mit der Art und Weise, wie Sie die Benutzer verarbeiten möchten, entsprechen.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Bevor Sie das Öffnen SfbUsers.csv, und bestätigen Sie, dass Benutzerdaten erfolgreich exportiert wurden. Sie benötigen lineUri (Telefonnummer), UserPrincipalName, SamAccountName und SipAddress aus dieser Datei in einem späteren Schritt.

4. Löschen Sie die Attributinformationen zu Skype for Business Server aus active Directory für die Benutzer, die Sie aktualisieren können.  Es gibt 2 Schritte zu diesem Prozess, wie unten gezeigt.

   > [!Important] 
   > Nach dem nächsten AAD-Synchronisierungszyklus nach Ausführung dieses Schritts verlieren Benutzer mit Telefonsystem, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, die Möglichkeit, Anrufe zu führen und zu empfangen, bis Schritt 8 erfolgreich abgeschlossen und in Schritt 9 bestätigt wurde. Stellen Sie außerdem sicher, dass Sie die Telefonnummern und zugehörigen Informationen des Benutzers nach Schritt 2 gespeichert haben, da diese Informationen für diesen Schritt erforderlich sind.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Löschen Sie als Nächstes für dieselbe Gruppe von Benutzern den Wert von msRTCSIP-DeploymentLocator mithilfe der lokalen Active Directory PowerShell:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Führen Sie das folgende lokale Active Directory-Modul für Windows PowerShell aus, um dem lokalen Active Directory-ProxyAddresses einen sip-Adresswert hinzuzufügen. Dadurch werden Interoperabilitätsprobleme verhindert, die auf diesem Attribut beruhen. 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. Ausführen der Azure AD-Synchronisierung

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Warten Sie, bis die Benutzerbereitstellung abgeschlossen ist. Sie können den Fortschritt der Benutzerbereitstellung überwachen, indem Sie den folgenden Skype for Business Online PowerShell-Befehl ausführen. Der folgende Skype for Business Online PowerShell-Befehl gibt ein leeres Ergebnis zurück, sobald der Prozess abgeschlossen ist.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Führen Sie den folgenden Skype for Business Online PowerShell-Befehl aus, um Telefonnummern zuzuordnen und Benutzer für das Telefonsystem zu aktivieren:
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  Wenn Sie weiterhin Über Skype for Business-Endpunkte (entweder Skype-Clients oder Drittanbietertelefone) verfügen, sollten Sie auch -HostedVoiceMail auf $true. Wenn Ihre Organisation nur Teams-Endpunkte für sprachfähige Benutzer verwendet, gilt diese Einstellung nicht für Ihre Benutzer. 

9. Vergewissern Sie sich, dass Benutzer mit Telefonsystemfunktionen ordnungsgemäß bereitgestellt wurden. Der folgende Skype for Business Online PowerShell-Befehl gibt ein leeres Ergebnis zurück, sobald der Prozess abgeschlossen ist.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. Wiederholen Sie die Schritte 3 bis 9, bis alle Benutzer verarbeitet werden.

11. Vergewissern Sie sich, dass alle Benutzer erfolgreich verarbeitet wurden, indem Sie die folgenden beiden PowerShell-Befehle ausführen.

    Lokales Skype for Business Server-lokales PowerShell-Befehl:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Skype for Business Online PowerShell-Befehl:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. Nachdem Sie alle Schritte in Methode 2 abgeschlossen haben, finden Sie unter Verschieben von Hybridanwendungsendpunkten von lokal in [online](decommission-move-on-prem-endpoints.md) und Entfernen Ihres lokalen Skype for Business Server weitere Schritte zum Entfernen Ihrer lokalen Skype for [Business Server-Bereitstellung.](decommission-remove-on-prem.md)


## <a name="see-also"></a>Weitere Artikel

- [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

