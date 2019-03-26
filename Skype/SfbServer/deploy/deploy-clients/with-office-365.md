---
title: Bereitstellen von Skype Room Systems v2 mit Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lesen Sie dieses Thema bietet Informationen zum Skype Raum Systemen v2 mit Office 365 bereitstellen.
ms.openlocfilehash: 05288842a54fd8be7487181582fcc7bd4780fd2e
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800124"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Bereitstellen von Skype Room Systems v2 mit Office 365 

Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 mit Office 365, wobei Skype für Unternehmen und Exchange online sind.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten ist von remote Windows PowerShell konfigurieren. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Skype Raum Systemen v2-Benutzerkonten aktivieren überprüfen helfen. Auf Wunsch können Sie die Schritte unten, um Geräts v2 Skype Raum Systemen verwendeten Konten zu konfigurieren.

## <a name="requirements"></a>Voraussetzungen

Bevor Sie Skype Raum Systemen v2 mit Office 365 bereitstellen, müssen Sie unbedingt, dass Sie die Anforderungen erfüllt sind. Weitere Informationen finden Sie unter [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).

Um Skype für Unternehmen zu aktivieren, müssen Sie über Folgendes verfügen:

- Skype für Business Online (Plan 2 oder eines Plans für Enterprise-basierte) oder höher in Ihrem Office 365-Plan. Der Plan muss Funktionen von einwahlkonferenzen können.

- Wenn Sie eine Zugriffsnummer für Einwahl-Funktionen aus einer Besprechung benötigen, benötigen Sie eine Audiokonferenz und Telefonsystem Lizenz.  Wenn Sie Dial-Out-Funktionen aus einer Besprechung benötigen, benötigen Sie eine nationalen oder nationalen und internationalen aufrufen planen.

- Die Mandanten-Benutzer müssen Exchange-Postfächer haben.

