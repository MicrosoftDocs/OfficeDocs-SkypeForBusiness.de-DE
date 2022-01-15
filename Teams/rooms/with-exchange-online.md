---
title: Bereitstellen von Microsoft Teams-Raum mit Exchange online
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Exchange Online.
ms.openlocfilehash: e6eb3253d7edb999ba74d28ef9a6d8ae835ac16d
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055485"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange online

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Exchange Online.
  
Wenn Ihre Organisation über eine Mischung von Diensten verfügt, von denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. Dieses Thema befasst sich mit Hybridbereitstellungen für Microsoft Teams-Räume mit Exchange online gehosteten Bereitstellungen. Da es bei diesem Bereitstellungstyp so viele verschiedene Varianten gibt, können keine detaillierten Anweisungen für alle Bereitstellungen zur Verfügung stehen. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfiehlt es sich, Windows PowerShell zu verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, sowie für andere Bereitstellungsoptionen.

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Exchange Online bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)
  
Zum Bereitstellen Microsoft Teams-Räume mit Exchange Online, führen Sie die folgenden Schritte aus. Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der Cmdlets verfügen. 

   > [!NOTE]
   >  Das Azure Active Directory-Modul für [Windows PowerShell-Cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in diesem Abschnitt (z. B. Set-MsolUser) wurde unter Einrichten von Konten für Microsoft Teams-Räume. Es ist möglich, dass andere Cmdlets funktionieren, aber in diesem speziellen Szenario noch nicht getestet wurden.

Wenn Sie Active Directory-Verbunddienste (AD FS) bereitgestellt haben, müssen Sie das Benutzerkonto möglicherweise in einen verwalteten Benutzer konvertieren, bevor Sie diese Schritte ausführen, und dann den Benutzer wieder in einen Partnerbenutzer konvertieren, nachdem Sie diese Schritte abgeschlossen haben.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften

1. Starten Sie eine Windows PowerShell-Sitzung auf einem PC, und stellen Sie wie folgt eine Exchange Online Verbindung mit dem Computer dar:

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann sich das Konto bei ihrem Konto Microsoft Teams-Räume.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Um die Besprechungserfahrung zu verbessern, müssen Sie die Eigenschaften Exchange Benutzerkonto wie folgt festlegen:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto

1. Klicken **Sie im Active Directory-Ad-Tool** Benutzer und Computer mit der rechten Maustaste auf den Container oder die Organisationseinheit, in dem Ihre Microsoft Teams-Räume-Konten erstellt werden, klicken Sie auf Neu und dann auf **Benutzer.** 
2. Geben Sie den Anzeigenamen (- Identity) aus dem vorherigen Cmdlet  (Set-Mailbox oder New-Mailbox) in das Feld Vollständiger Name und den Alias in das Feld **Benutzeranmeldungsname** ein. Klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab** ist eine Voraussetzung für Microsoft Teams-Räume. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Falls müssen Sie für jedes einzelne Benutzerkonto Microsoft Teams-Räume erstellen.
  
4. Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.
5. Nachdem Sie das Konto erstellt haben, führen Sie eine Verzeichnissynchronisierung aus. Dies kann mithilfe von [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell erreicht werden. Wechseln Sie nach Abschluss des Vorgangs zur Seite des Benutzers, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. Stellen Sie zunächst eine Verbindung mit Azure AD, um einige Kontoeinstellungen anzuwenden. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt.

    ``` PowerShell
   Connect-MsolService
    ```

2. Das Benutzerkonto muss über eine gültige Lizenz Office 365 verfügen, um eine Verbindung mit Microsoft Teams. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Benutzerkonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind.
3. Verwenden Sie "Get-MsolAccountSku", um eine Liste der verfügbaren SKUs für Ihren Mandanten Office 365 abzurufen.
4. Nachdem Sie die SKUs aufgeführt haben, können Sie mit "Set-MsolUserLicense" eine Lizenz hinzufügen. <!-- Set-AzureADUserLicense--> cmdlet. 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem beliebigen Microsoft Teams-Client bei dem von Ihnen erstellten Konto anmelden.
  
## <a name="see-also"></a>Mehr dazu

[Aktualisieren von Raumpostfächern mit zusätzlichen Metadaten, um eine bessere Erfahrung mit Such- und Raumvorschlägen zu ermöglichen](/powershell/module/exchange/set-place)

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
