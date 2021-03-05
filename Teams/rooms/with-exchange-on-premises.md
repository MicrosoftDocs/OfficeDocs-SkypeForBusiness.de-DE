---
title: Bereitstellen von Microsoft Teams-Räumen mit exchange lokal
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams Rooms in einer Hybridumgebung mit Exchange lokal.
ms.openlocfilehash: fcf7216a4fcadee1e81ef11b5310b9d0a88e378a
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460515"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange vor Ort

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams Rooms in einer Hybridumgebung mit Exchange lokal und Microsoft Teams oder Skype for Business Online.
  
Wenn Ihre Organisation über eine Mischung aus Diensten verfügt, bei denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. Dieses Thema befasst sich mit Hybridbereitstellungen für Microsoft Teams-Räume, bei der Exchange lokal gehostet wird. Da es bei dieser Art der Bereitstellung so viele unterschiedliche Varianten gibt, ist es nicht möglich, detaillierte Anweisungen für alle Bereitstellungen zu geben. Der folgende Vorgang funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfehlen wir, Windows PowerShell zu verwenden, um das gleiche Endergebnis wie hier dokumentiert zu erzielen, und für andere Bereitstellungsoptionen.

Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, das beim Erstellen neuer Benutzerkonten hilft, oder vorhandene Ressourcenkonten zu überprüfen, über die Sie verfügen, um sie in kompatible Microsoft Teams Rooms-Benutzerkonten zu verwandeln. Wenn Es Ihnen lieber ist, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die Ihr Microsoft Teams Rooms-Gerät verwendet.
  
## <a name="requirements"></a>Anforderungen

Bevor Sie Microsoft Teams Rooms mit Exchange lokal bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams Rooms-Anforderungen](requirements.md).
  
Wenn Sie Microsoft Teams Rooms mit Exchange lokal bereitstellen, verwenden Sie Active Directory-Verwaltungstools, um eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzuzufügen. Dieses Konto wird mit Microsoft 365 oder Office 365 synchronisiert. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.

- Weisen Sie eine Microsoft 365- oder Office 365-Lizenz zu.

- Aktivieren Sie das Gerätekonto mit Skype for Business Server. Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:

  - Sie benötigen Skype for Business Online (Plan 2) oder höher in Ihrem Microsoft 365- oder Office 365-Plan. Der Plan muss die Konferenzfunktion unterstützen.
  
  - Wenn Sie eine Enterprise-VoIP (PSTN-Telefonie) mit Telefoniedienstanbietern für Microsoft Teams Rooms benötigen, benötigen Sie Skype for Business Online (Plan 3).
  
  - Ihre Mandantenbenutzer müssen über Exchange-Postfächer verfügen.
  
  - Ihr Microsoft Teams Rooms-Konto erfordert zwar eine Lizenz für Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3), erfordert jedoch keine Exchange Online-Lizenz.

- Weisen Sie Ihrem Microsoft Teams Rooms-Konto eine Skype for Business Server-Lizenz zu.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

1. Klicken Sie **im Tool Active Directory-Benutzer** und -Computer mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in dem Ihre Microsoft Teams Rooms-Konten erstellt werden, klicken Sie auf **Neu**, und klicken Sie dann auf **Benutzer**.

2. Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.

3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab,** ist eine Anforderung für Skype for Business Server in Microsoft Teams Rooms. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. Wenn ja, müssen Sie für jedes Microsoft Teams Rooms-Gerätekonto eine Ausnahme erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wenn sie abgeschlossen ist, wechseln Sie zur Benutzerseite in Ihrem Microsoft 365 Admin Center, und vergewissern Sie sich, dass das in den vorherigen Schritten erstellte Konto mit online zusammengeführt wurde.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. [Öffnen Sie die Exchange-Verwaltungsshell,](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) oder stellen Sie eine Verbindung mit [Ihrem Exchange-Server mithilfe von Remote-PowerShell ein.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. Erstellen Sie in Exchange PowerShell ein Postfach für das Konto (postfachaktiviert das Konto), indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Ausführliche Syntax- und Parameterinformationen finden Sie unter [Aktivieren-Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. Konfigurieren Sie in Exchange PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - AutomatisierenVerarbeitung: AutoAccept (Besprechungsorganisatoren erhalten die Raumreservierungsentscheidung direkt ohne menschliches Eingreifen: frei = annehmen; beschäftigt = ablehnen.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie beliebigen Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01 konfiguriert.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Syntax- und Parameterinformationen finden Sie unter [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365- oder Office 365-Lizenz

1. Stellen Sie eine Verbindung mit Azure Active Directory bereit. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 wird](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

2. Das Gerätekonto muss über eine gültige Microsoft 365- oder Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams funktionieren nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Nutzungsspeicherort zuweisen – dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> , um eine Liste der verfügbaren SKUs abzurufen.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

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

   Ausführliche Anweisungen finden Sie unter Zuweisen von Lizenzen [zu Benutzerkonten mit Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Aktivieren des Gerätekontos

Skype for Business Online PowerShell wird zum Verwalten von Diensten für Microsoft Teams und Skype for Business Online verwendet.

1. Erstellen Sie eine Remotesitzung Windows PowerShell pc wie folgt:
> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Abrufen der SIP-Adresse des Kontos:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Führen Sie zum Aktivieren Ihres Microsoft Teams Rooms-Kontos den folgenden Befehl aus:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Wenn Sie nicht sicher sind, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet werden soll, können Sie den Wert von einem vorhandenen Benutzer mit diesem Befehl erhalten:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Zuweisen einer Lizenz zu Ihrem Microsoft Teams Rooms-Konto

1. Melden Sie sich als Mandantenadministrator an, öffnen Sie das Microsoft 365 Admin Center, und klicken Sie auf die Admin-App.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie auf das Microsoft Teams Rooms-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP Microsoft Teams Rooms verwenden möchten.
6. Klicken Sie auf **Speichern**.

Zur Überprüfung sollten Sie jeden Beliebigen Client verwenden können, um sich bei diesem Konto anmelden zu können.
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams Rooms](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
