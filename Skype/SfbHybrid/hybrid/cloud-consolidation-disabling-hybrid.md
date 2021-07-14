---
title: Deaktivieren der Hybridbereitstellung zum Abschließen der Migration zu Teams Only
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
description: Dieser Artikel enthält ausführliche Schritte zum Deaktivieren der Hybridbereitstellung im Rahmen der Cloudkonsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420840"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Deaktivieren Der Hybridkonfiguration, um die Migration zu Teams Only abzuschließen 

In diesem Artikel wird beschrieben, wie Sie Ihre Hybridkonfiguration vor der Außerbetriebnahme Ihrer lokalen Skype for Business umgebung deaktivieren. Dies ist Schritt 2 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben Sie alle erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung.](decommission-move-on-prem-users.md)

- **Schritt 2. Deaktivieren Sie die Hybridkonfiguration.** (Dieser Artikel)

- Schritt 3: [Migrieren Sie Hybridanwendungsendpunkte von der lokalen Umgebung in die Onlineumgebung.](decommission-move-on-prem-endpoints.md)

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business Bereitstellung.](decommission-remove-on-prem.md)

> [!NOTE]
> Die Schritte 2 und 3 sollten im gleichen Wartungsfenster ausgeführt werden, da vorhandene Hybridanwendungsendpunkte zwischen Schritt 2 und Abschluss von Schritt 3 nicht gefunden werden können.

## <a name="overview"></a>Übersicht

Nachdem Sie alle Benutzer von Skype for Business lokal auf Teams nur in Microsoft 365 aktualisiert haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb gesetzt haben. Bevor Sie die lokale Skype for Business Bereitstellung außer Betrieb genommen und Hardware entfernt haben, müssen Sie die lokale Bereitstellung logisch von Microsoft 365 trennen, indem Sie die Hybridbereitstellung deaktivieren. Das Deaktivieren der Hybridbereitstellung besteht aus den folgenden vier Schritten:

1. Aktualisieren der DNS-Einträge, um auf Microsoft 365 zu verweisen.

2. Ändern Sie den Koexistenzmodus für Ihre Organisation in Teams Only.

3. Deaktivieren Sie den freigegebenen SIP-Adressraum (auch als "geteilte Domäne" bezeichnet) in der Microsoft 365 Organisation.

4. Deaktivieren Sie die Möglichkeit, lokal mit Microsoft 365 zu kommunizieren.

Diese Schritte trennen ihre lokale Bereitstellung von Skype for Business Server logisch von Microsoft 365 und stellen sicher, dass Ihre Organisation vollständig Teams ist. Details zu den einzelnen Schritten finden Sie in diesem Artikel. Sobald dies abgeschlossen ist, können Sie Ihre lokale Skype for Business Bereitstellung mithilfe einer der beiden unten aufgeführten Methoden außer Betrieb lassen.

> [!Important] 
> Sobald diese logische Trennung abgeschlossen ist, weisen msRTCSIP-Attribute aus Ihrem lokalen Active Directory weiterhin Werte auf und werden weiterhin über Azure AD Verbinden in Azure AD synchronisiert. Wie Sie die lokale Umgebung außer Betrieb nehmen, hängt davon ab, ob Sie diese Attribute beibehalten oder zuerst aus Ihrem lokalen Active Directory löschen möchten. Beachten Sie, dass das Löschen der lokalen msRTCSIP-Attribute nach der Migration von der lokalen Bereitstellung zu einem Dienstverlust für Benutzer führen kann! Details und Nachteile der beiden Außerbetriebnahmeansätze werden später beschrieben.

## <a name="detailed-steps"></a>Detaillierte Schritte

