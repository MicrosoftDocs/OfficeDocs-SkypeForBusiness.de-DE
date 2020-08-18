---
title: Zuweisen von Teams-Add-on-Lizenzen zu Benutzern
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Erfahren Sie, wie Sie Benutzern für Features wie Audiokonferenz, Telefon System und Anrufpläne Teams Add-on-Lizenzen zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788739"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Zuweisen von Teams-Add-on-Lizenzen zu Benutzern

Add-on-Lizenzen sind Lizenzen für bestimmte Teams-Features wie Audiokonferenzen, Telefonsysteme und Anrufpläne. In diesem Artikel wird beschrieben, wie Sie einzelnen Benutzern Add-on-Lizenzen und große Gruppen von Benutzern massenweise zuweisen können.

> [!NOTE]
> Weitere Informationen finden Sie unter [Teams-Add-on-Lizenzierung](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) für Teamfunktionen, die mit Add-on-Lizenzen verfügbar sind. Darüber hinaus finden Sie Informationen darüber, welche Lizenzen Sie kaufen müssen und wie Sie Sie erwerben (je nach Plan), sodass Benutzer Features wie Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihres Unternehmens erhalten können. Nachdem Sie sich entschieden haben, welche Features für Ihre Benutzer zur Verfügung stehen, weisen Sie Ihnen die Lizenzen zu.

Sie können das Microsoft 365 Admin Center oder PowerShell verwenden, um Benutzern in Ihrer Organisation Lizenzen zuzuweisen. Sie müssen ein globaler Administrator oder Benutzer Verwaltungs Administrator sein, um Lizenzen verwalten zu können.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Was Sie wissen müssen, bevor Sie eine Telefonanlage, einen Anrufplan und Kommunikationsguthaben-Lizenzen zuweisen

Bevor Sie beginnen, sehen Sie sich Folgendes an:

- Wenn Sie eine lokale PSTN-Konnektivität (Public Switched Telephone Network) für Hybrid Benutzer verwenden, müssen Sie nur eine Telefon System Lizenz zuweisen. Weisen Sie keine Anruf Plan Lizenz zu.

