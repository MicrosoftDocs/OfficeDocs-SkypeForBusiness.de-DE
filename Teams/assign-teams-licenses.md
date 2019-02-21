---
title: Zuweisen von Lizenzen für Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: mikedav
description: Informationen Sie zum Zuweisen von Lizenzen für Anrufe Pläne und Funktionen wie Audiokonferenzen, Telefonsystem.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 078db13179f0e33cb950c00ea58e76f11c8eb405
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2019
ms.locfileid: "30127630"
---
# <a name="assign-microsoft-teams-licenses"></a>Zuweisen von Lizenzen für Microsoft-Teams

Sie können Ihre Benutzer für Funktionen wie Audiokonferenzen Telefonsystem und plant aufrufen Lizenzen zuweisen. In diesem Artikel wird erläutert, wie diese Lizenzen in einer Sammeloperation und für einen einzelnen Benutzer hinzufügen. 

> [!IMPORTANT]
> Informationen finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) was Lizenzen, die Sie kaufen müssen und wie Sie sie, je nach Ihrer Office 365 kaufen planen, damit Benutzer Audiokonferenzen und gebührenfreie Nummern anrufen Telefonnummern außerhalb Ihres Unternehmens erhalten.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen

Hier ist, was Sie vor dem Zuweisen von Lizenzen für Audiokonferenzen, Telefonsystem und Planen von Aufrufen wissen müssen.

- **Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine Telefonsystemlizenz zuweisen. Weisen Sie KEINEN Anrufplan zu.

- **Wartezeit nach dem Zuweisen von Lizenzen**: wegen der Wartezeit zwischen Office 365 und Microsoft-Teams, dauert es bis zu 24 Stunden für einen Benutzer aufrufen planen zugewiesen werden soll, nachdem Sie eine Lizenz zugewiesen haben. Wenn nach 24 Stunden aufrufen Planen der Benutzer zugewiesen ist nicht, wenden Sie [Unterstützung für Business-Produkte - Admin-Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.

- **Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Weisen Sie eine Lizenz Telefonsystem und Planen von Aufrufen an einen Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Zuweisen von Lizenzen von Telefonsystem und Planen von Aufrufen in einer Sammeloperation

1. Installieren Sie den Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW. Ist das Modul nicht installiert? Finden Sie unter [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunterladen.

2. Installieren Sie das Windows Azure Active Directory-Modul. Ist das Modul nicht installiert? Download-Anweisungen und die Syntax finden Sie unter [Verwalten von Azure Active Directory mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

3. Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:

In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Telefonsysteme und einer Lizenz für einen Plan für Inlandsanrufe zugewiesen.

Der Name der Lizenzen oder Produktnamen in das Skript werden in Kursivschrift (siehe [Telefonsystem und plant aufrufen Produktnamen oder SKUs für das Skripting verwendet](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), nachdem das Beispiel) aufgeführt.

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan

| Produktname | SKU-Teilename |
|--------------|---------------|
| Enterprise E5 (mit Telefonsystem) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| Telefonsystem | MCOEV |
| Internationaler nationalen & Plan | MCOPSTN2 |
| Nationalen aufrufen (3000 Minuten pro Benutzer pro Monat für US/PR/CA 1200 Minuten pro Benutzer pro Monat für EU-Ländern) planen | MCOPSTN1 |
| Nationalen aufrufen planen (120 Minuten pro Benutzer pro Monat für jedes Land) </br>*Hinweis: dieser Plan ist nicht verfügbar in den USA*. | MCOPSTN5 |
| Nationalen aufrufen planen (240 Minuten pro Benutzer pro Monat für jedes Land) </br>*Hinweis: dieser Plan ist nicht verfügbar in den USA*. | MCOPSTN6 |
| Guthaben für Kommunikationen | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audiokonferenzen: Tipps und Skripts zum Zuweisen von Lizenzen

Hier ist, was Sie vor dem Zuweisen von Lizenzen für Audiokonferenzen wissen müssen.

- **Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für Audiokonferenzen zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.

- **Nächste Schritte**: Nachdem Sie Audiokonferenzen Lizenzen zuweisen möchten, müssen Sie kein Audiokonferenzanbieter zuweisen. Finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Ein Benutzer eine Audiokonferenz-Lizenz zuweisen

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Zuweisen von Lizenzen in einer Sammeloperation Audiokonferenzen

1. Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.

2. Laden Sie das Windows Azure Active Directory-Modul herunter und installieren Sie es. Download-Anweisungen und die Syntax finden Sie unter [Verwalten von Azure Active Directory mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:

Der Name der Lizenzen oder Produktnamen in das Skript werden in Kursivschrift aufgeführt. Finden Sie unter [Audiokonferenzen Produktnamen oder SKUS für das Skripting verwendet](#audio-conferencing-product-names-or-skus-used-for-scripting) für alle von der Produktnamen enthält.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Audio Conferencing Produktnamen oder SKUS für das Skripting verwendet

| Produktname | SKU-Teilename |
|--------------|---------------|
| Audiokonferenzen (Abonnement) | MCOMEETADV | 
| Audio-Konferenzen bezahlen pro Minute (Quellenbesteuerung)</br>*Hinweis: erfordert Communications haben eingerichtet und aktiviert werden*. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (ohne Audiokonferenz) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (mit Audiokonferenz) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Guthaben für Kommunikationen

Hier ist, was Sie vor dem Zuweisen von Lizenzen Communications haben, wissen müssen.

- **Enterprise-E5 Kunden**:, auch wenn Ihre Benutzer Enterprise E5 Lizenzen zugewiesen sind, empfohlen, dass die Kommunikation haben Lizenzen zugewiesen.

- **Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Ein Benutzer eine Lizenz Communications haben zuweisen

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Zuweisen von Lizenzen in einer Sammeloperation Communications haben

Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für Audiokonferenzen an. Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für Guthaben für Kommunikationen.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufplänen](set-up-calling-plans.md)
</br>
[Hinzufügen von Geld und Verwalten von Guthaben für Kommunikationen](add-funds-and-manage-communications-credits.md)
