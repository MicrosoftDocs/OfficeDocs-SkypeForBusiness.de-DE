---
title: Zuweisen Teams Add-On-Lizenzen zu Benutzern
author: SerdarSoysal
ms.author: serdars
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
description: Erfahren Sie, wie Teams add-on-Lizenzen für Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8668b31caf0dc10e8585a518a9c4c9be890d1d0d
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435839"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Zuweisen Teams Add-On-Lizenzen zu Benutzern

Add-On-Lizenzen sind Lizenzen für Teams Funktionen wie Audiokonferenzen, Telefonsystem und Anrufpläne. In diesem Artikel wird beschrieben, wie Sie einzelnen Benutzern und großen Mengen an Benutzern Add-On-Lizenzen in Massen zuweisen.

> [!NOTE]
> Unter [Teams-Add-On-Lizenzierung](./microsoft-teams-add-on-licensing.md) finden Teams Funktionen, die mit Add-On-Lizenzen verfügbar sind. Außerdem finden Sie hier Informationen dazu, welche Lizenzen Sie kaufen müssen und wie Sie sie je nach Ihrem Plan kaufen können. Nachdem Sie sich entschieden haben, welche Funktionen Sie ihren Benutzern zuweisen möchten, weisen Sie ihnen Lizenzen zu.

Sie können die Microsoft 365 Admin Center oder PowerShell verwenden, um Benutzern in Ihrer Organisation Lizenzen zuzuordnen. Sie müssen ein globaler Administrator oder Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Was Sie wissen müssen, bevor Sie Lizenzen Telefonsystem, Anrufplan und Guthaben für Kommunikationen zuweisen

Bevor Sie beginnen, überprüfen Sie die folgenden Anforderungen:

- Wenn Sie lokale PSTN-Konnektivität (Public Switched Telephone Network) für Benutzer verwenden, müssen Sie nur eine Teams Telefon Standardlizenz zuweisen. Weisen Sie KEINE Anrufplanlizenz zu.

- Nach dem Zuweisen eines Microsoft-Anrufplans zu einem Benutzer kann es bis zu 24 Stunden dauern, bis ihm die Wähltast in seinem Teams angezeigt wird. Wenn die Wählta nicht in 24 Stunden angezeigt wird, überprüfen Sie die Konfiguration der [Wählta nicht](../dial-pad-configuration.md). Bei Bedarf können Sie auch den [Support kontaktieren](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie die Option zum Kauf von weiteren aus.

- Selbst wenn Ihren Benutzern E5 Enterprise zugewiesen sind, müssen Sie sie dennoch mit dem PSTN verbinden. Es gibt mehrere [PSTN-Konnektivitätsoptionen](../pstn-connectivity.md), darunter Microsoft Teams Anrufpläne, Direct-Routing oder Verbinden.

- Nachdem Sie Ihren Benutzern Lizenzen für Anrufplan- oder Guthaben für Kommunikationen zugewiesen haben, müssen Sie Telefonnummern für Ihre Organisation erhalten und diese Nummern dann Benutzern zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden der Microsoft 365 Admin Center

Verwenden Sie Microsoft 365 Admin Center, um einzelnen Benutzern oder kleinen Gruppen von Benutzern gleichzeitig Lizenzen zuzuordnen.

Sie weisen Lizenzen auf der  Seite Lizenzen (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite Aktive  Benutzer (für bis zu 40 Benutzer gleichzeitig) zu. Die von Ihnen wählen Methode hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Eine schrittweise Anleitung finden Sie unter Zuweisen [von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).

Wenn Sie Lizenzen für eine große Anzahl von Benutzern, z. B. Hunderte oder Tausende von Benutzern, zuweisen müssen, verwenden Sie Powershell oder eine gruppenbasierte Lizenzierung [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)

## <a name="using-powershell"></a>Verwendung von PowerShell

Mithilfe von PowerShell können Sie Benutzern Lizenzen in Massen zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Beispielskript

Hier ist ein Beispiel für die Verwendung eines Skripts zum Zuweisen von Lizenzen zu Ihren Benutzern.

1. Installieren Sie die 64-Bit-Version [des Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](/collaborate/connect-redirect?DownloadID=59185).
2. Installieren Sie Microsoft Azure Active Directory-Modul für Windows PowerShell:
    1. Öffnen Sie eine Eingabeaufforderung Windows PowerShell mit erhöhten Rechten (führen Windows PowerShell als Administrator aus).
    2. Führen Sie den folgenden Befehl aus:
        ```powershell
        Install-Module MSOnline
        ```
    3. Wenn Sie aufgefordert werden, den Anbieter NuGet, geben Sie **Y** ein, und drücken Sie dann die EINGABETASTE.
    4. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y** ein, und drücken Sie dann die EINGABETASTE.
3. Führen Sie Windows PowerShell Eingabeaufforderung zuweisen das folgende Skript aus, um Ihren Benutzern Lizenzen zuzuordnen. \<CompanyName:License> Dabei handelt es sich um den Namen Ihrer Organisation und den Bezeichner für die Lizenz, die Sie zuweisen möchten. Beispiel: litwareinc:MCOMEETADV.

    Der Bezeichner ist anders als der Anzeigename der Lizenz. Der Bezeichner für Audiokonferenzen ist z. B. MCOMEETADV. Weitere Informationen finden Sie unter [Produktnamen und SKU-IDs für die Lizenzierung](#product-names-and-sku-identifiers-for-licensing).

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

    Wenn Sie z. B. Microsoft 365 Enterprise E1- und Audiokonferenzlizenzen zuweisen möchten, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Wenn Sie eine Teams Telefon Anrufplanlizenz zuweisen möchten, verwenden Sie die folgende Syntax im Skript:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Produktnamen und SKU-IDs für die Lizenzierung

Hier finden Sie eine teilweise Liste der Produktnamen und der entsprechenden SKU-Teilenamen, auf die Sie verweisen können, wenn Sie PowerShell zum Verwalten von Lizenzen in Teams.

Weitere Informationen finden Sie unter Anzeigen von Lizenzen und Diensten [mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), Produktnamen und [Serviceplan-IDs](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) für lizenzierung und [SKU-Referenz für Bildungseinrichtungen](../sku-reference-edu.md).

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
| Audiokonferenzen | MCOMEETADV |
| Audiokonferenzen Mit Minuten bezahlt (im Voraus bezahlen) Setzt das Einrichten und Aktivieren von Guthaben für Kommunikationen voraus.* | MCOMEETACPEA |
| Teams Telefon Standard | MCOEV |
| Teams Telefon mit Anrufplan | MCOTEAMS_ESSENTIALS |
| Anrufplan für In- und Ausland | MCOPSTN2 |
| Plan für Inlandsrufe (3.000 Minuten pro Benutzer/Monat für US/PR/CA, 1.200 Minuten pro Benutzer/Monat für EU-Länder) | MCOPSTN1 |
| Plan für Inlandsrufe (120 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan steht in den USA nicht zur Verfügung.* | MCOPSTN5 |
| Plan für Inlandsrufe (240 Minuten pro Benutzer/Monat für jedes Land) </br>*Dieser Plan steht in den USA nicht zur Verfügung.* | MCOPSTN6 |
| Guthaben für Kommunikationen | MCOPSTNPP |

## <a name="related-content"></a>Verwandter Inhalt

- [Lizenzierung für Teams-Add-On](./microsoft-teams-add-on-licensing.md)
- [Verwalten des Benutzerzugriffs auf Teams](../user-access.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [SKU-Referenz für Bildungseinrichtungen](../sku-reference-edu.md)
