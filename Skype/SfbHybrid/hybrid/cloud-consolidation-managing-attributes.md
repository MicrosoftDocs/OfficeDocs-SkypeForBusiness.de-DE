---
title: Entscheiden, wie Attribute nach der Außerbetriebnahme verwaltet werden sollen
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
ms.localizationpriority: medium
description: In diesem Artikel wird beschrieben, wie Sie Attribute nach der Außerbetriebnahme Ihrer lokalen Umgebung verwalten.
ms.openlocfilehash: 9f78dbcfaf1c753d18cc2e85a6b209248c2feea8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636896"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Entscheiden, wie Attribute nach der Außerbetriebnahme verwaltet werden sollen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Standardmäßig haben alle Benutzer, die zuvor für Skype for Business Server aktiviert und anschließend in die Cloud verschoben wurden, weiterhin msRTCSIP-Attribute in Ihrem lokalen Active Directory konfiguriert. 

Diese Attribute, insbesondere sip-Adresse (msRTCSIP-PrimaryUserAddress) und potenziell Telefonnummer (msRTCSIP-Line), werden weiterhin mit Azure AD synchronisiert. Wenn Änderungen an einem der msRTCSIP-Attribute erforderlich sind, müssen diese Änderungen im lokalen Active Directory vorgenommen und dann mit Azure AD synchronisiert werden. Nachdem die Skype for Business Server Bereitstellung entfernt wurde, stehen die Skype for Business Server Tools jedoch nicht mehr zum Verwalten dieser Attribute zur Verfügung.

Für diese Situation stehen zwei Optionen zur Verfügung:

1. Lassen Sie Die Benutzer, die für Skype for Business Serverkonten aktiviert waren, so, wie sie sind, und verwalten Sie die MsRTCSIP-Attribute mithilfe von Active Directory-Tools. Dies stellt keinen Dienstverlust für migrierte Benutzer sicher und ermöglicht es Ihnen, die Skype for Business Server Bereitstellung ganz einfach zu entfernen, indem Sie die Server entfernen (z. B. zurücksetzen), ohne dass eine vollständige Außerbetriebnahme erfolgt. Neu lizenzierte Benutzer haben diese Attribute jedoch nicht in Ihrem lokalen Active Directory aufgefüllt und müssen online verwaltet werden.

2.  Löschen Sie alle msRTCSIP-Attribute von migrierten Benutzern in Ihrem lokalen Active Directory, und verwalten Sie diese Attribute mithilfe von Onlinetools. Diese Methode ermöglicht einen konsistenten Verwaltungsansatz für vorhandene und neue Benutzer, kann jedoch möglicherweise zu einem vorübergehenden Dienstausfall während der lokalen Außerbetriebnahme führen.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Methode 1 : Verwalten von SIP-Adressen und Telefonnummern für Benutzer in Active Directory

Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch nachdem die lokale Bereitstellung außer Betrieb genommen wurde. 

Wenn Sie Änderungen an der SIP-Adresse eines Benutzers oder an der Telefonnummer eines Benutzers vornehmen möchten (und die SIP-Adresse oder Telefonnummer bereits einen Wert im lokalen Active Directory aufweist), müssen Sie dies im lokalen Active Directory tun und die Werte bis zu Azure AD fließen lassen. Dies erfordert KEINE lokale Skype for Business Server. Stattdessen können Sie diese Attribute direkt im lokalen Active Directory mithilfe des MMC-Snap-Ins "Active Directory-Benutzer und -Computer" (wie unten dargestellt) oder mithilfe von PowerShell ändern. Wenn Sie das MMC-Snap-In verwenden, öffnen Sie die Eigenschaftenseite des Benutzers, klicken Sie auf die Registerkarte "Attribut-Editor", und suchen Sie nach den entsprechenden Attributen, die Sie ändern möchten:

