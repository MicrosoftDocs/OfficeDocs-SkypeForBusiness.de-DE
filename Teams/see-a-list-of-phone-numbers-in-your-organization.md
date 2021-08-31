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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie Microsoft Teams Admin Center verwenden können, um eine Liste aller Telefonnummern in Ihrer Organisation und aller Nummern, die Benutzern zugewiesen oder nicht zugewiesen sind, ein- oder auszuweisen.
ms.openlocfilehash: d7de480508020dac24a63b5923af9cf2481c691b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733974"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Telefonnummernliste für Ihre Organisation anzeigen

Es gibt verschiedene Arten von Telefonnummern, die Sie Benutzern oder anderen Diensten (Servicenummern) zuweisen können, z. B. für Audiokonferenzen in Microsoft 365 oder Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>So zeigen Sie eine Liste aller Telefonnummern für Ihre Organisation an

![Ein Symbol mit dem Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.

3. Informationen zum Anzeigen der zugewiesenen Telefonnummern finden Sie in der **Spalte Status.**

4. Zum Filtern der Ansicht klicken Sie auf das Filtersymbol. Im **Bereich Filter** können Sie die Dropdownliste verwenden, um die Ansicht nach den hier aufgeführten Filtern zu filtern:

   - **Von Ihnen festgelegter** Zahlenbereich Sie können nach der niedrigsten oder der höchsten Zahl suchen.

   - Zahlen, die mit einer von Ihnen angegebenen Zahl beginnen.

   - Status **der Nummernaktivierung.**

   - **Zahlentyp**.

   - Telefon den **Zahlenstatus**.

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>So zeigen Sie alle Benutzern zugewiesenen Telefonnummern an

Wenn Sie Benutzer einrichten, möchten Sie vielleicht nur eine Liste der Telefonnummern sehen, die Benutzern bereits zugewiesen sind und welche Telefonnummern verfügbar sind, die ihnen zugewiesen werden können.
  
![Ein Symbol mit dem Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  "Sprache" im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Telefonsystem-Add-On-Lizenz oder eine Add-On-Lizenz für **Audiokonferenzen** erwerben. 

3. Wenn Sie die Zahlen schnell sortieren möchten, damit Sie sehen können, welche zugewiesen sind, klicken Sie auf die **Spaltenüberschrift** Status. Sie können auch auf das Filtersymbol klicken und dann Ihre Ansicht filtern, um Telefonnummern, die Benutzern bereits zugewiesen sind, oder nicht zugewiesene Nummern, die Sie Benutzern zuweisen können, zu sehen. Sie können nach folgenden Kriterien filtern:

   - **Benutzer zugewiesen**

   - **Einer Konferenzbrücke zugewiesen** 

   - **Nicht zugewiesen**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>So zeigen Sie die VoIP-Benutzern zugewiesenen Telefonnummern an

Wenn Sie Benutzer in Ihrer Organisation einrichten, die Telefonanrufe tätigen und empfangen sollen, müssen Sie zuerst die Telefonnummern abrufen und diese dann den Benutzern zuweisen. Nachdem Sie Ihre Telefonnummern erhalten haben, möchten Sie möglicherweise nur noch den Aktivierungsstatus der Nummernzuweisungen sehen.

![Ein Symbol mit dem Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers!**
  
1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  "Sprache" im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Telefonsystem-Add-On-Lizenz oder eine Add-On-Lizenz für **Audiokonferenzen** erwerben. 

3. Klicken Sie auf das Filtersymbol, um die Ansicht nach **Aktivierungszustand zu filtern** Sie können nach:

   - **Aktiviert**

   - **Zuweisung ausstehend**

   - **Zuordnung fehlgeschlagen**

   - **Update steht noch aus**

   - **Aktualisierung fehlgeschlagen**

## <a name="using-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Sie können das Teams PowerShell-Modul verwenden, um dieselben Informationen aus den vorherigen Abschnitten zu erhalten, aber Version 1.1.6 oder höher ist erforderlich, die die Integration des Skype for Business Online-Connectors umfasst. Weitere Informationen zum Modul finden Sie unter Übersicht [Microsoft Teams PowerShell.](teams-powershell-overview.md)

Mit dem [Cmdlet Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) können Sie eine Liste aller Telefonnummern für Ihre Organisation sehen. Sie können z. B. den folgenden Befehl ausführen, um die einzelnen Telefonnummern und deren Status zu sehen:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Sie können alle Telefonnummern, die Benutzern zugewiesen sind, mithilfe des [Cmdlets Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) sehen. Sie können z. B. den folgenden Befehl ausführen, um alle Benutzer mit einer zugewiesenen Telefonnummer zu sehen:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)