- Ihr Skype Raum Systemen v2 Konto erfordert mindestens einen Skype für Business Online (Plan 2)-Lizenz, aber keine Exchange Online-Lizenz erforderlich. Einzelheiten finden Sie unter [Skype Raum Systemen v2-Lizenzierung](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .

Ausführliche Informationen zum Skype für Business Online-Pläne finden Sie unter der [Skype für Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos

1. Herstellen einer Verbindung mit Exchange Online PowerShell. Anweisungen finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. Erstellen Sie in Exchange Online PowerShell eine neue Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Standardmäßig haben nicht raumpostfächer zugeordnete Konten, müssen Sie ein Konto hinzufügen, wenn Sie erstellen oder ändern ein raumpostfachs, das zur Authentifizierung mit Skype Raum Systemen v2 ermöglicht.

   - Verwenden Sie die folgende Syntax, um eine neue Raumpostfach zu erstellen:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird eine neue Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: Project-Rigel-01

     - Alias: ProjectRigel01

     - Konto: ProjectRigel01@contoso.onmicrosoft.com

     - Kennwort: P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Dieses Beispiel aktiviert das Konto für den vorhandenen Raumpostfach, das den Alias-Wert ProjectRigel02 hat, und legt das Kennwort auf 9898P@$$W0rd. Beachten Sie, dass das Konto ProjectRigel02@contoso.onmicrosoft.com aufgrund der vorhandenen Aliaswert.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Informationen zur Syntax und Parametern finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. Konfigurieren Sie die folgenden Einstellungen in Exchange Online PowerShell klicken Sie auf das Raumpostfach, um die Besprechung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren empfangen die Raum Reservierung Entscheidung direkt und ohne Eingreifen: freien = akzeptieren; gebucht = ablehnen.)

   - AddOrganizerToSubject: $false (Organisator der Besprechung wird nicht auf den Betreff der Besprechungsanfrage hinzugefügt.)

   - DeleteComments: $false (beibehalten im Textkörper Nachricht eingehender Besprechungsanfragen.)

   - DeleteSubject: $false (Keep den Betreff der eingehenden Besprechungsanfragen).

   - RemovePrivateProperty: $false (stellt sicher das Flag ' Privat ', die vom Organisator Besprechung in der ursprünglichen Besprechung gesendet wurde anfordern bleibt wie angegeben).

   - AddAdditionalResponse: $true (der Text, durch den Parameter AdditionalResponse angegeben wird auf Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist eine Skype Besprechungsraum!" (Der zusätzliche Text, der auf die Besprechungsanfrage hinzugefügt.)

   In diesem Beispiel wird konfiguriert diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Informationen zur Syntax und Parametern finden Sie unter [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Verbinden mit MS-Online-PowerShell zu Active Directory-Einstellungen durch Ausführen der `Connect-MsolService -Credential $cred` Powershell-Cmdlet.   Ausführliche Informationen zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. Wenn Sie nicht das Kennwort an, die ablaufen soll, verwenden Sie die folgende Syntax:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Dieses Beispiel legt das Kennwort für das Konto ProjectRigel01@contoso.onmicrosoft.com läuft nie ab.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Sie können auch eine Telefonnummer für das Konto festlegen, indem Sie den folgenden Befehl ausführen:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Skype für Unternehmen funktionieren nicht. Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen. Sie können`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Um eine Liste der verfügbaren SKUs wie folgt für Ihre Office 365-Mandanten abzurufen:

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Sie können im nächsten Schritt fügen Sie eine Lizenz using der`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Weitere Informationen finden Sie unter [Zuweisen von Lizenzen, um die Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Als Nächstes müssen Sie das Gerät Konto mit Skype für Unternehmen zu aktivieren. Vergewissern Sie sich, dass Ihre Umgebung den in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md) definierten Anforderungen entspricht.

   Starten Sie einen remote [Windows PowerShell-Sitzung](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) wie folgt (unbedingt [Skype für Business Online-PowerShell-Komponenten zu installieren](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Aktivieren Sie im nächsten Schritt Ihr Skype Raum Systemen v2-Konto für Skype für Business Server durch Ausführen des folgenden Cmdlets:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto-Setup wird, wie im folgenden Beispiel dargestellt:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Neue Benutzerkonten möglicherweise nicht im gleichen Registrar-Pool als vorhandenen Benutzerkonten in den Mandanten erstellt werden. Der vorangehenden Befehl wird verhindert, dass Fehler in kontoeinrichtung aufgrund dieser Situation.

Nachdem Sie die vorhergehenden Schritte zum Aktivieren der Erstellung Ihres Kontos Skype Raum Systemen v2 im Skype für Business Online abgeschlossen haben, müssen Sie Skype Raum Systemen v2 Gerät eine Lizenz zuweisen. Verwenden das administrative Office 365-Portal, weisen Sie entweder einen Skype für Business Online (Plan 2) oder eine Skype für Business Online (Plan 3)-Lizenz auf das Gerät.

### <a name="assign-a-license-to-your-account"></a>Zuweisen einer Lizenz zu Ihrem Konto

1. Anmeldung als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.

2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.

3. Wählen Sie das Konto Skype Raum Systemen v2, und klicken Sie auf, oder tippen Sie auf das Stiftsymbol, das Möglichkeit zu bearbeiten.

4. Klicken Sie auf die Option **Lizenzen**.

5. Klicken Sie im Abschnitt **Lizenzen zuweisen** müssen Sie Skype für Business Online (Plan 2) oder Skype auswählen, für Business Online (Plan 3), je nach Ihrer Lizenzierung und was Sie entschieden haben, im Hinblick auf Enterprise-VoIP benötigen. Sie müssen eine Lizenz planen 3 verwenden, wenn Sie auf Skype Raum Systemen v2 Cloud Nebenstellenanlage verwenden möchten. Minimal benötigen Sie CloudPBX für VoIP-Konnektivität. Konfigurieren Sie anschließend Hybrid-VoIP oder PSTN-Basis für die PSTN-Konnektivität-Methode aufrufen. Einzelheiten finden Sie unter [Skype Raum Systemen v2 Lizenzen](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .

6. Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Beispiel: Raum setup im Exchange Online und Skype für Business Online

Exchange Online PowerShell-Befehle:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory-PowerShell-Befehle:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Skype für Business-PowerShell-Befehl:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Dadurch werden CloudPBX und PSTNCallingDomesticAndInternational hinzugefügt. Darüber hinaus müssen Sie die Admin-Benutzeroberfläche verwenden, um eine Telefonnummer zuweisen.

## <a name="validate"></a>Überprüfen

Für die Validierung sollten Sie möglicherweise Skype für Business-Client verwenden, das Konto anmelden, die Sie erstellt haben.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Skype Raum Systemen v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Bereitstellen von Skype Room Systems v2](room-systems-v2.md)

[Konfigurieren einer Konsole für Skype Room Systems v2](console.md)

[Verwalten von Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Skype-Raum Systemen v2 Lizenzierung](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
