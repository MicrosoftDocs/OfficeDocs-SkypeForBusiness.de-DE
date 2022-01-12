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
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767228"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Bereitstellen Microsoft Teams-Räume mit Exchange lokal (Hybrid)

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume in einer Hybridumgebung mit Exchange lokalen und lokalen Microsoft Teams.
  
Wenn Ihre Organisation über eine Mischung von Diensten verfügt, von denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. In diesem Thema werden Hybridbereitstellungen für Microsoft Teams-Räume mit lokal gehosteten Exchange behandelt. Da es bei diesem Bereitstellungstyp so viele verschiedene Varianten gibt, können keine detaillierten Anweisungen für alle Bereitstellungen zur Verfügung stehen. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfehlen wir, Windows PowerShell zu verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, sowie für andere Bereitstellungsoptionen.
  
## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Exchange lokal bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. [Öffnen Sie die Exchange-Verwaltungsshell,](/powershell/exchange/exchange-server/open-the-exchange-management-shell) oder stellen Sie mithilfe Exchange [PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)eine Verbindung mit Dem Server herzustellen.

2. Erstellen Exchange in PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Raumpostfächer verfügen standardmäßig nicht über zugeordnete Konten, daher müssen Sie beim Erstellen oder Ändern eines Raumpostfachs, das es ermöglicht, sich bei anderen Benutzern zu authentifizieren, ein Konto Microsoft Teams.

   - Zum Erstellen eines neuen Raumpostfachs verwenden Sie die folgende Syntax:

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Konto: ConferenceRoom01@contoso.com
  
     - Name: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Kontokennwort: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie zum Ändern eines vorhandenen Raumpostfachs die folgende Syntax:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert ConferenceRoom02 hat, und das Kennwort auf 9898P@$$W 0rd. Beachten Sie, dass das Konto aufgrund ConferenceRoom02@contoso.com vorhandenen Aliaswerts nicht mehr verwendet wird.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

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

### <a name="set-password-to-never-expire"></a>Festlegen, dass das Kennwort nie abläuft

1. Suchen Sie **im Active Directory-Tool** Benutzer und Computer nach dem Microsoft Teams-Räume, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Eigenschaften aus.**

2. Aktivieren Sie **das Kontrollkästchen Kennwort läuft nie ab,** und klicken Sie dann auf **OK.**

   > [!NOTE]
   > Die **Auswahl von Kennwort läuft nie ab** ist eine Voraussetzung für Microsoft Teams-Räume. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Falls müssen Sie für jedes einzelne Konto eine Microsoft Teams-Räume erstellen.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365 oder Office 365 Lizenz

1. Verbinden zu Azure Active Directory. Details zu den Azure Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

2. Das Ressourcenkonto muss über eine gültige Lizenz Microsoft 365 oder Office 365 verfügen, da Exchange und Microsoft Teams nicht funktionieren. Wenn Sie über eine Lizenz verfügen, müssen Sie Ihrem Ressourcenkonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> um eine Liste der verfügbaren SKUs abzurufen.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. In diesem Beispiel wird Besprechungsraum-Lizenz dem Konto hinzufügt:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

Zur Überprüfung sollten Sie in der Lage sein, sich mit jedem Client bei diesem Konto anmelden zu können.
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
