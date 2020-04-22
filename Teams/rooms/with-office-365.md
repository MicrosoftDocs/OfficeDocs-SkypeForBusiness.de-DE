---
title: Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365.
ms.openlocfilehash: 02eb5869d7464a4daeece177c4d1b5a5ef440fa0
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780544"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Office 365, in denen Microsoft Teams oder Skype for Business und Exchange Online sind.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht darin, Sie mithilfe der Windows PowerShell-Remotekonfiguration zu konfigurieren. Microsoft bietet [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können. Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.

## <a name="requirements"></a>Voraussetzungen

Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Office 365 bereitstellen. Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).

Damit Sie Skype for Business aktivieren können, müssen Sie über Folgendes verfügen:

- Skype for Business Online (Plan 2 oder ein Unternehmens basierter Plan) oder höher in Ihrem Office 365-Plan. Der Plan muss Funktionen für Einwahlkonferenzen zulassen.

- Wenn Sie in einer Besprechung Einwahl Funktionen benötigen, benötigen Sie eine Audiokonferenz-und Telefon System Lizenz.  Wenn Sie aus einer Besprechung heraus Wählfunktionen benötigen, benötigen Sie eine Audiokonferenz-Lizenz.

- Ihre Mandanten Benutzer müssen über Exchange-Postfächer verfügen.

- Für Ihr Microsoft Teams rooms-Konto ist mindestens eine Lizenz für Skype for Business Online (Plan 2) erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich. Weitere Informationen finden Sie unter [Microsoft Teams rooms-Lizenzen](rooms-licensing.md) .

Einzelheiten zu den Skype for Business Online-Plänen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Standardmäßig verfügen Raumpostfächer nicht über zugeordnete Konten, sodass Sie ein Konto hinzufügen müssen, wenn Sie ein Raumpostfach erstellen oder ändern, das es ermöglicht, sich bei Skype Room Systems v2 zu authentifizieren.

   - Verwenden Sie die folgende Syntax, um ein neues Raumpostfach zu erstellen:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: Project-Rigel-01

     - Alias: ProjectRigel01

     - Konto: ProjectRigel01@contoso.onmicrosoft.com

     - Kontokennwort: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach mit dem Alias Wert ProjectRigel02 aktiviert, und das Kennwort wird auf 9898P@ $ $W 0rd festgelegt. Beachten Sie, dass das Konto aufgrund des vorhandenen Alias Werts ProjectRigel02@contoso.onmicrosoft.com wird.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [festgelegtes Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungs Erfahrung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raum Reservierungs Entscheidung direkt ohne menschliche Intervention: kostenlos = akzeptieren; busy = ablehnen.)

   - AddOrganizerToSubject: $false (der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Text im Nachrichtentext der eingehenden Besprechungsanfragen behalten.)

   - Dem DeleteSubject können: $false (Betreff der eingehenden Besprechungsanfragen beibehalten.)

   - RemovePrivateProperty: $false (stellt sicher, dass das private Flag, das vom Organisator der Besprechung in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (der durch den AdditionalResponse-Parameter angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Stellen Sie eine Verbindung mit MS Online PowerShell her, um Active Directory `Connect-MsolService -Credential $cred` -Einstellungen durch Ausführen des PowerShell-Cmdlets zu erstellen.   Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt. 

5. Wenn Sie nicht möchten, dass das Kennwort abläuft, verwenden Sie die folgende Syntax:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   In diesem Beispiel wird das Kennwort für das Konto ProjectRigel01@contoso.onmicrosoft.com so festgelegt, dass es nie abläuft.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Sie können auch eine Telefonnummer für das Konto einrichten, indem Sie den folgenden Befehl ausführen:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Das Geräte Konto muss über eine gültige Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams oder Skype for Business funktionieren nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Geräte Konto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> So rufen Sie eine Liste der verfügbaren SKUs für Ihre Office 365-Organisation wie folgt ab:

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Als nächstes können Sie eine Lizenz hinzufügen, indem Sie die`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

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

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Als nächstes müssen Sie das Geräte Konto in Skype for Business aktivieren. Stellen Sie sicher, dass Ihre Umgebung die Anforderungen erfüllt, die in den [Microsoft Teams-Chatrooms](requirements.md)festgelegt sind.

   Starten Sie eine [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) -Remotesitzung wie folgt (stellen Sie sicher, dass Sie die [Skype for Business Online PowerShell-Komponenten installieren](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Aktivieren Sie als nächstes das Microsoft Teams rooms-Konto für Skype for Business Server, indem Sie das folgende Cmdlet ausführen:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Beziehen Sie die RegistrarPool-Informationen aus dem neu eingerichteten Benutzerkonto, wie in diesem Beispiel gezeigt:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Neue Benutzerkonten werden möglicherweise nicht im gleichen Registrierungspool wie vorhandene Benutzerkonten im Mandanten erstellt. Der obige Befehl verhindert aufgrund dieser Situation Fehler beim Einrichten des Kontos.

Nachdem Sie die vorstehenden Schritte zum Aktivieren Ihres Microsoft Teams rooms-Kontos in Microsoft Teams oder Skype for Business Online abgeschlossen haben, müssen Sie Microsoft Teams Room-Geräten eine Lizenz zuweisen. Weisen Sie dem Gerät über das Office 365-Verwaltungsportal entweder eine Skype for Business Online (Plan 2) oder eine Skype for Business Online-Lizenz (Plan 3) zu.

### <a name="assign-a-license-to-your-account"></a>Zuweisen einer Lizenz zu Ihrem Konto

1. Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365-Verwaltungs Portal, und klicken Sie auf die Administrator-app.

2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.

3. Wählen Sie das Microsoft Teams rooms-Konto aus, und klicken oder tippen Sie dann auf das Stiftsymbol, was "Bearbeiten" bedeutet.

4. Klicken Sie auf die Option **Lizenzen**.

5. Im Abschnitt **Lizenzen zuweisen** müssen Sie Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3) auswählen – je nach ihrer Lizenzierung und dem, was Sie im Hinblick auf die Notwendigkeit von Enterprise-VoIP entschieden haben. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Cloud PBX in Microsoft Teams-Räumen verwenden möchten. Minimal benötigen Sie CloudPBX für die sprach Konnektivität. Konfigurieren Sie dann Hybrid-sprach-oder PSTN-Anrufe basierend auf der PSTN-Verbindungsmethode. Weitere Informationen finden Sie unter [Microsoft Teams rooms-Lizenzen](rooms-licensing.md) .

6. Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Beispiel: Einrichten des Raum Kontos in Exchange Online und Skype for Business Online

PowerShell-Befehle in Exchange Online:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory PowerShell-Befehle:

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

Skype for Business PowerShell-Befehl:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Dadurch werden CloudPBX und PSTNCallingDomesticAndInternational hinzugefügt. Darüber hinaus müssen Sie die Administratorschnittstelle verwenden, um eine Telefonnummer zuzuweisen.

## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei dem von Ihnen erstellten Konto anzumeldet.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft Teams-Chatrooms](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Lizenzierung von Microsoft Teams rooms](rooms-licensing.md)