1. *Aktualisieren Sie DNS so, dass es auf Microsoft 365 verweist.* Das externe DNS der Organisation für die lokale Organisation muss aktualisiert werden, damit Skype for Business Einträge auf Microsoft 365 anstatt auf die lokale Bereitstellung verweisen. Insbesondere gilt:

    |Eintragstyp|Name|TTL|Priorität|Schriftbreite|Port|Wert|
    |---|---|---|---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync. <span> Com|
    |SRV|_sip._tls|3600|100|1|443|sipdir.online.lync. <span> Com|
    |CNAME| lyncdiscover|   3600| | | |webdir.online.lync. <span> Com|
    |CNAME| sip|    3600| | | | sipdir.online.lync. <span> Com|

    Darüber hinaus können CNAME-Einträge für Meet- oder Dialin-Einträge (sofern vorhanden) gelöscht werden. Schließlich sollten alle DNS-Einträge für Skype for Business in Ihrem internen Netzwerk entfernt werden.

    > [!Note] 
    > In seltenen Fällen kann das Ändern von DNS von der Lokalen auf Microsoft 365 für Ihre Organisation dazu führen, dass der Partnerverbund mit einigen anderen Organisationen nicht mehr funktioniert, bis diese andere Organisation ihre Verbundkonfiguration aktualisiert:
    >
    > - Alle Verbundorganisationen, die das ältere Direct Federation-Modell (auch als zulässiger Partnerserver bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Legacyverbundmodell basiert nicht auf DNS-SRV-Einträgen, sodass eine solche Konfiguration veraltet ist, sobald Ihre Organisation in die Cloud verschoben wird.
    > 
    > - Eine Partnerorganisation, die über keinen aktivierten Hostinganbieter für "sipfed.online.lync" verfügt. <span> com muss die Konfiguration aktualisieren, um dies zu aktivieren. Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und nie mit einem Hybrid- oder Onlinemandanten verbunden ist. In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn sie ihren Hostinganbieter aktivieren.
    >
    > Wenn Sie vermuten, dass einer Ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder nicht mit einer Online- oder Hybridorganisation verbunden ist, empfehlen wir Ihnen, ihnen eine Entsprechende-Kommunikation zu senden, während Sie sich auf die Durchführung Der Migration in die Cloud vorbereiten.

2.  *Ändern Sie den Koexistenzmodus für Ihre Organisation in Teams Only.* Dadurch wird sichergestellt, dass jeder neue Benutzer in Ihrer Organisation immer als Teams Einziger Benutzer erstellt wird. Außerdem wird bei dem Versuch, den Mandantenmodus in Teams Only zu ändern, automatisch überprüft, ob lokale DNS-Einträge vorhanden sind, die möglicherweise in Schritt 1 übersehen wurden, und diese Einträge in der Ausgabe identifiziert.  Das Ändern des Mandantenmodus in Teams Nur ist erst erfolgreich, wenn alle DNS-Einträge für Ihre Organisation aktualisiert wurden. Um den Mandantenmodus in Teams Führen Sie nur den folgenden Befehl aus einem Teams PowerShell-Fenster aus.

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
Alternativ können Sie das Teams Admin Center verwenden, um den Mandanten-Koexistenzmodus in TeamsOnly unter "Organisationsweite Einstellungen" > "Teams Upgrade" zu ändern.    
    
3.  *Deaktivieren Sie den freigegebenen SIP-Adressraum in Microsoft 365 Organisation.* Der folgende Befehl muss über ein Teams PowerShell-Fenster ausgeführt werden.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  *Deaktivieren Sie die Möglichkeit, lokal mit Microsoft 365 zu kommunizieren.* Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Verwalten von Attributen nach dem Verschieben von Benutzern aus der lokalen Umgebung in die Cloud

Standardmäßig haben alle Benutzer, die zuvor für Skype for Business Server aktiviert und anschließend in die Cloud verschoben wurden, weiterhin msRTCSIP-Attribute in Ihrem lokalen Active Directory konfiguriert. Diese Attribute, insbesondere sip-Adresse (msRTCSIP-PrimaryUserAddress) und potenziell Telefonnummer (msRTCSIP-Line), werden weiterhin mit Azure AD synchronisiert. Wenn Änderungen an einem der msRTCSIP-Attribute erforderlich sind, müssen diese Änderungen im lokalen Active Directory vorgenommen und dann mit Azure AD synchronisiert werden. Nachdem die Skype for Business Server Bereitstellung entfernt wurde, stehen die Skype for Business Server Tools jedoch nicht mehr zum Verwalten dieser Attribute zur Verfügung.

Für diese Situation stehen zwei Optionen zur Verfügung:

1. Lassen Sie Die Benutzer, die für Skype for Business Serverkonten aktiviert waren, so, wie sie sind, und verwalten Sie die MsRTCSIP-Attribute mithilfe von Active Directory-Tools. Dadurch wird kein Dienstverlust für migrierte Benutzer sichergestellt, und Sie können die Skype for Business Server Bereitstellung ganz einfach entfernen, indem Sie die Server entfernen (z. B. zurücksetzen), ohne dass eine vollständige Außerbetriebnahme erfolgt. Neu lizenzierte Benutzer haben diese Attribute jedoch nicht in Ihrem lokalen Active Directory aufgefüllt und müssen online verwaltet werden.

2.  Löschen Sie alle msRTCSIP-Attribute von migrierten Benutzern in Ihrem lokalen Active Directory, und verwalten Sie diese Attribute mithilfe von Onlinetools. Diese Methode ermöglicht einen konsistenten Verwaltungsansatz für vorhandene und neue Benutzer, kann jedoch möglicherweise zu einem vorübergehenden Dienstausfall während der lokalen Außerbetriebnahme führen.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Methode 1 : Verwalten von SIP-Adressen und Telefonnummern für Benutzer in Active Directory

Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch nachdem die lokale Bereitstellung außer Betrieb genommen wurde. Wenn Sie Änderungen an der SIP-Adresse eines Benutzers oder an der Telefonnummer eines Benutzers vornehmen möchten (und die SIP-Adresse oder Telefonnummer bereits einen Wert im lokalen Active Directory aufweist), müssen Sie dies im lokalen Active Directory tun und die Werte bis zu Azure AD fließen lassen. Dies erfordert KEINE lokalen Skype for Business Server. Stattdessen können Sie diese Attribute direkt im lokalen Active Directory mithilfe des MMC-Snap-Ins "Active Directory-Benutzer und -Computer" (wie unten dargestellt) oder mithilfe von PowerShell ändern. Wenn Sie das MMC-Snap-In verwenden, öffnen Sie die Eigenschaftenseite des Benutzers, klicken Sie auf die Registerkarte "Attribut-Editor", und suchen Sie nach den entsprechenden Attributen, die Sie ändern möchten:

- Um die SIP-Adresse eines Benutzers zu ändern, ändern Sie die `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Wenn das `ProxyAddresses` Attribut eine SIP-Adresse enthält, aktualisieren Sie diesen Wert auch als bewährte Methode. Obwohl die SIP-Adresse in `ProxyAddresses` von O365 ignoriert wird, wenn `msRTCSIP-PrimaryUserAddress` sie aufgefüllt ist, kann sie von anderen lokalen Komponenten verwendet werden.

- Wenn Sie die Telefonnummer eines Benutzers ändern möchten, ändern Sie `msRTCSIP-Line` *diese, wenn sie bereits einen Wert aufweist.*

  ![Tool für Active Directory-Benutzer und -Computer](../media/disable-hybrid-1.png)
  
-  Wenn der Benutzer vor der Verschiebung ursprünglich keinen Wert für die lokale Bereitstellung `msRTCSIP-Line` hatte, können Sie die Telefonnummer mithilfe des Parameters - `onpremLineUri` im Cmdlet ["Set-CsUser"](/powershell/module/skype/set-csuser?view=skype-ps) im Skype for Business Online PowerShell-Modul ändern.

Diese Schritte sind für neue Benutzer, die nach dem Deaktivieren der Hybridbereitstellung erstellt wurden, nicht erforderlich, und diese Benutzer können direkt in der Cloud verwaltet werden. Wenn Sie mit der Kombination dieser Methode und dem Verlassen der msRTCSIP-Attribute in Ihrem lokalen Active Directory vertraut sind, können Sie einfach die lokalen Skype for Business Server neu abbilden. Wenn Sie jedoch alle msRTCSIP-Attribute löschen und eine herkömmliche Deinstallation von Skype for Business Server durchführen möchten, verwenden Sie Methode 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Methode 2 – Löschen Skype for Business Attribute für alle lokalen Benutzer in Active Directory

Diese Option erfordert zusätzlichen Aufwand und eine ordnungsgemäße Planung, da Benutzer, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, erneut bereitgestellt werden müssen. Diese Benutzer können in zwei verschiedene Kategorien unterteilt werden: Benutzer ohne Telefonsystem und Benutzer mit Telefonsystem. Bei Benutzern mit Telefonsystem tritt ein vorübergehender Verlust des Telefondiensts im Rahmen des Übergangs der Telefonnummer von der Verwaltung im lokalen Active Directory in die Cloud auf. **Es wird empfohlen, ein Pilotprojekt mit einer kleinen Anzahl von Benutzern mit Telefonsystem durchzuführen, bevor Sie massenweise Benutzervorgänge starten.** Bei großen Bereitstellungen können Benutzer in kleineren Gruppen in verschiedenen Zeitfenstern verarbeitet werden. 

> [!NOTE] 
> Dieser Vorgang ist am einfachsten für Benutzer mit einer übereinstimmenden SIP-Adresse und UserPrincipalName. Für Organisationen, die Benutzer mit nicht übereinstimmenden Werten für diese beiden Attribute haben, muss für einen reibungslosen Übergang besondere Vorsicht geboten werden.

> [!NOTE]
> Wenn Sie lokale Hybridanwendungsendpunkte für automatische Telefonzentralen oder Anrufwarteschleifen konfiguriert haben, müssen Sie diese Endpunkte in Microsoft 365 verschieben, bevor Sie Skype for Business Server außer Betrieb nehmen.


1. Bestätigen Sie die folgende lokale Skype for Business PowerShell-Cmdlet ein leeres Ergebnis zurückgibt. Ein leeres Ergebnis bedeutet, dass keine Benutzer lokal verwaltet werden und entweder in Microsoft 365 verschoben oder deaktiviert wurden:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Notieren Sie die aktuelle Telefonnummer (LineUri), den UserPrincipalName und verwandte Informationen der Benutzer, indem Sie das folgende lokale Skype for Business Server PowerShell-Cmdlet ausführen, um Benutzerdaten zu exportieren:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Öffnen Sie vor dem Öffnen SfbUserSettings.csv Datei, und vergewissern Sie sich, dass alle Benutzerdaten erfolgreich exportiert wurden. Es wird empfohlen, eine Kopie dieser Datei beizubehalten.  Verwenden Sie diese Datei nicht in den folgenden Schritten für die Verarbeitung von Benutzern. 

3. Erstellen Sie eine Datei mit einer Gruppe von Benutzern, die in den folgenden Schritten verwendet werden soll. Nachdem die erste Benutzergruppe erfolgreich abgeschlossen wurde, fahren Sie mit der nächsten Benutzergruppe fort. Im folgenden Beispiel werden die Benutzergruppen alphabetisch ausgewählt, Sie können jedoch nach Benutzern basierend auf Kriterien filtern, die der Art und Weise entsprechen, wie Sie die Benutzer verarbeiten möchten.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Bevor Sie mit dem Öffnen SfbUsers.csv Datei fortfahren und bestätigen, dass Die Benutzerdaten erfolgreich exportiert wurden. Sie benötigen den LineUri (Telefonnummer), UserPrincipalName, SamAccountName und SipAddress in einem späteren Schritt aus dieser Datei.

4. Löschen Sie die Attributinformationen im Zusammenhang mit Skype for Business Server aus Active Directory für die Gruppe von Benutzern, die Sie aktualisieren möchten.  Es gibt zwei Schritte zu diesem Prozess, wie unten dargestellt.

   > [!Important] 
   > Nach dem nächsten AAD Sync Zyklus nach Ausführung dieses Schritts verlieren Benutzer mit Telefonsystem, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, die Möglichkeit, Anrufe zu tätigen und zu empfangen, bis Schritt 8 erfolgreich abgeschlossen und in Schritt 9 bestätigt wurde. Stellen Sie außerdem sicher, dass Sie die Telefonnummern und zugehörigen Informationen des Benutzers gemäß Schritt 2 gespeichert haben, da diese Informationen für diesen Schritt erforderlich sind.

 
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

5. Führen Sie das folgende lokale Active Directory-Modul für Windows PowerShell Cmdlet aus, um den lokalen Active Directory-Proxyadressen einen SIP-Adresswert hinzuzufügen. Dadurch werden Interoperabilitätsprobleme verhindert, die auf diesem Attribut basieren. 

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

6. Ausführen von Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Warten Sie, bis die Benutzerbereitstellung abgeschlossen ist. Sie können den Fortschritt der Benutzerbereitstellung überwachen, indem Sie den folgenden Skype for Business Online PowerShell-Befehl ausführen. Der folgende Skype for Business Online PowerShell-Befehl gibt ein leeres Ergebnis zurück, sobald der Prozess abgeschlossen ist.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Führen Sie den folgenden Skype for Business Online-PowerShell-Befehl aus, um Telefonnummern zuzuweisen und Benutzer für Telefonsystem zu aktivieren:
     
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
   >  Wenn Sie weiterhin Skype for Business Endpunkte haben (entweder Skype Clients oder Telefone von Drittanbietern), sollten Sie auch -HostedVoiceMail auf $true festlegen. Wenn Ihre Organisation nur Teams Endpunkte für sprachfähige Benutzer verwendet, gilt diese Einstellung nicht für Ihre Benutzer. 

9. Vergewissern Sie sich, dass Benutzer mit Telefonsystem Funktionen ordnungsgemäß bereitgestellt wurden. Der folgende Skype for Business Online PowerShell-Befehl gibt ein leeres Ergebnis zurück, sobald der Prozess abgeschlossen ist.

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

    Lokaler Skype for Business Server lokalen PowerShell-Befehl:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Skype for Business Online-PowerShell-Befehl:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. Nachdem Sie alle Schritte in Methode 2 abgeschlossen haben, finden Sie weitere Schritte zum Entfernen ihrer Skype for Business Server lokalen Bereitstellung unter ["Verschieben von hybriden Anwendungsendpunkten von der lokalen](decommission-move-on-prem-endpoints.md) Bereitstellung in die Onlinebereitstellung" und ["Entfernen Ihrer lokalen Skype for Business Server".](decommission-remove-on-prem.md)


## <a name="see-also"></a>Siehe auch

- [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

