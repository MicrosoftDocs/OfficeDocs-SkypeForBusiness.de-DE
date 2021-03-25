---
title: Zuweisen von Teams-Add-On-Lizenzen zu Benutzern
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie Benutzern Teams-Add-On-Lizenzen für Features wie Audiokonferenzen, Telefonsystem und Anrufpläne zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116933"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Zuweisen von Teams-Add-On-Lizenzen zu Benutzern

Add-On-Lizenzen sind Lizenzen für bestimmte Teams-Features wie Audiokonferenzen, Telefonsystem und Anrufpläne. In diesem Artikel wird beschrieben, wie Sie einzelnen Benutzern und großen Gruppen von Benutzern Massenlizenzen zuweisen.

> [!NOTE]
> Weitere [Informationen finden Sie unter Teams-Add-On-Lizenzierung](./microsoft-teams-add-on-licensing.md) für Teams-Features, die mit Add-On-Lizenzen verfügbar sind. Außerdem finden Sie Informationen dazu, welche Lizenzen Sie kaufen müssen und wie sie (je nach Plan) erworben werden, damit Benutzer Features wie Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihrer Organisation erhalten können. Nachdem Sie entschieden haben, welche Features Sie für Ihre Benutzer verwenden möchten, weisen Sie ihnen die Lizenzen zu.

Sie können das Microsoft 365 Admin Center oder PowerShell verwenden, um Benutzern in Ihrer Organisation Lizenzen zuzuordnen. Sie müssen globaler Administrator oder Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Was Sie vor der Zuweisung von Lizenzen für Telefonsystem, Anrufplan und Kommunikationsguthaben wissen müssen

Bevor Sie beginnen, überprüfen Sie die folgenden Anforderungen:

- Wenn Sie lokale PstN-Konnektivität (Public Switched Telephone Network) für Hybridbenutzer verwenden, müssen Sie nur eine Telefonsystemlizenz zuweisen. Weisen Sie KEINE Anrufplanlizenz zu.

- Aufgrund der Latenz zwischen Microsoft 365 und Microsoft Teams kann es bis zu 24 Stunden dauern, bis einem Benutzer nach dem Zuweisen einer Lizenz ein Anrufplan zugewiesen wurde. Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen wurde, wenden Sie sich an den Support für [Business-Produkte – Administratorhilfe.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Lizenzen für den Anrufplan erwerben müssen, wählen Sie die Option aus, um mehr zu kaufen.

- Auch wenn Ihren Benutzern Enterprise E5-Lizenzen zugewiesen [](../what-are-communications-credits.md) sind, müssen Sie ihnen weiterhin Lizenzen für Guthaben für Kommunikationen zuweisen, wenn sie Anrufe aus dem PSTN machen oder empfangen möchten.

- Nachdem Sie Ihren Benutzern Lizenzen für Anrufplan- oder Kommunikationsguthaben zugewiesen haben, müssen Sie Telefonnummern für Ihre Organisation erhalten und diese Nummern dann Benutzern zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden des Microsoft 365 Admin Centers

Verwenden Sie das Microsoft 365 Admin Center, um einzelnen Benutzern lizenzen oder kleine Benutzergruppen gleichzeitig zuzuordnen. Sie weisen Lizenzen auf der Seite **Lizenzen** (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite **Aktive Benutzer** zu. Die methode, die Sie auswählen, hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer verwalten oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Schrittweise Anleitungen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

Wenn Sie Lizenzen für eine große Anzahl von Benutzern zuweisen müssen, z. B. Hunderte oder Tausende von Benutzern, verwenden Sie Powershell oder gruppenbasierte Lizenzierung [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, um Benutzern Lizenzen in Massen zuzuordnen.  Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>Beispielskript

Hier ist ein Beispiel für die Verwendung eines Skripts zum Zuweisen von Lizenzen zu Ihren Benutzern.

1. Installieren Sie die 64-Bit-Version [des Microsoft Online Services-Anmelde-Assistenten für IT-Experten RTW](/collaborate/connect-redirect?DownloadID=59185).
2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell:
    1. Öffnen Sie eine Windows PowerShell Eingabeaufforderung (führen Windows PowerShell als Administrator aus).
    2. Führen Sie den folgenden Befehl aus:
        ```powershell
        Install-Module MSOnline
        ```
    3. Wenn Sie aufgefordert werden, den NuGet-Anbieter zu installieren, geben Sie **Y** ein, und drücken Sie dann die EINGABETASTE.
    4. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y** ein, und drücken Sie dann die EINGABETASTE.
3. Führen Sie an Windows PowerShell Eingabeaufforderung das folgende Skript aus, um Ihren Benutzern Lizenzen zu zuweisen. Dabei handelt es sich um den Namen Ihrer Organisation und den Bezeichner für die Lizenz, die \<CompanyName:License> Sie zuweisen möchten. Beispiel: litwareinc:MCOMEETADV.

    Der Bezeichner ist anders als der Anzeigename der Lizenz. Der Bezeichner für Audiokonferenzen ist z. B. MCOMEETADV. Weitere Informationen finden Sie unter [Produktnamen und SKU-Bezeichner für die Lizenzierung.](#product-names-and-sku-identifiers-for-licensing)

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

    Wenn Sie beispielsweise Lizenzen für Microsoft 365 Enterprise 1 und Audiokonferenzen zuweisen möchten, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Verwenden Sie zum Zuweisen einer Microsoft Business Voice (ohne Anrufplan) die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Produktnamen und SKU-Bezeichner für die Lizenzierung

Hier ist eine teilweise Liste der Produktnamen und der zugehörigen SKU-Teilenamen, die Sie als Referenz verwenden können, wenn Sie PowerShell zum Verwalten von Lizenzen in Teams verwenden.

Weitere Informationen finden Sie unter Anzeigen von Lizenzen und Diensten [mit PowerShell,](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)Produktnamen und [Serviceplanbezeichnern für die](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)Lizenzierung und Education [SKU-Referenz](../sku-reference-edu.md).

| Produktname| SKU-Teilename |
|--------------|---------------|
| Microsoft Enterprise E5 (mit Telefonsystem) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (ohne Audiokonferenzen) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (mit Audiokonferenzen) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Kanada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Vereinigtes Königreich) | BUSINESS_VOICE  |
| Microsoft Business Voice (Vereinigte Staaten) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (ohne Anrufplan) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (ohne Anrufplan) für die USA| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audiokonferenz | MCOMEETADV | 
| Audiokonferenzen– Zahlung pro Minute (unterwegs bezahlen)</br>*Erfordert das Einrichten und Aktivieren von Guthaben für Kommunikationen.* | MCOMEETACPEA |
| Telefonsystem | MCOEV |
| Plan für Inlands- und Auslandsrufe | MCOPSTN2 |
| Domestic Calling Plan (3000 Minuten pro Benutzer/Monat für US/PR/CA, 1200 Minuten pro Benutzer/Monat für EU-Länder) | MCOPSTN1 |
| Plan für Inlandsrufe (120 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan steht in den USA nicht zur Verfügung.* | MCOPSTN5 |
| Plan für Inlandsrufe (240 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan steht in den USA nicht zur Verfügung.* | MCOPSTN6 |
| Guthaben für Kommunikationen | MCOPSTNPP |

## <a name="related-topics"></a>Verwandte Themen

- [Lizenzierung für Teams-Add-On](./microsoft-teams-add-on-licensing.md)
- [Verwalten des Benutzerzugriffs auf Microsoft Teams](../user-access.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referenz zur Bildungs-SKU](../sku-reference-edu.md)