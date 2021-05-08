---
title: Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie einen Notfallstandort für Benutzer in Ihrer Organisation zuweisen oder ändern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102981"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer

Wenn Sie Anrufpläne einrichten, müssen Sie jeder Telefonnummer oder jedem Benutzer einen Notfallstandort zuweisen. In europäischen Ländern wird der Notfallstandort der Telefonnummer zugeordnet, wenn Sie ihn von Microsoft 365 oder Office 365 oder wenn Sie eine Telefonnummer zu Microsoft 365 oder Office 365. In den USA wird der Notfallstandort der Telefonnummer zugeordnet, wenn sie dem Benutzer zugewiesen wird. Die Notfalladresse kann geändert werden, wenn der Benutzer, dem sie zugewiesen ist, an einen neuen Standort wechselt. Weitere Informationen zu Notfalladressen und -standorten finden Sie unter Was sind Notfallstandorte, Notfallstandorte [und Anrufrouting?.](./what-are-emergency-locations-addresses-and-call-routing.md)
  
Informationen dazu, wie Sie Anrufpläne erhalten und was sie kosten, finden Sie unter [Teams-Add-On-Lizenzierung.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
Sie können einen Notfallstandort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste Microsoft Teams Admin Center **auf**  >  **Sprachanrufnummern Telefon .**

2. Klicken Sie **Telefon Der** Telefonnummern-Seite auf die Registerkarte Zahlen, wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**. 

3. Gehen Sie **im** Bereich Bearbeiten **unter Notfallstandort** wie folgt vor:

   - Um einen Notfallstandort zuzuordnen, suchen Sie einen Notfallstandort, und wählen Sie diesen aus.

   - Wenn Sie den dem Benutzer bereits zugewiesenen Notfallstandort ändern möchten, klicken Sie auf **X,** um den vorhandenen Standort zu entfernen. Suchen Sie dann nach dem Standort, den Sie zuweisen möchten, und wählen Sie ihn aus.

4. Je nachdem, ob Sie dem Benutzer eine E-Mail mit seinen Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie **Dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden**. Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer](assign-change-emergency-place-user.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)