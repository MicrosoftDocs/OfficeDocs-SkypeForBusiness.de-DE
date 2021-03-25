---
title: Bereitstellen von Microsoft Teams-Raum mit Exchange online
ms.author: dstrome
author: dstrome
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: In diesem Thema erfahren Sie, wie Sie Microsoft Teams Rooms mit Exchange Online und Skype for Business Server lokal bereitstellen.
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117343"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange online

In diesem Thema erfahren Sie, wie Sie Microsoft Teams Rooms mit Exchange Online und Skype for Business Server lokal bereitstellen.
  
Wenn Ihre Organisation über eine Mischung aus Diensten verfügt, bei denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. Dieses Thema befasst sich mit Hybridbereitstellungen für Microsoft Teams-Räume, bei der Exchange online gehostet wird. Da es bei dieser Art der Bereitstellung so viele unterschiedliche Varianten gibt, ist es nicht möglich, detaillierte Anweisungen für alle Bereitstellungen zu geben. Der folgende Vorgang funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfehlen wir, Windows PowerShell zu verwenden, um das gleiche Endergebnis wie hier dokumentiert zu erzielen, und für andere Bereitstellungsoptionen.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht in der Konfiguration mithilfe von Remotekonten Windows PowerShell. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, das beim Erstellen neuer Benutzerkonten hilft, oder vorhandene Ressourcenkonten zu überprüfen, über die Sie verfügen, um sie in kompatible Microsoft Teams Rooms-Benutzerkonten zu verwandeln. Wenn Es Ihnen lieber ist, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die Ihr Microsoft Teams Rooms-Gerät verwendet.

## <a name="requirements"></a>Anforderungen

Stellen Sie vor der Bereitstellung von Microsoft Teams Rooms mit Exchange Online sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams Rooms-Anforderungen](requirements.md).
  
Zum Bereitstellen von Microsoft Teams Rooms mit Exchange Online führen Sie die folgenden Schritte aus. Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen. 

   > [!NOTE]
   >  Das [Azure Active Directory-Modul für Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in diesem Abschnitt (z. B. Set-MsolUser) wurde beim Einrichten von Konten für Microsoft Teams Rooms-Geräte getestet. Es ist möglich, dass andere Cmdlets funktionieren, aber sie wurden in diesem speziellen Szenario noch nicht getestet.

Wenn Sie Active Directory Federation Services (AD FS) bereitgestellt haben, müssen Sie das Benutzerkonto möglicherweise in einen verwalteten Benutzer konvertieren, bevor Sie diese Schritte ausführen, und den Benutzer dann nach Abschluss dieser Schritte wieder in einen Verbundbenutzer konvertieren.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften

1. Starten Sie eine Remotesitzung Windows PowerShell PC, und stellen Sie eine Verbindung mit Exchange Online wie folgt dar:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Nachdem Sie eine Sitzung erstellt haben, erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann sich das Konto bei Microsoft Teams Rooms authentifizieren.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Um die Besprechungserfahrung zu verbessern, müssen Sie die Exchange-Eigenschaften für das Benutzerkonto wie folgt festlegen:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto

1. Klicken **Sie im Active Directory-Tool** Benutzer und Computer ad mit der rechten Maustaste auf den Container oder die Organisationseinheit, in dem Ihre Microsoft Teams Rooms-Konten erstellt werden, klicken Sie auf **Neu**, und klicken Sie dann auf **Benutzer**.
2. Geben Sie den Anzeigenamen (- Identität) aus dem **vorherigen** Cmdlet  (Set-Mailbox oder New-Mailbox) in das Feld Vollständiger Name und den Alias in das Feld Benutzername ein. Klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab,** ist eine Anforderung für Skype for Business Server in Microsoft Teams Rooms. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. Wenn ja, müssen Sie für jedes Microsoft Teams Rooms-Benutzerkonto eine Ausnahme erstellen.
  
4. Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.
5. Nachdem Sie das Konto erstellt haben, führen Sie eine Verzeichnissynchronisierung aus. Dies kann mithilfe von [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell erreicht werden. Wenn dies abgeschlossen ist, wechseln Sie zur Benutzerseite, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365- oder Office 365-Lizenz

1. Stellen Sie zunächst eine Verbindung mit Azure AD bereit, um einige Kontoeinstellungen anzuwenden. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 wird](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Das Benutzerkonto muss über eine gültige Microsoft 365- oder Office 365-Lizenz verfügen, um sicherzustellen, dass Exchange und Skype for Business Server funktionieren. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Benutzerkonto einen Nutzungsspeicherort zuweisen – dadurch wird bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie nehmen die Aufgabe in einem folgenden Schritt vor.
3. Verwenden Sie als Nächstes `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> , um eine Liste der verfügbaren SKUs für Ihre Microsoft 365- oder Office 365-Organisation abzurufen.
4. Nachdem Sie die SKUs aufgeführt haben, können Sie eine Lizenz hinzufügen, indem Sie `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Aktivieren des Benutzerkontos mit Skype for Business Server

1. Erstellen Sie eine Remotesitzung Windows PowerShell pc wie folgt:

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. Führen Sie zum Aktivieren Ihres Microsoft Teams Rooms-Kontos für Skype for Business Server den folgenden Befehl aus:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Wenn Sie nicht sicher sind, welchen Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet werden soll, können Sie den Wert von einem vorhandenen Skype for Business Server-Benutzer mit diesem Befehl erhalten.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Zuweisen einer Skype for Business Server-Lizenz zu Ihrem Microsoft Teams Rooms-Konto

1. Melden Sie sich als Mandantenadministrator an, öffnen Sie das Microsoft 365 Admin Center, und klicken Sie auf die Admin-App.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie auf das Microsoft Teams Rooms-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP Microsoft Teams Rooms verwenden möchten.
6. Klicken Sie auf **Speichern**.

Zur Überprüfung sollten Sie einen beliebigen Skype for Business-Client verwenden können, um sich bei diesem Konto zu anmelden.

> [!NOTE]
> Wenn Sie derzeit E1-, E3-, E4- oder E5-SKUs mit Skype for Business Plan 2 mit Audiokonferenzen oder mit Telefonsystem und einem Anrufplan verwenden, funktionieren diese weiterhin. Nach Ablauf der aktuellen Lizenzen sollten Sie jedoch einen Wechsel zu einem einfacheren Lizenzierungsmodell in Erwägung ziehen, wie unter Updates zur Lizenzierung von Besprechungsraums in [Teams](rooms-licensing.md)beschrieben.

> [!IMPORTANT]
> Wenn Sie Skype for Business Plan 2 verwenden, können Sie nur die Microsoft Teams-Räume im Skype for Business Only-Modus verwenden, d. h., alle Ihre Besprechungen sind Skype for Business-Besprechungen. Um Ihren Besprechungsraum für Microsoft Teams-Besprechungen zu aktivieren, empfiehlt es sich, die Lizenz für den Besprechungsraum zu erwerben.
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams Rooms](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)