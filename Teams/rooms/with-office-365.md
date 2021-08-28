---
title: Bereitstellen Microsoft Teams-Räume mit Microsoft 365 oder Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Microsoft 365 oder Office 365, wobei Teams oder Skype for Business und Exchange online sind.
ms.openlocfilehash: 91c6b1ecfa12e24daded5f821da44d72084aed72
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615221"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Bereitstellen Microsoft Teams-Räume mit Microsoft 365 oder Office 365

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Microsoft 365 oder Office 365, wobei Microsoft Teams oder Skype for Business und Exchange online verfügbar sind.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht in der Konfiguration mithilfe von Remotecomputern Windows PowerShell. Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)- ein Skript zur Unterstützung beim Erstellen neuer Benutzerkonten oder zum Überprüfen vorhandener Ressourcenkonten zur Verwendung in kompatible Microsoft Teams-Räume-Benutzerkonten zur Microsoft Teams-Räume zur Verwendung. Wenn Es Ihnen lieber ist, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die von Ihrem Microsoft Teams-Räume verwendet werden.

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Microsoft 365 oder Office 365 bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)

Um die Skype for Business zu aktivieren, müssen Sie über Folgendes verfügen:

- Skype for Business Online (Plan 2 oder ein Enterprise-basierter Plan) oder höher in Ihrem Microsoft 365 oder Office 365 Plan. Der Plan muss Einwahlkonferenzfunktionen zulassen.

- Wenn Sie einwahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Audiokonferenz und Telefonsystem Lizenz.  Wenn Sie Auswahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Lizenz für Audiokonferenzen.

- Ihre Mandantenbenutzer müssen über Exchange verfügen.

- Für Ihr Microsoft Teams-Räume-Konto ist mindestens eine Skype for Business Online (Plan 2)-Lizenz erforderlich, es ist jedoch keine Lizenz Exchange Online erforderlich. Weitere [Microsoft Teams-Räume finden Sie unter Verwalten](rooms-licensing.md) von Lizenzen.

Ausführliche Informationen zu Skype for Business Onlineplänen finden Sie in der Skype for Business [Onlinedienstbeschreibung.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)

### <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos

1. Verbinden Sie Exchange Online PowerShell. Anweisungen finden Sie [unter Verbinden zum Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Erstellen Exchange Online in PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Raumpostfächer verfügen standardmäßig nicht über zugeordnete Konten, daher müssen Sie beim Erstellen oder Ändern eines Raumpostfachs, das es ermöglicht, sich mit Skype Room Systems v2 zu authentifizieren, ein Konto hinzufügen.

   - Zum Erstellen eines neuen Raumpostfachs verwenden Sie die folgende Syntax:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: Rigel-01

     - Alias: Rigel1

     - Konto: Rigel1@contoso.onmicrosoft.com

     - Kontokennwort: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie zum Ändern eines vorhandenen Raumpostfachs die folgende Syntax:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert "Rigel2" enthält, und das Kennwort wird auf "9898P@$$W 0rd" festlegen. Beachten Sie, dass das Konto aufgrund Rigel2@contoso.onmicrosoft.com vorhandenen Aliaswerts nicht mehr verwendet werden kann.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

3. Konfigurieren Exchange Online in PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Entscheidung über die Raumreservierung direkt ohne Eingreifen eines Menschen: frei = akzeptieren; Beschäftigt = ablehnen.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechung Raum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach namens Rigel-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Verbinden MS Online PowerShell, um Active Directory-Einstellungen durch Ausführen des `Connect-MsolService -Credential $cred` PowerShell-Cmdlets zu erstellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt.

5. Wenn das Kennwort nicht ablaufen soll, verwenden Sie die folgende Syntax:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   In diesem Beispiel wird das Kennwort für das Konto so Rigel1@contoso.onmicrosoft.com, dass es nie abläuft.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Sie können auch eine Telefonnummer für das Konto festlegen, indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Wenn das Kennwort nicht auf Nie abläuft festgelegt ist, wird das Konto nicht mehr auf dem Gerät anmelden, wenn das Konto den Ablaufzeitraum erreicht. Das Kennwort muss dann für das Konto geändert und auch lokal auf dem MTR-Gerät aktualisiert werden.

6. Das Gerätekonto muss über eine gültige Microsoft 365 oder Office 365 verfügen, oder Exchange und Microsoft Teams oder Skype for Business funktionieren nicht. Wenn Sie über eine Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> um eine Liste der verfügbaren SKUs für Ihre Organisation Microsoft 365 oder Office 365 wie folgt abzurufen:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. In diesem Beispiel wird dem Besprechungsraum die folgende Lizenz hinzufügt:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Sie können diesem Konto Telefonsystem Funktionen hinzufügen, sie müssen sie aber zuerst konfigurieren. Weitere [Informationen finden Sie unter Telefonsystem?.](../what-is-phone-system-in-office-365.md) In diesem Beispiel wird der PSTN-Anrufplan für Inlands- und Auslandsrufe hinzufügt:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > Wenn Sie Ihr Teams-Räume so konfigurieren, dass sie nur systemeigene an Microsoft Teams teilnehmen, sollten Sie nicht mit dem folgenden Schritt fortfahren. Folgendes ist nur erforderlich, wenn Sie auch Unterstützung für lokale Skype for Business aktivieren.

7. Um das Gerätekonto mit einem lokalen Skype for Business zu aktivieren, stellen Sie sicher, dass Ihre Umgebung die in den anforderungen [Microsoft Teams-Räume erfüllt.](requirements.md)

   Starten Sie eine [Remote Windows PowerShell Sitzung](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) wie folgt (stellen Sie sicher, dass Sie Skype for Business [Online-PowerShell-Komponenten installieren):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

   > [!NOTE]
   > Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.
   >
   > Wenn Sie die neueste Version Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto ab, das eingerichtet wird, wie im folgenden Beispiel dargestellt:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Aktivieren Sie als Nächstes Ihr Microsoft Teams-Räume-Konto für Skype for Business Server, indem Sie das folgende Cmdlet ausführen:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Neue Benutzerkonten werden möglicherweise nicht in demselben Registrierungsstellenpool wie vorhandene Benutzerkonten im Mandanten erstellt. Mit dem obigen Befehl werden Fehler bei der Kontoeinrichtung aufgrund dieser Situation verhindert.

## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit Skype for Business-Client bei dem von Ihnen erstellten Konto anmelden.

## <a name="see-also"></a>Mehr dazu

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Microsoft Teams-Räume Lizenzierung](rooms-licensing.md)
