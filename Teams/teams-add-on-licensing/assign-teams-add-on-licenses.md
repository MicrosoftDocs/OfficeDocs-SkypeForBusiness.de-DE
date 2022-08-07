---
title: Zuweisen von Microsoft Teams-Add-On-Lizenzen zu Benutzern
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Erfahren Sie, wie Sie Benutzern Teams-Add-On-Lizenzen für Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b482781ee29094986c310158fe74f02662f790d
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268170"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Zuweisen von Microsoft Teams-Add-On-Lizenzen zu Benutzern

Add-On-Lizenzen sind Lizenzen für bestimmte Teams-Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne. In diesem Artikel wird beschrieben, wie Sie einzelnen Benutzern und großen Gruppen von Benutzern Massenlizenzen zuweisen.

> [!NOTE]
> Siehe [Microsoft Teams-Add-On-Lizenzierung für Teams-Funktionen](./microsoft-teams-add-on-licensing.md) , die mit Add-On-Lizenzen verfügbar sind. Sie finden auch Informationen dazu, welche Lizenzen Sie je nach Ihrem Plan kaufen müssen und wie Sie sie kaufen können. Nachdem Sie entschieden haben, welche Funktionen Sie ihren Benutzern zuweisen möchten, weisen Sie ihnen die Lizenzen zu.

Sie können die Microsoft 365 Admin Center oder PowerShell verwenden, um Benutzern in Ihrer Organisation Lizenzen zuzuweisen. Sie müssen ein globaler Administrator oder Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Was Sie wissen müssen, bevor Sie Lizenzen für Telefonsystem, Anrufplan und Kommunikationsguthaben zuweisen

Bevor Sie beginnen, überprüfen Sie die folgenden Anforderungen:

- Wenn Sie eine lokale PSTN-Konnektivität (Public Switched Telephone Network) für Benutzer verwenden, müssen Sie nur eine Teams Telefon Standard Lizenz zuweisen. Weisen Sie KEINE Anrufplanlizenz zu.

- Nach dem Zuweisen eines Microsoft-Anrufplans zu einem Benutzer kann es bis zu 24 Stunden dauern, bis die Wähltastatur in ihrem Teams-Client angezeigt wird. Wenn die Wähltastatur in 24 Stunden nicht angezeigt wird, überprüfen Sie ihre [Konfiguration der Wähltastatur](../dial-pad-configuration.md). Bei Bedarf können Sie sich auch [an den Support wenden](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen kaufen müssen, wählen Sie die Option aus, um mehr zu kaufen.

- Selbst wenn Ihren Benutzern Enterprise E5-Lizenzen zugewiesen sind, müssen Sie sie trotzdem mit dem PSTN verbinden. Sie haben mehrere [PSTN-Konnektivitätsoptionen](../pstn-connectivity.md), einschließlich Microsoft Teams-Anrufpläne, Direct Routing oder Operator Connect.

- Nachdem Sie Ihren Benutzern Lizenzen für Anrufpläne oder Kommunikationsguthaben zugewiesen haben, müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern dann Benutzern zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden der Microsoft 365 Admin Center

Verwenden Sie die Microsoft 365 Admin Center, um einzelnen Benutzern oder kleinen Gruppen von Benutzern gleichzeitig Lizenzen zuzuweisen.

Sie weisen Lizenzen auf der Seite **"Lizenzen** " (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite **"Aktive Benutzer** " (für bis zu 40 Benutzer gleichzeitig) zu. Die gewählte Methode hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Eine schrittweise Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).

Wenn Sie Lizenzen für eine große Anzahl von Benutzern zuweisen müssen, z. B. Hunderte oder Tausende von Benutzern, verwenden Sie PowerShell oder [gruppenbasierte Lizenzierung in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, um Benutzern massenhaft Lizenzen zuzuweisen. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Beispielskript

Hier ist ein Beispiel für die Verwendung eines Skripts zum Zuweisen von Lizenzen zu Ihren Benutzern.

1. [Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. Führen Sie an der eingabeaufforderung Windows PowerShell das folgende Skript aus, um Ihren Benutzern Lizenzen zuzuweisen. `CompanyName:License` Dabei ist der Name Ihrer Organisation und der Bezeichner für die Lizenz, die Sie zuweisen möchten. Beispiel `litwareinc:MCOMEETADV`: .

    Der Bezeichner unterscheidet sich vom Anzeigenamen der Lizenz. Der Bezeichner für Audiokonferenzen lautet `MCOMEETADV`beispielsweise . Weitere Informationen finden Sie unter [Produktnamen und SKU-Bezeichner für die Lizenzierung](#product-names-and-sku-identifiers-for-licensing).

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

    Um beispielsweise Microsoft 365 Enterprise E1- und Audiokonferenzlizenzen zuzuweisen, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Verwenden Sie zum Zuweisen einer Microsoft Teams-Telefon mit Anrufplanlizenz die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Produktnamen und SKU-Bezeichner für die Lizenzierung

Hier ist eine Teilliste der Produktnamen und deren entsprechenden SKU-Teilenamen, auf die Sie verweisen können, wenn Sie PowerShell zum Verwalten von Lizenzen in Teams verwenden.

Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Produktnamen und Serviceplan-IDs für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) und [Education-SKU-Referenz](../sku-reference-edu.md).

| Produktname| SKU-Teilename |
|--------------|---------------|
| Microsoft Enterprise E5 (mit Telefonsystem) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (ohne Audiokonferenz) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (mit Audiokonferenzen) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | Spb|
| Audiokonferenzen | MCOMEETADV |
| Audiokonferenzen pay per Minute (pay as you go) erfordert, dass Kommunikationsguthaben eingerichtet und aktiviert ist.* | MCOMEETACPEA |
| Teams Phone Standard | MCOEV |
| Teams Telefon mit Anrufplan | MCOTEAMS_ESSENTIALS |
| Plan für internationale Anrufe | MCOPSTN2 |
| Plan für Inlandsanrufe (3000 Minuten pro Benutzer/Monat für US/PR/CA, 1200 Minuten pro Benutzer/Monat für EU-Länder) | MCOPSTN1 |
| Anrufplan für Inland (120 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan ist in der USA nicht verfügbar.* | MCOPSTN5 |
| Anrufplan für Inland (240 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan ist in der USA nicht verfügbar.* | MCOPSTN6 |
| Guthaben für Kommunikationen | MCOPSTNPP |
| Pay-as-You-Go-Anrufpläne (Zone-1-Länder) | MCOPSTN_PAYG_1 |
| Pay-as-You-Go-Anrufpläne (Zone-2-Länder) | MCOPSTN_PAYG_2 |

## <a name="related-content"></a>Verwandter Inhalt

- [Lizenzierung für Teams-Add-On](./microsoft-teams-add-on-licensing.md)
- [Verwalten des Benutzerzugriffs auf Microsoft Teams](../user-access.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education-SKU-Referenz](../sku-reference-edu.md)
