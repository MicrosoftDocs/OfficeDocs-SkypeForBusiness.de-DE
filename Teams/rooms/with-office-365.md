---
title: Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365
ms.author: v-cichur
author: cichur
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365, in denen Teams oder Skype for Business und Exchange Online sind.
ms.openlocfilehash: 4b5bd3967d3a1fcc8859cf4da8b039418819cb4e
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616889"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365, in denen Microsoft Teams oder Skype for Business und Exchange Online sind.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht darin, Sie mithilfe der Windows PowerShell-Remotekonfiguration zu konfigurieren. Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)zur Verfügung, ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können. Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.

## <a name="requirements"></a>Voraussetzungen

Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Microsoft 365 oder Office 365 bereitstellen. Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).

Damit Sie Skype for Business aktivieren können, müssen Sie über Folgendes verfügen:

- Skype for Business Online (Plan 2 oder ein Unternehmens basierter Plan) oder höher in Ihrem Microsoft 365-oder Office 365-Plan. Der Plan muss Funktionen für Einwahlkonferenzen zulassen.

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

     - Name: Rigel-01

     - Alias: Rigel1

     - Konto: Rigel1@contoso.onmicrosoft.com

     - Kontokennwort: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach mit dem Alias Wert Rigel2 aktiviert, und das Kennwort wird auf 9898P@ $ $W 0rd festgelegt. Beachten Sie, dass das Konto aufgrund des vorhandenen Alias Werts Rigel2@contoso.onmicrosoft.com wird.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
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

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Rigel-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Stellen Sie eine Verbindung mit MS Online PowerShell her, um Active Directory-Einstellungen durch Ausführen des `Connect-MsolService -Credential $cred` PowerShell-Cmdlets zu erstellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt.

5. Wenn Sie nicht möchten, dass das Kennwort abläuft, verwenden Sie die folgende Syntax:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   In diesem Beispiel wird das Kennwort für das Konto Rigel1@contoso.onmicrosoft.com so festgelegt, dass es nie abläuft.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Sie können auch eine Telefonnummer für das Konto einrichten, indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Das Geräte Konto muss über eine gültige Microsoft 365-oder Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams oder Skype for Business funktionieren nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Geräte Konto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> So rufen Sie eine Liste der verfügbaren SKUs für Ihre Microsoft 365-oder Office 365-Organisation wie folgt ab:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Als nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet. In diesem Beispiel wird die Besprechungsraum-Lizenz dem Konto hinzugefügt:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

   Sie können diesem Konto auch Telefon System Funktionen hinzufügen, die Sie aber zuerst konfigurieren müssen. Weitere Informationen finden Sie unter [Was ist Telefon System?](../what-is-phone-system-in-office-365.md) . In diesem Beispiel wird der PSTN-Plan für Inlands-und Auslandsanrufe hinzugefügt:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Als nächstes müssen Sie das Geräte Konto in Skype for Business aktivieren. Stellen Sie sicher, dass Ihre Umgebung die Anforderungen erfüllt, die in den [Microsoft Teams-Chatrooms](requirements.md)festgelegt sind.

   Starten Sie eine [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) -Remotesitzung wie folgt (stellen Sie sicher, dass Sie die [Skype for Business Online PowerShell-Komponenten installieren](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Beziehen Sie die RegistrarPool-Informationen aus dem neu eingerichteten Benutzerkonto, wie in diesem Beispiel gezeigt:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Aktivieren Sie als nächstes das Microsoft Teams rooms-Konto für Skype for Business Server, indem Sie das folgende Cmdlet ausführen:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Neue Benutzerkonten werden möglicherweise nicht im gleichen Registrierungspool wie vorhandene Benutzerkonten im Mandanten erstellt. Der obige Befehl verhindert aufgrund dieser Situation Fehler beim Einrichten des Kontos.

## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei dem von Ihnen erstellten Konto anzumeldet.

## <a name="see-also"></a>Weitere Informationen

[Konfigurieren von Konten für Microsoft Teams-Chatrooms](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Lizenzierung von Microsoft Teams rooms](rooms-licensing.md)
