---
title: Eine Liste der Telefonnummern in Ihrer Organisation
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
description: Erfahren Sie, wie Sie Microsoft Teams Admin Center verwenden können, um eine Liste aller Telefonnummern in Ihrer Organisation und aller Nummern, die Benutzern zugewiesen oder nicht zugewiesen sind, zu sehen.
ms.openlocfilehash: 1473a87a190a671d537a958b34e839d53a668f3a
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432487"
---
# <a name="see-a-list-of-telephone-numbers"></a>Eine Liste der Telefonnummern 

Es gibt verschiedene Arten von Telefonnummern, die Sie Benutzern oder Sprachanwendungen wie [Audiokonferenzen](deploy-audio-conferencing-teams-landing-page.md) oder Anrufwarteschleifen [zuweisen können.](plan-auto-attendant-call-queue.md) Weitere Informationen finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](/microsoftteams/manage-phone-numbers-landing-page)

Dieser Artikel bezieht sich auf Anrufpläne und Verbinden. Informationen zu Direct Routing finden Sie unter Konfigurieren der [Telefonnummer und Aktivieren von Enterprise-Voicemail und -Voicemail.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>So sehen Sie alle Telefonnummern in Ihrer Organisation

So sehen Sie eine Liste aller Telefonnummern in Ihrer Organisation:

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

3. Informationen zum Anzeigen der zugewiesenen  Telefonnummern finden Sie in der Spalte Zuordnungsstatus, in der auch der Diensttyp angezeigt wird, dem die Nummer zugewiesen ist.

4. Zum Filtern der Ansicht klicken Sie auf das Filtersymbol. Im **Bereich Filter** können Sie die Dropdownliste verwenden, um die Ansicht nach den hier aufgeführten Filtern zu filtern:

   - **Von Ihnen festgelegter** Zahlenbereich Sie können nach der niedrigsten oder der höchsten Zahl suchen.

   - Zahlen, die mit einer von Ihnen angegebenen Zahl beginnen.

   - Status **der Nummernaktivierung.**

   - **Zahlentyp**.

   - Telefon den **Zahlenstatus .**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>So sehen Sie alle Telefonnummern, die Benutzern zugewiesen sind

Wenn Sie Benutzer einrichten, möchten Sie vielleicht nur eine Liste der Telefonnummern sehen, die Benutzern bereits zugewiesen sind und welche Telefonnummern verfügbar sind, die ihnen zugewiesen werden können.

1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

    > [!IMPORTANT]
    > Damit die Option  "Sprache" im linken Navigationsbereich im Microsoft Teams Admin Center angezeigt wird, müssen Sie zuerst mindestens eine **Enterprise E5-Lizenz,** eine Telefonsystem-Add-On-Lizenz oder eine Add-On-Lizenz für **Audiokonferenzen** erwerben. 

3. Um die Zahlen schnell zu sortieren, damit Sie sehen können, welche zugewiesen sind, klicken Sie **auf** die Spaltenüberschrift Zuordnungsstatus. Sie können auch auf das Filtersymbol klicken und dann Ihre Ansicht filtern, um Telefonnummern zu sehen, die Benutzern bereits zugewiesen sind, oder nicht zugewiesene Nummern, die Sie Benutzern zuweisen können. Sie können nach folgenden Kriterien filtern:

   - **Benutzer zugewiesen**
   - **Einer Konferenzbrücke zugewiesen** 
   - **Sprachanruf-App zugewiesen (automatische Telefonzentrale/Anrufwarteschleife)**
   - **Nicht zugewiesen**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>So sehen Sie alle Telefonnummern, die Sprachbenutzern zugewiesen sind

Wenn Sie Benutzer in Ihrer Organisation für das Anrufen und Empfangen von Telefonanrufen einrichten, müssen Sie zuerst die Telefonnummern erhalten und diese dann Ihren Benutzern zuweisen. Nachdem Sie Ihre Telefonnummern erhalten haben, möchten Sie möglicherweise den Aktivierungsstatus der Nummernzuweisungen sehen.
  
1. Wechseln Sie zum **Microsoft Teams Admin Center**.

2. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > **Telefonnummern**.

3. Klicken Sie auf das Filtersymbol, um die Ansicht nach **Aktivierungszustand zu filtern.** Sie können nach folgenden Kriterien filtern:

   - **Aktiviert**
   - **Zuweisung ausstehend**
   - **Zuordnung fehlgeschlagen**
   - **Update steht noch aus**
   - **Aktualisierung fehlgeschlagen**

## <a name="using-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Sie können das Teams PowerShell-Modul verwenden, um dieselben Informationen aus den vorherigen Abschnitten zu erhalten, aber Version 1.1.6 oder höher ist erforderlich, die die Integration des Skype for Business Online-Connectors umfasst. Weitere Informationen zum Modul finden Sie unter Übersicht [Microsoft Teams PowerShell.](teams-powershell-overview.md)

Wenn Sie eine Liste aller Telefonnummern für Ihre Organisation sehen möchten, verwenden Sie das [Cmdlet Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Führen Sie z. B. den folgenden Befehl aus, um die einzelnen Telefonnummern und deren Status zu sehen:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Zum Einsehen aller Telefonnummern, die Benutzern zugewiesen sind, verwenden Sie das [Cmdlet Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Wenn Sie beispielsweise alle Benutzer mit einer zugewiesenen Telefonnummer sehen möchten, führen Sie den folgenden Befehl aus:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)