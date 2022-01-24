---
title: Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie einen Notfallstandort für Benutzer in Ihrer Organisation zuweisen oder ändern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004635be112bb8d38b88277e89c24d263b21ec37
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180898"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer

Unabhängig von [](pstn-connectivity.md) der PstN-Konnektivitätsoption, die Sie für Microsoft-Anrufpläne, Operator Verbinden oder Direct Routing auswählen, muss jeder Telefonnummer oder jedem Benutzer ein Notfallstandort &mdash; zugewiesen &mdash; werden.

Je nach Ihrer PSTN-Konnektivitätsoption kann jedoch die Art und Weise, wie Sie Notfallstandorte für einen Benutzer verwalten und zuweisen, variieren. Weitere Informationen finden Sie unter [Verwalten von Notrufen.](what-are-emergency-locations-addresses-and-call-routing.md)

In diesem Artikel wird beschrieben, wie Sie einen Notfallstandort für einen Benutzer zuweisen oder ändern. 

Dieser Artikel bezieht sich auf Anrufpläne und Verbinden.
  
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

Weitere [Informationen finden Sie unter Set-CsPhoneNumberAssignment.](/powershell/module/teams/set-csphonenumberassignment) 

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer](assign-change-emergency-place-user.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)
