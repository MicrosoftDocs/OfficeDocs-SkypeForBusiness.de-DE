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
description: Erfahren Sie, wie Sie Benutzern Teams-Add-On-Lizenzen für Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196929"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Zuweisen von Teams-Add-On-Lizenzen zu Benutzern

Add-On-Lizenzen sind Lizenzen für bestimmte Teams-Features wie Audiokonferenzen, Telefonsystem und Anrufpläne. In diesem Artikel wird beschrieben, wie Sie einzelnen Benutzern und großen Gruppen von Benutzern Massenlizenzen zuweisen.

> [!NOTE]
> Sehen [Sie sich die Teams-Add-On-Lizenzierung](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) für Teams-Features an, die mit Add-On-Lizenzen verfügbar sind. Darüber hinaus finden Sie hier Informationen dazu, welche Lizenzen Sie kaufen müssen und wie Sie diese (je nach Plan) kaufen können, damit Benutzer Funktionen wie Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit erhalten, Telefonnummern außerhalb Ihrer Organisation anrufen zu können. Nachdem Sie sich entschieden haben, welche Features für Ihre Benutzer verwendet werden sollen, weisen Sie ihnen die Lizenzen zu.

Sie können das Microsoft 365 Admin Center oder PowerShell verwenden, um Benutzern in Ihrer Organisation Lizenzen zuzuordnen. Sie müssen ein globaler Administrator oder ein Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Was Sie wissen müssen, bevor Sie Lizenzen für Telefonsystem, Anrufplan und Guthaben für Kommunikationen zuweisen

Bevor Sie beginnen, überprüfen Sie die folgenden Anforderungen:

- Wenn Sie lokale Konnektivität über das öffentliche Telefonnetz (PSTN) für Hybridbenutzer verwenden, müssen Sie nur eine Telefonsystemlizenz zuweisen. Weisen Sie KEINE Anrufplanlizenz zu.

- Aufgrund der Latenz zwischen Microsoft 365 und Microsoft Teams kann es nach dem Zuweisen einer Lizenz bis zu 24 Stunden dauern, bis einem Benutzer ein Anrufplan zugewiesen wurde. Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen wurde, wenden Sie sich an den Support für Geschäftsprodukte [– Administratorhilfe.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie die Option zum Kauf von weiteren Anrufplanlizenzen aus.

- Auch wenn Ihren Benutzern Enterprise E5-Lizenzen zugewiesen [](../what-are-communications-credits.md) sind, müssen Sie ihnen weiterhin Lizenzen für Guthaben für Kommunikationen zuweisen, wenn sie Anrufe über das FESTNETZ anrufen oder empfangen möchten.

- Nachdem Sie Ihren Benutzern Lizenzen für Anrufplan- oder Guthaben für Kommunikationen zugewiesen haben, müssen Sie Telefonnummern für Ihre Organisation erhalten und diese Nummern dann den Benutzern zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden des Microsoft 365 Admin Centers

Verwenden Sie das Microsoft 365 Admin Center, um einzelnen Benutzern oder kleinen Gruppen von Benutzern gleichzeitig Lizenzen zuzuordnen. Sie weisen Lizenzen auf der Seite **"Lizenzen"** (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite **"Aktive Benutzer"** zu. Die von Ihnen wählende Methode hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Eine schrittweise Anleitung finden Sie unter ["Zuweisen von Lizenzen zu Benutzern".](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

Wenn Sie Lizenzen für eine große Anzahl von Benutzern zuweisen müssen, z. B. Hunderte oder Tausende von Benutzern, verwenden Sie Powershell oder eine gruppenbasierte Lizenzierung [in Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, um Benutzern Lizenzen in Massen zuzuordnen.  Weitere Informationen finden Sie unter Zuweisen von Lizenzen [zu Benutzerkonten mit PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>Beispielskript

Hier ist ein Beispiel für die Verwendung eines Skripts zum Zuweisen von Lizenzen zu Ihren Benutzern.

1. Installieren Sie die 64-Bit-Version [des Microsoft Online Services A0 für IT-Experten RTW.](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)
2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell:
    1. Öffnen Sie eine Windows PowerShell Eingabeaufforderung mit erhöhten Rechten (führen Windows PowerShell als Administrator aus).
    2. Führen Sie den folgenden Befehl aus:
        ```powershell
        Install-Module MSOnline
        ```
    3. Wenn Sie aufgefordert werden, den "NuGet"-Anbieter zu installieren, geben Sie **"Y" ein,** und drücken Sie dann die EINGABETASTE.
    4. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **"Y"** ein, und drücken Sie dann die EINGABETASTE.
3. Führen Sie Windows PowerShell Eingabeaufforderung an der eingabeaufforderung das folgende Skript aus, um Ihren Benutzern Lizenzen zuzuordnen. Dabei handelt es sich um den Namen Ihrer Organisation und den Bezeichner für die Lizenz, die \<CompanyName:License> Sie zuweisen möchten. Beispiel: litwareinc:MCOMEETADV.

    Der Bezeichner ist anders als der Anzeigename der Lizenz. Der Bezeichner für Audiokonferenzen ist z. B. MCOMEETADV. Weitere Informationen finden Sie unter ["Produktnamen und SKU-Bezeichner für die Lizenzierung".](#product-names-and-sku-identifiers-for-licensing)

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

    Wenn Sie z. B. Lizenzen für Microsoft 365 Enterprise 1 und Audiokonferenzen zuweisen möchten, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Wenn Sie eine Microsoft Business #A0 (ohne Anrufplan) zuweisen möchten, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Produktnamen und SKU-Bezeichner für die Lizenzierung

Hier ist eine Teilliste der Produktnamen und deren entsprechenden SKU-Teilenamen, die Sie als Referenz verwenden können, wenn Sie PowerShell zum Verwalten von Lizenzen in Teams verwenden.

Weitere Informationen finden Sie unter "Anzeigen von Lizenzen und Diensten mit [PowerShell",](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)Produktnamen und [Serviceplanbezeichnern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)für die Lizenzierung und [Education-SKU-Referenz.](../sku-reference-edu.md)

| Produktname| SKU-Teilename |
|--------------|---------------|
| Microsoft Enterprise E5 (mit Telefonsystem) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (ohne Audiokonferenz) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (mit Audiokonferenz) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Kanada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Vereinigtes Königreich) | BUSINESS_VOICE  |
| Microsoft Business Voice (USA) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (ohne Anrufplan) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (ohne Anrufplan) für die USA| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audiokonferenz | MCOMEETADV | 
| Audiokonferenzen mit Minutenzahl (während der Vorwahl bezahlen)</br>*Setzt voraus, dass Guthaben für Kommunikationen eingerichtet und aktiviert wird.* | MCOMEETACPEA |
| Telefonsystem | MCOEV |
| Anrufplan für Inland und Ausland | MCOPSTN2 |
| Plan für Inlandsrufe (3.000 Minuten pro Benutzer/Monat für US/PR/CA, 1.200 Minuten pro Benutzer/Monat für EU-Länder) | MCOPSTN1 |
| Plan für Inlandsrufe (120 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan steht in den USA nicht zur Verfügung.* | MCOPSTN5 |
| Plan für Inlandsrufe (240 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan steht in den USA nicht zur Verfügung.* | MCOPSTN6 |
| Kommunikationsguthaben | MCOPSTNPP |

## <a name="related-topics"></a>Verwandte Themen

- [Lizenzierung für Teams-Add-On](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Verwalten des Benutzerzugriffs auf Teams](../user-access.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education-SKU-Referenz](../sku-reference-edu.md)