- Aufgrund der Wartezeit zwischen Microsoft 365 und Microsoft Teams kann es bis zu 24 Stunden dauern, bis ein Benutzer einen Anrufplan zugewiesen hat, nachdem Sie eine Lizenz zugewiesen haben. Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen ist, [wenden Sie sich an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Sie erhalten eine Fehlermeldung, wenn Sie die richtige Anzahl von Lizenzen nicht gekauft haben. Wenn Sie weitere Lizenzen für den Anrufplan kaufen müssen, wählen Sie die Option zum kaufen von mehr aus.

- Auch wenn ihren Benutzern Enterprise E5-Lizenzen zugewiesen wurden, müssen Sie Ihnen weiterhin [Kommunikationsguthaben](../what-are-communications-credits.md) -Lizenzen zuweisen, wenn Sie Anrufe tätigen oder empfangen möchten.

- Nachdem Sie Ihren Benutzern Anrufplan-oder Kommunikationsguthaben Lizenzen zugewiesen haben, müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden des Microsoft 365 admin Centers

Verwenden Sie das Microsoft 365 Admin Center, um einzelnen Benutzern oder kleinen Gruppen von Benutzern gleichzeitig Lizenzen zuzuweisen. Sie können Lizenzen auf der Seite " **Lizenzen** " (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite " **aktive Benutzer** " zuweisen. Die Methode, die Sie auswählen, hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer verwalten oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Wenn Sie Lizenzen für eine große Anzahl von Benutzern, wie etwa Hunderte oder Tausende von Benutzern, zuweisen müssen, verwenden Sie PowerShell oder [Gruppenbasierte Lizenzierung in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden von PowerShell zum Zuweisen von Lizenzen für Benutzer in Massen.  Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Beispielskript

Im folgenden finden Sie ein Beispiel für die Verwendung eines Skripts zum Zuweisen von Lizenzen für Ihre Benutzer.

1. Installieren Sie die 64-Bit-Version des [Microsoft Online Services-Anmelde Assistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell:
    1. Öffnen Sie eine erweiterte Windows PowerShell-Eingabeaufforderung (Windows PowerShell als Administrator ausführen).
    2. Führen Sie den folgenden Befehl aus:
        ```powershell
        Install-Module MSOnline
        ```
    3. Wenn Sie aufgefordert werden, den NuGet-Anbieter zu installieren, geben Sie **Y**ein, und drücken Sie dann die EINGABETASTE.
    4. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y**ein, und drücken Sie dann die EINGABETASTE.
3. Führen Sie an der Windows PowerShell-Eingabeaufforderung das folgende Skript aus, um Ihren Benutzern Lizenzen zuzuweisen, wobei \<CompanyName:License> es sich um den Namen Ihrer Organisation und den Bezeichner für die Lizenz handelt, die Sie zuweisen möchten. Beispiel: "litwareinc: MCOMEETADV.

    Der Bezeichner unterscheidet sich von dem Anzeigenamen der Lizenz. Der Bezeichner für Audiokonferenzen lautet beispielsweise MCOMEETADV. Weitere Informationen finden Sie unter [Produktnamen und SKU-IDs für die Lizenzierung](#product-names-and-sku-identifiers-for-licensing).

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    Um beispielsweise Microsoft 365 Enterprise 1-und Audio Conferencing-Lizenzen zuzuweisen, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Wenn Sie eine Lizenz für Microsoft Business Voice (ohne Anrufplan) zuweisen möchten, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Produktnamen und SKU-IDs für die Lizenzierung

Nachfolgend finden Sie eine unvollständige Liste der Produktnamen und der zugehörigen SKU-Bauteilnamen, die Sie als Referenz verwenden können, wenn Sie PowerShell zum Verwalten von Lizenzen in Microsoft Teams verwenden.

Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Produktnamen und Service Plan-IDs für Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)und [Education-SKU-Referenz](../sku-reference-edu.md).

| Produktname| SKU-Teilename |
|--------------|---------------|
| Microsoft Enterprise E5 (mit Telefon System) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (ohne Audiokonferenz) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (mit Audiokonferenz) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | Spb|
| Microsoft Business Voice (Kanada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Vereinigtes Königreich) | BUSINESS_VOICE  |
| Microsoft Business Voice (Vereinigte Staaten) | BUSINESS_VOICE_MED2  |
| Microsoft Business-VoIP (ohne Anrufplan) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business-VoIP (ohne Anrufplan) für die Vereinigten Staaten| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audiokonferenz | MCOMEETADV | 
| Audio-Konferenzgebühren pro Minute (im Voraus bezahlen)</br>*Erfordert das Einrichten und Aktivieren von Kommunikationsguthaben.* | MCOMEETACPEA |
| Telefonsystem | MCOEV |
| Plan für Inlands-und Auslandsgespräche | MCOPSTN2 |
| Plan für Inlandsanrufe (3000 Minuten pro Nutzer/Monat für US/PR/ca, 1200 Minuten pro Nutzer/Monat für EU-Länder) | MCOPSTN1 |
| Plan für Inlandsanrufe (120 Minuten pro Nutzer/Monat für jedes Land) </br>*Dieser Plan steht in den Vereinigten Staaten nicht zur Verfügung.* | MCOPSTN5 |
| Plan für Inlandsanrufe (240 Minuten pro Nutzer/Monat für jedes Land) </br>*Dieser Plan steht in den Vereinigten Staaten nicht zur Verfügung.* | MCOPSTN6 |
| Guthaben für Kommunikationen | MCOPSTNPP |

## <a name="related-topics"></a>Verwandte Themen

- [Lizenzierung für Teams-Add-On](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Verwalten des Benutzerzugriffs auf Teams](../user-access.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education-SKU-Referenz](../sku-reference-edu.md)