- Um die SIP-Adresse eines Benutzers zu ändern, ändern Sie die `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Wenn das `ProxyAddresses` Attribut eine SIP-Adresse enthält, aktualisieren Sie diesen Wert auch als bewährte Methode. Obwohl die SIP-Adresse in `ProxyAddresses` von O365 ignoriert wird, wenn `msRTCSIP-PrimaryUserAddress` sie aufgefüllt ist, kann sie von anderen lokalen Komponenten verwendet werden.

- Wenn Sie die Telefonnummer eines Benutzers ändern möchten, ändern Sie `msRTCSIP-Line` *diese, wenn sie bereits einen Wert aufweist.*

  ![Tool für Active Directory-Benutzer und -Computer](../media/disable-hybrid-1.png)
  
-  Wenn der Benutzer vor der Verschiebung ursprünglich keinen Wert für die lokale Bereitstellung `msRTCSIP-Line` hatte, können Sie die Telefonnummer mithilfe des Parameters - `onpremLineUri` im Cmdlet ["Set-CsUser"](/powershell/module/skype/set-csuser?view=skype-ps) im Teams PowerShell-Modul ändern.

Diese Schritte sind für neue Benutzer, die nach dem Deaktivieren der Hybridbereitstellung erstellt wurden, nicht erforderlich, und diese Benutzer können direkt in der Cloud verwaltet werden. Wenn Sie mit der Kombination dieser Methode vertraut sind und die MsRTCSIP-Attribute in Ihrem lokalen Active Directory verbleiben, können Sie einfach die lokalen Skype for Business Server neu abbilden. Wenn Sie jedoch lieber alle msRTCSIP-Attribute löschen und eine herkömmliche Deinstallation von Skype for Business Server durchführen möchten, verwenden Sie Methode 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Methode 2 – Löschen Skype for Business Attribute für alle lokalen Benutzer in Active Directory

Diese Option erfordert zusätzlichen Aufwand und eine ordnungsgemäße Planung, da Benutzer, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, erneut bereitgestellt werden müssen. Diese Benutzer können in zwei verschiedene Kategorien unterteilt werden: Benutzer ohne Telefonsystem und Benutzer mit Telefonsystem. Bei Benutzern mit Telefonsystem tritt ein vorübergehender Verlust des Telefondiensts im Rahmen des Übergangs der Telefonnummer von der Verwaltung im lokalen Active Directory in die Cloud auf. **Es wird empfohlen, ein Pilotprojekt mit einer kleinen Anzahl von Benutzern mit Telefonsystem durchzuführen, bevor Sie massenweise Benutzervorgänge starten.** Bei großen Bereitstellungen können Benutzer in kleineren Gruppen in verschiedenen Zeitfenstern verarbeitet werden. 

> [!NOTE] 
> Dieser Vorgang ist am einfachsten für Benutzer mit einer übereinstimmenden SIP-Adresse und UserPrincipalName. Für Organisationen, die Benutzer mit nicht übereinstimmenden Werten für diese beiden Attribute haben, muss für einen reibungslosen Übergang besondere Vorsicht geboten werden.

> [!NOTE]
> Wenn Sie lokale Hybridanwendungsendpunkte für automatische Telefonzentralen oder Anrufwarteschleifen konfiguriert haben, müssen Sie diese Endpunkte vor der Außerbetriebnahme Skype for Business Server in Microsoft 365 verschieben. Ausführliche Informationen finden Sie unter [Migrieren von Hybridanwendungsendpunkten vor der Außerbetriebnahme Ihrer lokalen Umgebung.](decommission-move-on-prem-endpoints.md)  


1. Bestätigen Sie die folgende lokale Skype for Business PowerShell-Cmdlet ein leeres Ergebnis zurückgibt. Ein leeres Ergebnis bedeutet, dass keine Benutzer lokal verwaltet werden und entweder in Microsoft 365 verschoben oder deaktiviert wurden:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Notieren Sie die aktuelle Telefonnummer (LineUri), den UserPrincipalName und verwandte Informationen der Benutzer, indem Sie das folgende lokale Skype for Business Server PowerShell-Cmdlet ausführen, um Benutzerdaten zu exportieren:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Bevor Sie mit dem Öffnen SfbUserSettings.csv Datei fortfahren und bestätigen, dass alle Benutzerdaten erfolgreich exportiert wurden. Es wird empfohlen, eine Kopie dieser Datei beizubehalten.  Verwenden Sie diese Datei nicht in den folgenden Schritten für die Verarbeitung von Benutzern. 

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

7. Warten Sie, bis die Benutzerbereitstellung abgeschlossen ist. Sie können den Fortschritt der Benutzerbereitstellung überwachen, indem Sie den folgenden Teams PowerShell-Befehl ausführen. Der folgende Teams PowerShell-Befehl gibt ein leeres Ergebnis zurück, sobald der Vorgang abgeschlossen ist.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Führen Sie den folgenden Teams PowerShell-Befehl aus, um Telefonnummern zuzuweisen und Benutzer für Telefonsystem zu aktivieren:
     
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

9. Vergewissern Sie sich, dass Benutzer mit Telefonsystem Funktionen ordnungsgemäß bereitgestellt wurden. Der folgende Teams PowerShell-Befehl gibt ein leeres Ergebnis zurück, sobald der Vorgang abgeschlossen ist.

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

11. Stellen Sie sicher, dass alle Benutzer erfolgreich verarbeitet wurden, indem Sie die folgenden beiden PowerShell-Befehle ausführen.

    Lokale Skype for Business Server lokalen PowerShell-Befehl:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell-Befehl:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. Nachdem Sie alle Schritte in Methode 2 abgeschlossen haben, finden Sie weitere Schritte zum Entfernen der Skype for Business Server lokalen Bereitstellung unter ["Verschieben von hybriden Anwendungsendpunkten von der lokalen](decommission-move-on-prem-endpoints.md) Bereitstellung in die Onlinebereitstellung" und ["Entfernen Ihrer lokalen Skype for Business Server".](decommission-remove-on-prem.md)


## <a name="see-also"></a>Siehe auch

- [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

