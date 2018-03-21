---
title: Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Informationen Sie zum Zuweisen von Skype für Business-Lizenzen für Telefonsystem, Audiokonferenzen, plant aufrufen und Communications haben. "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen

Dieser Artikel enthält Tipps zum Zuweisen von Lizenzen für Ihre Benutzer für Funktionen wie Audiokonferenzen Telefonsystem und plant aufrufen. Darüber hinaus Skripts zum Zuweisen von Lizenzen in einer Sammeloperation.
  
 **Wichtig**: Siehe [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](skype-for-business-and-microsoft-teams-add-on-licensing.md) für Informationen zu vorhandenen Lizenzen benötigen zum erwerben und **Informationen zum Erwerben von** - je nach Ihrer Office 365-Plan - damit Benutzer Audiokonferenzen, gebührenfreie Nummern erhalten und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihres Unternehmens.
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen

Was müssen Sie wissen, bevor Sie Audiokonferenzen, Telefonsystem und Planen der Aufruf von Lizenzen zuweisen

- **Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine **Telefonsystemlizenz** zuweisen. Weisen Sie **KEINEN** Anrufplan zu.
    
- **Latenz nach dem Zuweisen von Lizenzen**: Aufgrund der Latenz zwischen Office 365 und Skype for Business Online kann es nach dem Zuweisen einer Lizenz unter Umständen bis zu 24 Stunden dauern, bis einem Benutzer ein Anrufplan zugewiesen wird. Wenn nach 24 Stunden aufrufen Planen der Benutzer zugewiesen ist nicht, nehmen Sie die [Kontakt-Unterstützung für Business-Produkte - Admin-Hilfe](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.
    
- **Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Zuweisen einer Telefonsystem- und Anrufplanlizenz für einen Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Massenzuweisen von Telefonsystem- und Anrufplanlizenzen

1. Installieren Sie den **Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW**. Ist das Modul nicht installiert? Finden Sie unter [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunterladen.
    
2. Installieren Sie das **Windows Azure Active Directory-Modul**. Ist das Modul nicht installiert? Download-Anweisungen und die Syntax finden Sie unter [Verwalten von Azure Active Directory mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .
    
3. Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:
    
  In diesem Beispiel wird eine **Enterprise E3-Lizenz** zusammen mit einer Lizenz für **Telefonsysteme** und einer Lizenz für einen **Plan für Inlandsanrufe** zugewiesen.
    
  Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert (siehe **Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan** nach dem Beispiel).
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
  
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
|Plan für Inlandsanrufe  <br/> |MCOPSTN1  <br/> |
|Guthaben für Kommunikationen  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Wichtige Informationen vor dem Zuweisen von Lizenzen für Audiokonferenzen

- **Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für **Audiokonferenzen** zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.
    
- Nächste Schritte: Nachdem Sie **Audiokonferenzen** Lizenzen zuweisen möchten, müssen Sie kein Audiokonferenzanbieter zuweisen. Wählen Sie eine der folgenden Optionen aus:
    
  - [Zuweisen von Microsoft als Audiokonferenzanbieter](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Oder [Zuweisen eines Drittanbieters für Audiokonferenzen](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Zuweisen einer Lizenz für Audiokonferenzen zu einem einzelnen Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Massenzuweisen von Lizenzen für Audiokonferenzen

1. Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.
    
2. Laden Sie das **Windows Azure Active Directory-Modul herunter und installieren Sie es.** Anweisungen zum Herunterladen und die cmdlet-Syntax finden Sie unter[Verwalten von Azure AD mithilfe der Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:
    
    Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert. Finden Sie unter [Audiokonferenzen Produktnamen oder SKUs für das Skripting verwendet](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) für alle von der Produktnamen enthält.
    
    In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Audiokonferenzen zugewiesen.
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

- **Enterprise-E5 Kunden**:, auch wenn Ihre Benutzer Enterprise E5 Lizenzen zugewiesen sind, empfohlen, dass die **Kommunikation haben** Lizenzen zugewiesen.
    
- **Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Zuweisen einer Lizenz für Guthaben für Kommunikationen zu einem einzelnen Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Zuweisen von Lizenzen in einer Sammeloperation Communications haben

Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für **Audiokonferenzen** an. Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für **Guthaben für Kommunikationen**.
  
## <a name="related-topics"></a>See Also

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Hinzufügen von Guthaben und Verwalten von Guthaben für Kommunikationen](add-funds-and-manage-communications-credits.md)
  