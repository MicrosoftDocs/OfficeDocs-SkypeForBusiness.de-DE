---
title: Bereitstellen Microsoft Teams-Räume mit Exchange lokal (Hybrid)
ms.author: czawideh
author: cazawideh
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
ms.openlocfilehash: 15936a805e45ce17ec35822bb02980b4d47499b8
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355614"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Bereitstellen Microsoft Teams-Räume mit Exchange lokal (Hybrid)

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume in einer Hybridumgebung Exchange lokalen und lokalen Microsoft Teams.
  
Wenn Ihre Organisation über eine Mischung von Diensten verfügt, von denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. In diesem Thema werden Hybridbereitstellungen für Microsoft Teams-Räume mit lokal Exchange lokalen Bereitstellungen behandelt. Da es bei diesem Bereitstellungstyp so viele verschiedene Varianten gibt, können keine detaillierten Anweisungen für alle Bereitstellungen zur Verfügung stehen. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfehlen wir, Windows PowerShell zu verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, sowie für andere Bereitstellungsoptionen.
  
## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Exchange lokal bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)
  
Wenn Sie Eine Microsoft Teams-Räume mit Exchange lokal bereitstellen, verwenden Sie Active Directory-Verwaltungstools, um eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzuzufügen. Dieses Konto wird mit Ihrem Konto Microsoft 365 Konto Office 365. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Azure Active Directory.

- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.

- Weisen Sie eine Microsoft 365 oder Office 365 zu.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>Erstellen eines Kontos und Synchronisieren mit Azure Active Directory

1. Klicken Sie **im Active Directory-Tool** Benutzer und Computer mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in dem Ihre Microsoft Teams-Räume-Konten erstellt werden, klicken Sie auf Neu **und** dann auf **Benutzer.**

2. Geben Sie den Anzeigenamen im Feld **Vollständiger Name** und den Alias in **das** Feld Benutzername ein. Klicken Sie auf **Weiter**.

3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab** ist eine Voraussetzung für Microsoft Teams-Räume. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. Wenn dies derFall ist, müssen Sie eine Ausnahme für jedes einzelne Microsoft Teams-Räume erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wechseln Sie nach Abschluss des Vorgangs zur Seite "Benutzer" in Ihrem Microsoft 365 Admin Center und vergewissern Sie sich, dass das in den vorherigen Schritten erstellte Konto mit online synchronisiert wurde.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. [Öffnen Sie die Exchange-Verwaltungsshell,](/powershell/exchange/exchange-server/open-the-exchange-management-shell) oder stellen Sie mithilfe Exchange [PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)eine Verbindung mit Dem Server herzustellen.

2. Erstellen Exchange in PowerShell ein Postfach für das Konto (Postfach aktivieren des Kontos), indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Enable-Mailbox ConferenceRoom01@contoso.com -Room
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. Konfigurieren Exchange in PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - Automatisieren Der Verarbeitung: AutoAccept (Besprechungsorganisatoren erhalten Entscheidungen zur Raumreservierung direkt ohne Eingreifen des Personals.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist Microsoft Teams Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach namens ConferenceRoom01 konfiguriert.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365 oder Office 365 Lizenz

1. Verbinden sie Azure Active Directory. Details zu den Azure Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

2. Das Ressourcenkonto muss über eine gültige Lizenz Microsoft 365 oder Office 365 verfügen, da Exchange und Microsoft Teams nicht funktionieren. Wenn Sie über eine Lizenz verfügen, müssen Sie Ihrem Ressourcenkonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> um eine Liste der verfügbaren SKUs abzurufen.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

Zur Überprüfung sollten Sie in der Lage sein, sich mit jedem Client bei diesem Konto anmelden zu können.
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
