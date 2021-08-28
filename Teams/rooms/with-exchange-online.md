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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Exchange Online und Skype for Business Server lokal.
ms.openlocfilehash: e1331526660b928b49beeebf2e70e2552afdacd8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636659"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange online

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Exchange Online und Skype for Business Server lokal.
  
Wenn Ihre Organisation über eine Mischung von Diensten verfügt, von denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. In diesem Thema werden Hybridbereitstellungen für Microsoft Teams-Räume mit online Exchange Bereitstellung behandelt. Da es bei diesem Bereitstellungstyp so viele verschiedene Varianten gibt, können keine detaillierten Anweisungen für alle Bereitstellungen zur Verfügung stehen. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfiehlt es sich, Windows PowerShell zu verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, sowie für andere Bereitstellungsoptionen.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht in der Konfiguration mithilfe von Remotecomputern Windows PowerShell. Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)- ein Skript zur Unterstützung beim Erstellen neuer Benutzerkonten oder zum Überprüfen vorhandener Ressourcenkonten zur Verwendung in kompatible Microsoft Teams-Räume-Benutzerkonten zur Microsoft Teams-Räume zur Verwendung. Wenn Es Ihnen lieber ist, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die von Ihrem Microsoft Teams-Räume verwendet werden.

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Exchange Online bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)
  
Führen Sie die Microsoft Teams-Räume mit Exchange Online aus. Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen. 

   > [!NOTE]
   >  Das Azure Active Directory-Modul für [Windows PowerShell-Cmdlets](/powershell/azure/active-directory/overview) in diesem Abschnitt (z. B. Set-MsolUser) wurde unter Einrichten von Konten für Microsoft Teams-Räume getestet. Es ist möglich, dass andere Cmdlets funktionieren, aber in diesem speziellen Szenario noch nicht getestet wurden.

Wenn Sie Active Directory-Verbunddienste (AD FS) bereitgestellt haben, müssen Sie das Benutzerkonto möglicherweise in einen verwalteten Benutzer konvertieren, bevor Sie diese Schritte ausführen, und dann den Benutzer wieder in einen Partnerbenutzer konvertieren, nachdem Sie diese Schritte abgeschlossen haben.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften

1. Starten Sie eine Windows PowerShell-Sitzung auf einem PC, und stellen Sie wie folgt eine Exchange Online Verbindung mit dem Computer dar:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount oder ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann sich das Konto bei ihrem Konto Microsoft Teams-Räume.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Um die Besprechungserfahrung zu verbessern, müssen Sie die Eigenschaften Exchange Benutzerkonto wie folgt festlegen:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto

1. Klicken **Sie im Active Directory-Ad-Tool** Benutzer und Computer mit der rechten Maustaste auf den Container oder die Organisationseinheit, in dem Ihre Microsoft Teams-Räume-Konten erstellt werden, klicken Sie auf Neu und dann auf **Benutzer.** 
2. Geben Sie den Anzeigenamen (- Identity) aus dem vorherigen Cmdlet  (Set-Mailbox oder New-Mailbox) in das Feld Vollständiger Name und den Alias in das Feld **Benutzeranmeldungsname** ein. Klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab** ist eine Voraussetzung für Skype for Business Server auf Microsoft Teams-Räume. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Falls müssen Sie für jedes einzelne Benutzerkonto Microsoft Teams-Räume erstellen.
  
4. Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.
5. Nachdem Sie das Konto erstellt haben, führen Sie eine Verzeichnissynchronisierung aus. Dies kann mithilfe von [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) in PowerShell erreicht werden. Wechseln Sie nach Abschluss des Vorgangs zur Seite Benutzer, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365 oder Office 365 Lizenz

1. Stellen Sie zunächst eine Verbindung mit Azure AD bereit, um einige Kontoeinstellungen anzuwenden. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview) nicht unterstützt.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Das Benutzerkonto muss über eine gültige Lizenz Microsoft 365 oder Office 365 verfügen, um sicherzustellen, dass Exchange und Skype for Business Server funktionieren. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Benutzerkonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie nehmen die Aufgabe in einem folgenden Schritt vor.
3. Verwenden Sie als Nächstes `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> um eine Liste der verfügbaren SKUs für Ihre Organisation Microsoft 365 oder Office 365 abzurufen.
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

> [!NOTE]
> Wenn Sie ihr Konto nur für Teams-Räume Besprechungen Microsoft Teams möchten, müssen Sie nicht die folgenden Schritte ausführen. Die folgenden Schritte sind nur erforderlich, wenn Sie die Unterstützung für ihre Skype for Business.

1. Erstellen Sie eine Windows PowerShell Sitzung von einem PC aus wie folgt:

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

2. Führen Sie zum Aktivieren Microsoft Teams-Räume Kontos für Skype for Business Server folgenden Befehl aus:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Wenn Sie nicht sicher sind, welchen Wert Sie für den Parameter RegistrarPool in Ihrer Umgebung verwenden sollen, können Sie den Wert eines vorhandenen Benutzers Skype for Business Server mit diesem Befehl erhalten.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Zuweisen einer Skype for Business Server Lizenz zu Ihrem Microsoft Teams-Räume Konto

> [!NOTE]
> Wenn Sie ihr Konto nur für Teams-Räume Besprechungen Microsoft Teams möchten, müssen Sie nicht die folgenden Schritte ausführen. Die folgenden Schritte sind nur erforderlich, wenn Sie die Unterstützung für ihre Skype for Business.

1. Melden Sie sich als Mandantenadministrator an, öffnen Sie Microsoft 365 Admin Center, und klicken Sie auf die Administrator-App.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie Microsoft Teams-Räume Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie ihr Konto auf Enterprise-VoIP Microsoft Teams-Räume.
6. Klicken Sie auf **Speichern**.

Zur Überprüfung sollten Sie in der Lage sein, sich mit Skype for Business-Client bei diesem Konto anmelden.

> [!NOTE]
> Wenn Sie derzeit E1-, E3-, E4- oder E5-SKUs mit Skype for Business Plan 2 mit Audiokonferenzen oder mit Telefonsystem und einem Anrufplan verwenden, funktionieren diese weiterhin. Sie sollten jedoch erwägen, nach Ablauf der aktuellen Lizenzen zu einem einfacheren Lizenzierungsmodell zu Teams Besprechungsraum [Lizenzierungsupdate](rooms-licensing.md)zu verwenden.

> [!IMPORTANT]
> Wenn Sie Skype for Business Plan 2 verwenden, können Sie den Microsoft Teams-Räume nur im Skype for Business-Modus verwenden, was bedeutet, dass alle Ihre Besprechungen Skype for Business sind. Um Ihren Besprechungsraum für Besprechungen Microsoft Teams zu aktivieren, empfehlen wir, die Lizenz Besprechungsraum erwerben.
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
