---
title: Telefonnummernliste für Ihre Organisation anzeigen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie im Microsoft Teams Admin Center eine Liste aller Telefonnummern in Ihrer Organisation und aller Nummern sehen, die Benutzern zugewiesen oder nicht zugewiesen sind.
ms.openlocfilehash: 61e1fb59ba5b68aeb2ab2af51b2ef91202e43678
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918901"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Telefonnummernliste für Ihre Organisation anzeigen

Es gibt verschiedene Arten von Telefonnummern, die Sie Benutzern oder anderen Diensten (Servicenummern) zuweisen können, z. B. für Audiokonferenzen in Microsoft 365 oder Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>So zeigen Sie eine Liste aller Telefonnummern für Ihre Organisation an

![Symbol mit dem Logo ](media/teams-logo-30x30.png) **"Teams" im Microsoft Teams Admin Center**

1. Wechseln Sie zum **Microsoft Teams Admin Center.**

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.

3. Informationen zum Anzeigen der zugewiesenen Telefonnummern finden Sie in der **Spalte "Status".**

4. Zum Filtern der Ansicht klicken Sie auf das Filtersymbol. Im **Filterbereich** können Sie die Dropdownliste verwenden, um die Ansicht nach den von Ihnen verwendeten Filtern zu filtern:

   - **Von Ihnen festgelegter** Zahlenbereich. Sie können nach der niedrigsten oder der höchsten Zahl suchen.

   - Zahlen, die mit einer von Ihnen angegebenen Zahl beginnen.

   - Status **der Nummernaktivierung.**

   - **Zahlentyp.**

   - **Telefonnummernstatus.**

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>So zeigen Sie alle Benutzern zugewiesenen Telefonnummern an

Beim Einrichten von Benutzern möchten Sie vielleicht nur die Liste der Telefonnummern sehen, die Benutzern bereits zugewiesen sind und welche Telefonnummern ihnen zugewiesen werden können.
  
![Symbol mit dem Logo ](media/teams-logo-30x30.png) **"Teams" im Microsoft Teams Admin Center**

1. Wechseln Sie zum **Microsoft Teams Admin Center.**

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  "Sprache" im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird,  müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Lizenz für das Telefonsystem-Add-On oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.

3. Wenn Sie die Zahlen schnell sortieren möchten, damit Sie sehen können, welche zugewiesen sind, klicken Sie auf die Spaltenüberschrift **"Status".** Sie können auch auf das Filtersymbol klicken und dann Ihre Ansicht filtern, um Telefonnummern, die Bereits Benutzern zugewiesen sind, oder nicht zugewiesene Nummern, die Sie einem Benutzer zuweisen können, zu sehen. Sie können nach folgenden Kriterien filtern:

   - **Benutzer zugewiesen**

   - **Einer Konferenzbrücke zugewiesen** 

   - **Nicht zugewiesen**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>So zeigen Sie die VoIP-Benutzern zugewiesenen Telefonnummern an

Wenn Sie Benutzer in Ihrer Organisation einrichten, die Telefonanrufe tätigen und empfangen sollen, müssen Sie zuerst die Telefonnummern abrufen und diese dann den Benutzern zuweisen. Nachdem Sie Ihre Telefonnummern erhalten haben, möchten Sie möglicherweise nur noch den Aktivierungsstatus der Nummernzuweisungen anzeigen.

![Symbol mit dem Logo ](media/teams-logo-30x30.png) **"Teams" im Microsoft Teams Admin Center!**
  
1. Wechseln Sie zum **Microsoft Teams Admin Center.**

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  "Sprache" im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird,  müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Lizenz für das Telefonsystem-Add-On oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.

3. Klicken Sie auf das Filtersymbol, um die Ansicht nach **Aktivierungszustand zu filtern.** Sie können nach:

   - **Aktiviert**

   - **Aufgabe ausstehend**

   - **Aufgabe fehlgeschlagen**

   - **Update ausstehend**

   - **Update fehlgeschlagen**

## <a name="using-the-teams-powershell-module"></a>Verwenden des Teams -PowerShell-Moduls

Sie können das Teams -PowerShell-Modul verwenden, um dieselben Informationen aus den vorherigen Abschnitten zu erhalten, aber Version 1.1.6 oder höher ist erforderlich, einschließlich der Integration des Skype for Business Online-Connectors. Weitere Informationen zum Modul finden Sie in der [Übersicht über Microsoft Teams PowerShell.](teams-powershell-overview.md)

Sie können eine Liste aller Telefonnummern, die Sie für Ihre Organisation haben, mithilfe des [Cmdlets "Get-CsOnlineTelephoneNumber"](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber) sehen. Sie können z. B. den folgenden Befehl ausführen, um die einzelnen Telefonnummern und deren Status zu sehen:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Sie können alle Telefonnummern, die Benutzern zugewiesen sind, mithilfe des [Cmdlets "Get-CsOnlineUser"](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser) sehen. Beispielsweise können Sie den folgenden Befehl ausführen, um alle Benutzer mit einer zugewiesenen Telefonnummer zu sehen:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser)
