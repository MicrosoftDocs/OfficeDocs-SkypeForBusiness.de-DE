---
title: "Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Dieser Artikel enthält Tipps zum Zuweisen von Lizenzen für Ihre Benutzer für Features wie Audio Konferenzen, Telefonsystem und Pläne aufrufen. Darüber hinaus Skripts zum Zuweisen von Lizenzen in Massen.
  
 **Wichtig**: finden Sie unter[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) Informationen, wie Sie Lizenzen benötigt kaufen und **erwerben** diese - je nach Office 365-Plan -, damit Benutzer abrufen von Audio Konferenzen, gebührenfreie Nummern und die Möglichkeit, das Anrufen von Telefonnummern außerhalb Ihres Unternehmens.
  
## Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen

### Was müssen Sie vor dem Zuweisen von Audio Konferenzen, Telefonsystem und planen Aufrufen von Lizenzen

- **WICHTIG**: Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.
    
- **Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine **Telefonsystemlizenz** zuweisen. Weisen Sie **KEINEN** Anrufplan zu.
    
- **Wartezeit nach dem Zuweisen von Lizenzen**: aufgrund der Wartezeit zwischen Office 365 und Skype for Business Online, kann es möglicherweise dauern bis zu 24 Stunden für einen Benutzer aufrufen planen zugewiesen werden soll, nachdem Sie eine Lizenz zuweisen. Wenn nach 24 Stunden aufrufen Planen der Benutzer zugewiesen nicht zur Verfügung, melden Sie[Kontaktieren des Office 365 Business-Supports - Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.
    
- **Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter[Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Zuweisen einer Telefonsystem- und Anrufplanlizenz für einen Benutzer

Die Schritte sind identisch mit eine Office 365-Lizenz zuweisen. Finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Massenzuweisen von Telefonsystem- und Anrufplanlizenzen

1. Installieren Sie den **Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW**. Das Modul ist nicht installiert? Unter[Microsoft Online Services-Anmelde-Assistent für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) können Sie es herunterladen.
    
2. Installieren Sie das **Windows Azure Active Directory-Modul**. Ist das Modul nicht installiert? Angaben zu Downloads und die Cmdlet-Syntax finden Sie unter[Verwalten von Azure AD mit Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
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
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan

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
   
## Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen

### Wichtige Informationen vor dem Zuweisen von Lizenzen für Audiokonferenzen

- **Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für **Audiokonferenzen** zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.
    
- Nächste Schritte: Nachdem Sie **Audiokonferenzanbieter** Lizenzen zugewiesen haben, müssen Sie einen Audiokonferenzanbieter zuweisen. Führen Sie eine der folgenden Aktionen aus:
    
  - [Zuweisen von Microsoft als Audiokonferenzanbieter](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Oder [Zuweisen eines Drittanbieters für Audiokonferenzen](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### Zuweisen einer Lizenz für Audiokonferenzen zu einem einzelnen Benutzer

Die Schritte sind identisch mit eine Office 365-Lizenz zuweisen. Finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Massenzuweisen von Lizenzen für Audiokonferenzen

1. Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.
    
2. Laden Sie das **Windows Azure Active Directory-Modul herunter und installieren Sie es.** Anweisungen zum Herunterladen und die cmdlet-Syntax finden Sie unter[Verwalten von Azure AD mithilfe der Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:
    
    Der Name der Lizenzen oder Produktnamen in das Skript werden in kursiver Text aufgelistet. Finden Sie unter [Für die Skripterstellung verwendete Produktnamen oder SKUs für Audiokonferenz](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku) für alle Artikelnamen.
    
    In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Audiokonferenzen zugewiesen.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### Für die Skripterstellung verwendete Produktnamen oder SKUs für Audiokonferenz
<a name="sku"> </a>

|**Produktname**|**SKU-Teilename**|
|:-----|:-----|
|Audiokonferenz  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (ohne Audiokonferenz)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (mit Audiokonferenz)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## Guthaben für Kommunikationen

### Wichtige Informationen vor dem Zuweisen von Guthaben für Kommunikationen

- **E5 Enterprise-Kunden**: auch wenn Ihre Benutzer Enterprise E5 Lizenzen zugewiesen sind, empfohlen, dass Sie **Kommunikation Gutschriften** Lizenzen zuweisen.
    
- **Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter[Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Zuweisen einer Lizenz für Guthaben für Kommunikationen zu einem einzelnen Benutzer

Die Schritte sind identisch mit eine Office 365-Lizenz zuweisen. Finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### So Kommunikation Gutschriften Lizenzen in Massen zuweisen

Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für **Audiokonferenzen** an. Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für **Guthaben für Kommunikationen**.
  
## Verwandte Artikel

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Mittel hinzufügen und Verwalten von Kommunikation Gutschriften](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

