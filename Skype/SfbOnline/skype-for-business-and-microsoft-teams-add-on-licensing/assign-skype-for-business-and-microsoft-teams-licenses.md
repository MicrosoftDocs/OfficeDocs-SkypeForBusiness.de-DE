---
title: Zuweisen von Skype for Business-Lizenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Erfahren Sie, wie Sie Skype for Business-Lizenzen für Telefonsysteme, Audiokonferenzen, Anrufpläne und Kommunikationsguthaben zuweisen. '
ms.openlocfilehash: 6917b3d47f29c10bea8b7695cfa69ace60609393
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671821"
---
# <a name="assign-skype-for-business-licenses"></a>Zuweisen von Skype for Business-Lizenzen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel finden Sie Tipps zum Zuweisen von Lizenzen zu Ihren Benutzern für Features wie Audiokonferenz, Telefonsystem und Anrufpläne. Außerdem werden Skripts für die Massenzuweisung von Lizenzen bereitgestellt.

> [!IMPORTANT]
> Unter [Skype for Business Add-On-Lizenzierung](skype-for-business-and-microsoft-teams-add-on-licensing.md) finden Sie Informationen dazu, welche Lizenzen Sie kaufen müssen und wie Sie diese **kaufen können** – je nach Microsoft 365 oder Office 365-Plan – damit Benutzer Audiokonferenz, gebührenfreie Telefonnummern und die Möglichkeit erhalten, Telefonnummern außerhalb Ihres Unternehmens anzurufen.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen

Wissenswertes vor dem Zuweisen von Lizenzen für Audiokonferenz, Telefonsystem und Anrufpläne

- **Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine **Telefonsystemlizenz** zuweisen. Weisen Sie **KEINEN** Anrufplan zu.

- **Latenz nach dem Zuweisen von Lizenzen**: Aufgrund der Latenz zwischen Microsoft 365 oder Office 365 und Skype for Business Online kann es bis zu 24 Stunden dauern, bis einem Benutzer nach dem Zuweisen einer Lizenz ein Anrufplan zugewiesen wurde. Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen ist, [wenden Sie sich bitte an den Support für Geschäftsprodukte – Admin Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.
    
- **Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Zuweisen einer Telefonsystem- und Anrufplanlizenz für einen Benutzer

Die Schritte sind identisch mit dem Zuweisen einer Microsoft 365- oder Office 365-Lizenz. Weitere Informationen [finden Sie unter Zuweisen oder Entfernen von Lizenzen für Microsoft 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Massenzuweisen von Telefonsystem- und Anrufplanlizenzen

1. Installieren Sie den **Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW**. Ist das Modul nicht installiert? Informationen zum Herunterladen finden Sie unter [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) .

2. Installieren Sie das **Windows Azure Active Directory-Modul**. Ist das Modul nicht installiert? Downloadanweisungen und Cmdlet-Syntax finden [Sie unter Verwalten von Azure AD mit Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).

3. Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:

   In diesem Beispiel wird eine **Enterprise E3-Lizenz** zusammen mit einer Lizenz für **Telefonsysteme** und einer Lizenz für einen **Plan für Inlandsanrufe** zugewiesen.

   Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert (siehe **Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan** nach dem Beispiel).

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan

|**Produktname**|**SKU-Teilename**|
|:-----|:-----|
|Enterprise E5 (mit Telefonsystem)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Telefonsystem  <br/> |MCOEV  <br/> |
|Plan für Auslandsanrufe  <br/> |MCOPSTN2  <br/> |
|Inlandsanrufplan (3000 Min. USA / 1200 Min. EU-Pläne)  <br/> |MCOPSTN1  <br/> |
|Anrufplan für Inland (120 Minuten Anrufplan)  <br/> |MCOPSTN5  <br/> |
|Anrufplan für Inland (240 Minuten Anrufplan)  <br/> |MCOPSTN6  <br/> |
|Guthaben für Kommunikationen  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Wichtige Informationen vor dem Zuweisen von Lizenzen für Audiokonferenzen

- **Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für **Audiokonferenzen** zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.

- Nächste Schritte: **Nachdem Sie Audiokonferenz** Lizenzen zugewiesen haben, müssen Sie einen Audiokonferenzanbieter zuweisen. Siehe [Microsoft als Anbieter von Audiokonferenzen zuweisen].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Zuweisen einer Lizenz für Audiokonferenzen zu einem einzelnen Benutzer

Die Schritte sind identisch mit dem Zuweisen einer Microsoft 365- oder Office 365-Lizenz. Weitere Informationen [finden Sie unter Zuweisen oder Entfernen von Lizenzen für Microsoft 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Massenzuweisen von Lizenzen für Audiokonferenzen

1. Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.

2. Laden Sie das **Windows Azure Active Directory-Modul herunter und installieren Sie es.** Anweisungen zum Herunterladen und die cmdlet-Syntax finden Sie unter [Verwalten von Azure AD mithilfe der Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).

   Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:

   Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert. Informationen [zu allen Produktnamen finden Sie unter Audiokonferenz Produktnamen oder SKUs, die für die Skripterstellung verwendet werden](assign-skype-for-business-and-microsoft-teams-licenses.md#sku).

   In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Audiokonferenzen zugewiesen.

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
   #Example of text file:
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
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
   ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Für die Skripterstellung verwendete Produktnamen oder SKUs für Audiokonferenz
<a name="sku"> </a>

|**Produktname**|**SKU-Teilename**|
|:-----|:-----|
|Audiokonferenz  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (ohne Audiokonferenz)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (mit Audiokonferenz)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Guthaben für Kommunikationen

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Wichtige Informationen vor dem Zuweisen von Guthaben für Kommunikationen

- **Enterprise E5-Kunden**: Auch wenn Ihren Benutzern Enterprise E5-Lizenzen zugewiesen sind, empfehlen wir dennoch, ihnen **Lizenzen für Guthaben für Kommunikationen** zuzuweisen.
    
- **Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Zuweisen einer Lizenz für Guthaben für Kommunikationen zu einem einzelnen Benutzer

Die Schritte sind identisch mit dem Zuweisen einer Microsoft 365- oder Office 365-Lizenz. Weitere Informationen [finden Sie unter Zuweisen oder Entfernen von Lizenzen für Microsoft 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>So weisen Sie Lizenzen für Guthaben für Kommunikationen massenhaft zu

Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für **Audiokonferenzen** an. Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für **Guthaben für Kommunikationen**.

## <a name="related-topics"></a>Verwandte Themen
  
[Einrichten von Anrufplänen](/microsoftteams/set-up-calling-plans)
  
[Hinzufügen und Verwalten von Guthaben für Kommunikationen](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
