---
title: Bereitstellen Microsoft Teams-Räume mit Exchange lokal
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume in einer Hybridumgebung Exchange lokalen Bereitstellungsumgebung.
ms.openlocfilehash: 35b69e12c38991ecf8ac4d9c0f6f335a097da334
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612984"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange vor Ort

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume in einer Hybridumgebung mit Exchange lokal und Microsoft Teams oder Skype for Business Online.
  
Wenn Ihre Organisation über eine Mischung von Diensten verfügt, von denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. Dieses Thema befasst sich mit Hybridbereitstellungen für Microsoft Teams-Räume mit lokal Exchange lokalen Bereitstellungen. Da es bei diesem Bereitstellungstyp so viele verschiedene Varianten gibt, können keine detaillierten Anweisungen für alle Bereitstellungen zur Verfügung stehen. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfiehlt es sich, Windows PowerShell zu verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, sowie für andere Bereitstellungsoptionen.

Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)- ein Skript zur Unterstützung beim Erstellen neuer Benutzerkonten oder zum Überprüfen vorhandener Ressourcenkonten zur Verwendung in kompatible Microsoft Teams-Räume-Benutzerkonten zur Microsoft Teams-Räume zur Verwendung. Wenn Sie es vorziehen, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die von Ihrem Microsoft Teams-Räume verwendet werden.
  
## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit einem Exchange lokal bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)
  
Wenn Sie Ihre E-Microsoft Teams-Räume mit Exchange lokal bereitstellen, verwenden Sie Active Directory-Verwaltungstools, um eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzuzufügen. Dieses Konto wird mit ihrem Konto Microsoft 365 Konto Office 365. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.

- Weisen Sie eine Microsoft 365 oder Office 365 zu.

- Aktivieren Sie das Gerätekonto mit Skype for Business Server. Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:

  - Sie benötigen Online (Skype for Business Plan 2) oder höher in Ihrem Microsoft 365 oder Office 365 Haben. Der Plan muss die Konferenzfunktion unterstützen.
  
  - Wenn Sie Telefonie Enterprise-VoIP (PSTN-Telefonie) für Telefoniedienstanbieter benötigen Microsoft Teams-Räume sie Skype for Business Online (Plan 3) verwenden.

  - Wenn Sie ein Raumkonto mit Microsoft Teams oder Skype for Business Online konfigurieren, sollte die Telefonnummer zugewiesen werden, bevor das Konto als Konto für den Raum aktiviert wird.
  
  - Ihre Mandantenbenutzer müssen über Exchange verfügen.
  
  - Für Ihr Microsoft Teams-Räume-Konto ist zwar eine Skype for Business Online (Plan 2)- oder Skype for Business Online (Plan 3)-Lizenz erforderlich, es ist jedoch keine Lizenz Exchange Online erforderlich.

- Weisen Sie Skype for Business Server Konto eine Lizenz Microsoft Teams-Räume zu.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

1. Klicken Sie **im Active Directory-Tool** Benutzer und Computer mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in dem Ihre Microsoft Teams-Räume-Konten erstellt werden, klicken Sie auf Neu **und** dann auf **Benutzer.**

2. Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.

3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab** ist eine Voraussetzung für Skype for Business Server auf Microsoft Teams-Räume. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Falls müssen Sie für jedes ihrer Gerätekonto eine Microsoft Teams-Räume erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wechseln Sie nach Abschluss des Vorgangs zur Seite "Benutzer" in Ihrem Microsoft 365 Admin Center und vergewissern Sie sich, dass das in den vorherigen Schritten erstellte Konto mit der Online-Version zusammengeführt wurde.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. [Öffnen Sie die Exchange-Verwaltungsshell,](/powershell/exchange/exchange-server/open-the-exchange-management-shell) oder stellen Sie mithilfe Exchange [PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)eine Verbindung mit Dem Server herzustellen.

2. Erstellen Exchange PowerShell ein Postfach für das Konto (Postfach aktivieren des Kontos), indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. Konfigurieren Exchange in PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Entscheidung über die Raumreservierung direkt ohne Eingreifen eines Menschen: frei = akzeptieren; Beschäftigt = ablehnen.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechung Raum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach Project-Rigel-01 konfiguriert.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365 oder Office 365 Lizenz

1. Verbinden sie Azure Active Directory. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

2. Das Gerätekonto muss über eine gültige Microsoft 365 oder Office 365 verfügen, da Exchange und Microsoft Teams nicht funktionieren. Wenn Sie über eine Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> um eine Liste der verfügbaren SKUs abzurufen.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Aktivieren des Gerätekontos

Skype for Business Online-PowerShell wird zum Verwalten von Diensten für Microsoft Teams und Skype for Business Online verwendet.

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

2. SIP-Adresse des Kontos abrufen:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **Optional.** Wenn Sie dem Konto eine Telefonnummer zuweisen möchten, sollte der Vorgang an diesem Punkt ausgeführt werden. Wenn Sie eine Direct Routing-Telefonnummer zuweisen möchten:

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Wenn Sie eine von Microsoft bereitgestellte Telefonnummer zuweisen möchten, verwenden Sie das cmdlet unten, nachdem Sie dem Benutzer eine Anrufplanlizenz bereitgestellt haben:
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Führen Sie zum Aktivieren Microsoft Teams-Räume Kontos den folgenden Befehl aus:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Wenn Sie nicht sicher sind, welchen Wert Sie für den Parameter RegistrarPool in Ihrer Umgebung verwenden sollen, können Sie den Wert eines vorhandenen Benutzers mit diesem Befehl erhalten:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Zuweisen einer Lizenz zu Ihrem Microsoft Teams-Räume Konto

1. Melden Sie sich als Mandantenadministrator an, öffnen Sie Microsoft 365 Admin Center, und klicken Sie auf die Administrator-App.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie Microsoft Teams-Räume Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie ihr Enterprise-VoIP verwenden Microsoft Teams-Räume.
6. Klicken Sie auf **Speichern**.

Zur Überprüfung sollten Sie in der Lage sein, sich mit jedem Client bei diesem Konto anmelden zu können.
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)