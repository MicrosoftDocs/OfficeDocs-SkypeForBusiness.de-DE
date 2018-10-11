---
title: Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Aktivieren oder Deaktivieren der Funktion für den Gastzugriff in Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498121"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
======================================

Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können. 

Die Gasteinstellungen werden in Azure Active Directory festgelegt. Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden. Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.


> [!IMPORTANT]
> Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>Konfigurieren von Gastzugriff in der Teams & Skype für Business-Verwaltungskonsole

1.  Melden Sie sich bei der Teams & Skype für Business Administrationscenter.

2.  Wählen Sie **gesamte Org Einstellungen** > **Gastzugriff**.

3. Legen Sie die Umschaltfläche **Gast Zugriffsberechtigung in Microsoft-Teams** auf **aktiviert**.

    ![Legen Sie Gast Access Switch auf auf zulassen ](media/set-up-guests-image1.png)

4.  Legen Sie die Schaltet für **aufrufen**, **Besprechung**und **Messaging** zum **ein-** oder **Ausschalten**, je nach dem Zugriff, den Sie zulassen möchten.

5.  Klicken Sie auf **Speichern**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Verwenden von PowerShell, aktivieren oder deaktivieren Sie Gastzugriff

1.  Laden Sie die Skype für Business Online-PowerShell-Modul aushttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Verbinden Sie eine PowerShell-Sitzung mit der Skype für Business Online Endpunkt.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Überprüfen Sie die Konfiguration und wenn `AllowGuestUser` ist `$False`, verwenden Sie das Cmdlet " [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) ", um diese Liste festgelegt, `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Sie können jetzt Gastbenutzer in Teams für Ihre Organisation verwenden.

## <a name="more-information"></a>Weitere Informationen

Das folgende Video ausführliche Informationen zum Gastzugriff.

|  |  |
|---------|---------|
| Hinzufügen von Gästen in Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
