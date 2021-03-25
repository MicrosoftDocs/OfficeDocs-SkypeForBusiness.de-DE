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
ms.openlocfilehash: 41eceb3618fae61308b90a88165ce1935ad6b30b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117233"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Telefonnummernliste für Ihre Organisation anzeigen

Es gibt verschiedene Arten von Telefonnummern, die Sie Benutzern oder anderen Diensten (Dienstnummern) zuweisen können, z. B. für Audiokonferenzen in Microsoft 365 oder Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>So zeigen Sie eine Liste aller Telefonnummern für Ihre Organisation an

![Ein Symbol mit dem Teams-Logo ](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit im linken Navigationsbereich des Skype for Business Admin Centers die Option **Voice** angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine Add-On-Lizenz für das **Telefonsystem** oder eine Add-On-Lizenz für **Audiokonferenzen** kaufen.

3. Informationen zum Anzeigen der zugewiesenen Telefonnummern finden Sie in der Spalte **Status.**

4. Zum Filtern der Ansicht klicken Sie auf das Filtersymbol. Im Bereich **Filter** können Sie die Dropdownliste verwenden, um Ihre Ansicht nach den

   - **Von Ihnen festgelegter** Zahlenbereich. Sie können nach der niedrigsten oder höchsten Zahl suchen.

   - Zahlen, die mit einer von Ihnen angegebenen Zahl beginnen.

   - Der **Aktivierungszustand von Zahlen**.

   - **Zahlentyp**.

   - **Telefonnummernstatus**.

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>So zeigen Sie alle Benutzern zugewiesenen Telefonnummern an

Wenn Sie Benutzer einrichten, möchten Sie möglicherweise nur die Liste der Telefonnummern sehen, die benutzern bereits zugewiesen sind und welche Telefonnummern verfügbar sind, um ihnen zugewiesen zu werden.
  
![Ein Symbol mit dem Teams-Logo ](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  Voice im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird, müssen  Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Lizenz für das Telefonsystem-Add-On oder eine Lizenz für **Audiokonferenzen** erwerben.

3. Wenn Sie die Zahlen schnell sortieren möchten, damit Sie sehen können, welche zugewiesen sind, klicken Sie auf die Spaltenüberschrift **Status.** Sie können auch auf das Filtersymbol klicken und dann ihre Ansicht filtern, um Telefonnummern zu sehen, die bereits Benutzern zugewiesen sind, oder nicht zugewiesene Nummern, die Sie einem Benutzer zuweisen können. Sie können nach folgenden Kriterien filtern:

   - **Benutzer zugewiesen**

   - **Der Konferenzbrücke zugewiesen** 

   - **Nicht zugewiesen**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>So zeigen Sie die VoIP-Benutzern zugewiesenen Telefonnummern an

Wenn Sie Benutzer in Ihrer Organisation einrichten, die Telefonanrufe tätigen und empfangen sollen, müssen Sie zuerst die Telefonnummern abrufen und diese dann den Benutzern zuweisen. Nachdem Sie Ihre Telefonnummern erhalten haben, möchten Sie möglicherweise nur noch den Aktivierungsstatus der Nummernzuweisungen anzeigen.

![Ein Symbol mit dem Teams-Logo ](media/teams-logo-30x30.png) **Mithilfe des Microsoft Teams Admin Centers** !
  
1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  Voice im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird, müssen  Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Lizenz für das Telefonsystem-Add-On oder eine Lizenz für **Audiokonferenzen** erwerben.

3. Klicken Sie auf das Filtersymbol, um Die Ansicht nach **Aktivierungszustand zu** filtern Sie können nach:

   - **Aktiviert**

   - **Aufgabe ausstehend**

   - **Aufgabe fehlgeschlagen**

   - **Update ausstehend**

   - **Update fehlgeschlagen**

## <a name="using-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Sie können das Teams PowerShell-Modul verwenden, um dieselben Informationen aus den vorherigen Abschnitten zu erhalten, aber Version 1.1.6 oder höher ist erforderlich, was die Integration des Skype for Business Online-Connectors umfasst. Weitere Informationen zum Modul finden Sie unter [Microsoft Teams PowerShell Overview](teams-powershell-overview.md).

Mithilfe des [Get-CsOnlineTelephoneNumber-Cmdlets](/powershell/module/skype/get-csonlinetelephonenumber) können Sie eine Liste aller Telefonnummern für Ihre Organisation sehen. Sie können beispielsweise den folgenden Befehl ausführen, um jede Telefonnummer und deren Zustand zu sehen:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Sie können alle Telefonnummern, die Benutzern zugewiesen sind, mithilfe des [Get-CsOnlineUser-Cmdlets](/powershell/module/skype/get-csonlineuser) sehen. Sie können beispielsweise den folgenden Befehl ausführen, um alle Benutzer mit einer zugewiesenen Telefonnummer zu sehen:

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