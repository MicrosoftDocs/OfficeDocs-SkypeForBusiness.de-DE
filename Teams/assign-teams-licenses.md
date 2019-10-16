---
title: Zuweisen von Teams-Lizenzen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Hier erfahren Sie, wie Sie Lizenzen für Features wie Audio-Conferencing, Telefon System und Anrufpläne zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e5783a2fa0c6479d59e563b9001b736015f20fa
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515780"
---
# <a name="assign-microsoft-teams-licenses"></a>Zuweisen von Microsoft Teams-Lizenzen

Sie können Ihren Benutzern Lizenzen für Funktionen wie Audio-Conferencing, Telefon System und Anrufpläne zuweisen. In diesem Artikel wird erläutert, wie Sie diese Lizenzen in loser Schüttung und für einen einzelnen Benutzer hinzufügen. 

> [!IMPORTANT]
> Informationen dazu, welche Lizenzen Sie kaufen müssen und wie Sie Sie erwerben, finden Sie in der [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) – je nach Ihrem Office 365-Plan –, damit Benutzer Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihres Unternehmens erhalten.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen

Hier erfahren Sie, was Sie vor dem Zuweisen von Audiokonferenz-, Telefon System-und Anruf Plan Lizenzen wissen müssen.

- **Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine Telefonsystemlizenz zuweisen. Weisen Sie KEINEN Anrufplan zu.

- **Wartezeit nach dem Zuweisen von Lizenzen**: aufgrund der Wartezeit zwischen Office 365 und Microsoft Teams kann es bis zu 24 Stunden dauern, bis ein Benutzer einen Anrufplan zugewiesen hat, nachdem Sie eine Lizenz zugewiesen haben. Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen ist, wenden Sie [sich bitte an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.

- **Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Zuweisen einer Telefonanlage und einer Anruf Plan Lizenz für einen Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Zuweisen von Telefon System-und Anruf Plan Lizenzen in loser Schüttung

1. Installieren Sie den Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW. Ist das Modul nicht installiert? Informationen zum Herunterladen finden Sie [im Microsoft Online Services-Anmelde Assistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) .

2. Installieren Sie das Windows Azure Active Directory-Modul. Ist das Modul nicht installiert? Informationen zum Herunterladen von Anweisungen und zur Cmdlet-Syntax finden Sie unter [Verwalten von Azure AD mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

3. Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:

In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Telefonsysteme und einer Lizenz für einen Plan für Inlandsanrufe zugewiesen.

Der Name der Lizenzen oder Produktnamen im Skript wird kursiv angezeigt (siehe [Telefon System-und Anrufplan-Produktnamen oder SKUs, die für die Skripterstellung verwendet](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)werden, nach dem Beispiel).

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
| Plan für Inlands #a0 Auslandsgespräche | MCOPSTN2 |
| Plan für Inlandsanrufe (3000 Minuten pro Nutzer/Monat für US/PR/ca, 1200 Minuten pro Nutzer/Monat für EU-Länder) | MCOPSTN1 |
| Plan für Inlandsanrufe (120 Minuten pro Nutzer/Monat für jedes Land) </br>*Hinweis: dieser Plan steht in den USA nicht zur Verfügung*. | MCOPSTN5 |
| Plan für Inlandsanrufe (240 Minuten pro Nutzer/Monat für jedes Land) </br>*Hinweis: dieser Plan steht in den USA nicht zur Verfügung*. | MCOPSTN6 |
| Guthaben für Kommunikationen | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen

Hier erfahren Sie, was Sie vor dem Zuweisen von Lizenzen für Audiokonferenzen wissen müssen.

- **Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für Audiokonferenzen zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.

- **Nächste Schritte**: Nachdem Sie Lizenzen für Audiokonferenzen zugewiesen haben, müssen Sie einen Audiokonferenz-Anbieter zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Audiokonferenz-Anbieter](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Zuweisen einer Audiokonferenz-Lizenz für einen Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Zuweisen von Lizenzen für Audiokonferenzen im Massen Format

1. Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.

2. Laden Sie das Windows Azure Active Directory-Modul herunter und installieren Sie es. Informationen zum Herunterladen von Anweisungen und zur Cmdlet-Syntax finden Sie unter [Verwalten von Azure AD mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:

Der Name der Lizenzen oder Produktnamen im Skript wird kursiv angezeigt. Sehen Sie sich die [Produktnamen oder SKUs für Audiokonferenzen](#audio-conferencing-product-names-or-skus-used-for-scripting) an, die für die Skripterstellung für alle Produktnamen verwendet werden.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Für die Skripterstellung verwendete Produktnamen oder SKUs für Audio-Konferenzen

| Produktname | SKU-Teilename |
|--------------|---------------|
| Audiokonferenzen (Abonnement) | MCOMEETADV | 
| Audio-Konferenzgebühren pro Minute (im Voraus bezahlen)</br>*Hinweis: die Einrichtung und Aktivierung von Kommunikationsguthaben ist erforderlich*. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (ohne Audiokonferenz) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (mit Audiokonferenz) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Guthaben für Kommunikationen

Hier erfahren Sie, was Sie wissen müssen, bevor Sie Lizenzen für Communications-Guthaben zuweisen.

- **Enterprise E5-Kunden**: selbst wenn ihren Benutzern Enterprise E5-Lizenzen zugewiesen sind, empfehlen wir Ihnen weiterhin, Ihnen Kommunikationsguthaben-Lizenzen zuzuweisen.

- **Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Zuweisen einer Lizenz für Kommunikations Kredite zu einem Benutzer

Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Zuweisen von Lizenzen für Kommunikations Kredite in loser Schüttung

Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für Audiokonferenzen an. Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für Guthaben für Kommunikationen.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufplänen](set-up-calling-plans.md)
</br>
[Hinzufügen von Geld und Verwalten von Guthaben für Kommunikationen](add-funds-and-manage-communications-credits.md)
