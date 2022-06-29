---
title: Anzeigen einer Liste der Telefonnummern in Ihrer Organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
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
description: Erfahren Sie, wie Sie das Microsoft Teams Admin Center verwenden, um eine Liste aller Telefonnummern in Ihrer Organisation und aller Nummern anzuzeigen, die Benutzern zugewiesen oder nicht zugewiesen sind.
ms.openlocfilehash: 84162b3971b1730df114482d30820dcf7e86a684
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494462"
---
# <a name="see-a-list-of-telephone-numbers"></a>Anzeigen einer Liste von Telefonnummern 

Es gibt verschiedene Arten von Telefonnummern, die Sie Benutzern oder Sprachanwendungen wie [Audiokonferenzen](deploy-audio-conferencing-teams-landing-page.md) oder [Anrufwarteschleifen](plan-auto-attendant-call-queue.md) zuweisen können. Weitere Informationen finden [Sie unter Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-landing-page).

Dieser Artikel bezieht sich auf Anrufpläne und Telefonieanbieter. Informationen zum Direct Routing finden Sie unter [Konfigurieren der Telefonnummer und Aktivieren von Enterprise-VoIP](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>So zeigen Sie alle Telefonnummern in Ihrer Organisation an

So zeigen Sie eine Liste aller Telefonnummern in Ihrer Organisation an:

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

3. Informationen zum Anzeigen der zugewiesenen Telefonnummern finden Sie in der Spalte **"Zuordnungsstatus"** , in der auch angezeigt wird, welcher Diensttyp der Nummer zugewiesen ist.

4. Klicken Sie zum Filtern der Ansicht auf das Filtersymbol. Im **Filterbereich** können Sie die Dropdownliste verwenden, um Ihre Ansicht nach folgendem zu filtern:

   - Von Ihnen festgelegter **Nummernbereich**. Sie können nach der niedrigsten oder höchsten Zahl suchen.

   - Zahlen, die mit einer von Ihnen angegebenen Zahl beginnen.

   - **Nummernaktivierungsstatus**.

   - **Zahlentyp**.

   - **Telefonnummernstatus**.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>So zeigen Sie alle Telefonnummern an, die Benutzern zugewiesen sind

Wenn Sie Benutzer einrichten, möchten Sie möglicherweise nur die Liste der Telefonnummern anzeigen, die benutzern bereits zugewiesen sind und welche Telefonnummern verfügbar sind, um ihnen zugewiesen zu werden.

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die **VoIP-Option** im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz**, eine **Telefonsystem-Add-On-Lizenz** oder eine **Audiokonferenz-Add-On-Lizenz** erwerben.

3. Wenn Sie die Zahlen schnell sortieren möchten, damit Sie sehen können, welche zugewiesen sind, klicken Sie auf die Spaltenüberschrift **"Zuordnungsstatus** ". Sie können auch auf das Filtersymbol klicken und dann Ihre Ansicht filtern, um Telefonnummern anzuzeigen, die bereits Benutzern zugewiesen sind, oder nicht zugewiesene Nummern, die Sie einem Benutzer zuweisen können. Sie können nach folgenden Kriterien filtern:

   - **Benutzer zugewiesen**
   - **Konferenzbrücke zugewiesen** 
   - **VoIP-App zugewiesen (automatische Telefonzentrale/Anrufwarteschleife)**
   - **Nicht zugewiesen**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>So zeigen Sie alle Telefonnummern an, die VoIP-Benutzern zugewiesen sind

Wenn Sie Benutzer in Ihrer Organisation einrichten, um Telefonanrufe zu tätigen und zu empfangen, müssen Sie zuerst die Telefonnummern abrufen und sie dann Ihren Benutzern zuweisen. Nachdem Sie Ihre Telefonnummern erhalten haben, möchten Sie möglicherweise den Aktivierungsstatus der Nummernzuweisungen anzeigen.
  
1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

3. Klicken Sie auf das Filtersymbol, um ihre Ansicht nach **Aktivierungsstatus** zu filtern. Sie können nach folgenden Kriterien filtern:

   - **Aktiviert**
   - **Zuordnung ausstehend**
   - **Zuordnung fehlgeschlagen**
   - **Update ausstehend**
   - **Aktualisierung fehlgeschlagen**

## <a name="using-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Sie können das Teams PowerShell-Modul verwenden, um dieselben Informationen aus den vorherigen Abschnitten abzurufen, aber Version 1.1.6 oder höher ist erforderlich, was die Integration des Skype for Business Online-Connectors umfasst. Weitere Informationen zum Modul finden Sie unter [Microsoft Teams PowerShell Overview](teams-powershell-overview.md).

Um eine Liste aller Telefonnummern anzuzeigen, die Sie für Ihre Organisation haben, verwenden Sie das Cmdlet [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) . Führen Sie beispielsweise den folgenden Befehl aus, um jede Telefonnummer, ihren Typ und ihren Zustand anzuzeigen:

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

Um alle Telefonnummern anzuzeigen, die Benutzern zugewiesen sind, verwenden Sie das Cmdlet ["Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) ". Um beispielsweise alle Benutzer mit zugewiesener Telefonnummer anzuzeigen, führen Sie den folgenden Befehl aus:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
