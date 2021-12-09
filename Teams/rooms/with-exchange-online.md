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
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355634"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange online

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Exchange Online.
  
Wenn Ihre Organisation über eine Mischung von Diensten verfügt, von denen einige lokal und einige online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden. In diesem Thema werden Hybridbereitstellungen für Microsoft Teams-Räume mit online Exchange Bereitstellung behandelt. Da es bei diesem Bereitstellungstyp so viele verschiedene Varianten gibt, können keine detaillierten Anweisungen für alle Bereitstellungen zur Verfügung stehen. Das folgende Verfahren funktioniert für viele Konfigurationen. Wenn der Vorgang für Ihre Einrichtung nicht richtig ist, empfehlen wir, Windows PowerShell zu verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, sowie für andere Bereitstellungsoptionen.

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Exchange Online bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)
  
Zum Bereitstellen Microsoft Teams-Räume mit Exchange Online, führen Sie die folgenden Schritte aus. Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen. 

   > [!NOTE]
   >  Das Azure Active Directory-Modul für [Windows PowerShell-Cmdlets](/powershell/azure/active-directory/overview) in diesem Abschnitt (z. B. Set-MsolUser) wurde unter Einrichten von Konten für Microsoft Teams-Räume getestet. Es ist möglich, dass andere Cmdlets funktionieren, aber in diesem speziellen Szenario noch nicht getestet wurden.

Wenn Sie Active Directory-Verbunddienste (AD FS) bereitgestellt haben, müssen Sie das Benutzerkonto möglicherweise in einen verwalteten Benutzer konvertieren, bevor Sie diese Schritte ausführen, und dann den Benutzer wieder in einen Partnerbenutzer konvertieren, nachdem Sie diese Schritte abgeschlossen haben.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften

1. Starten Sie eine Windows PowerShell-Sitzung auf einem PC, und stellen Sie wie folgt eine Exchange Online Verbindung mit dem Computer dar:

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann sich das Konto bei ihrem Konto Microsoft Teams-Räume.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Um die Besprechungserfahrung zu verbessern, müssen Sie die Eigenschaften Exchange Benutzerkonto wie folgt festlegen:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto

1. Klicken **Sie im Active Directory-Ad-Tool** Benutzer und Computer mit der rechten Maustaste auf den Container oder die Organisationseinheit, in dem Ihre Microsoft Teams-Räume-Konten erstellt werden, klicken Sie auf Neu und dann auf  **Benutzer.**
2. Geben Sie den Anzeigenamen (- Identity) aus dem vorherigen Cmdlet  (Set-Mailbox oder New-Mailbox) in das Feld Vollständiger Name und den Alias in das Feld **Benutzeranmeldungsname** ein. Klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Die **Auswahl von Kennwort läuft nie ab** ist eine Voraussetzung für die Skype for Business Server auf Microsoft Teams-Räume. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Falls müssen Sie für jedes einzelne Benutzerkonto Microsoft Teams-Räume erstellen.
  
4. Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.
5. Nachdem Sie das Konto erstellt haben, führen Sie eine Verzeichnissynchronisierung aus. Dies kann mithilfe von [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) in PowerShell erreicht werden. Wechseln Sie nach Abschluss des Vorgangs zur Seite Benutzer, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Zuweisen einer Microsoft 365 oder Office 365 Lizenz

1. Stellen Sie zunächst eine Verbindung mit Azure AD, um einige Kontoeinstellungen anzuwenden. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview) nicht unterstützt.

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Das Benutzerkonto muss über eine gültige Lizenz Microsoft 365 oder Office 365 verfügen, um sicherzustellen, dass Exchange funktioniert. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Benutzerkonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie nehmen die Aufgabe in einem folgenden Schritt vor.
3. Verwenden Sie als Nächstes `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> um eine Liste der verfügbaren SKUs für Ihre Organisation Microsoft 365 oder Office 365 abzurufen.
4. Sie können eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. In diesem Fall wird die Microsoft Teams-Räume Standard angewendet. 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
