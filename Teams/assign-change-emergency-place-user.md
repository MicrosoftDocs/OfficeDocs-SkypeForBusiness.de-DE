---
title: Zuweisen oder Ändern von Orten für Notfallstandorte für Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie den Ort für einen Notfallstandort für Benutzer in Ihrer Organisation zuweisen oder ändern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9bd69356be22954ee1b1b44b2dcc1a52c1e72507
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634884"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern des Orts für einen Notfallstandort für einen Benutzer

Unabhängig von [](pstn-connectivity.md) der PstN-Konnektivitätsoption, die Sie für Microsoft-Anrufpläne, Operator Verbinden oder Direct Routing auswählen, muss jeder Telefonnummer oder jedem Benutzer ein Notfallstandort &mdash; zugewiesen &mdash; werden.

Je nach Ihrer PSTN-Konnektivitätsoption kann jedoch die Art und Weise, wie Sie Notfallstandorte für einen Benutzer verwalten und zuweisen, variieren. Weitere Informationen finden Sie unter [Verwalten von Notrufen.](what-are-emergency-locations-addresses-and-call-routing.md)

In diesem Artikel wird beschrieben, wie Sie einen Notfallstandort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern. 

Dieser Artikel bezieht sich auf Anrufpläne und Verbinden.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste Microsoft Teams Admin Center **auf**  >  **Sprachanrufnummern Telefon .**

2. Klicken Sie **Telefon Seite** Zahlen bearbeiten  auf die Registerkarte Zahlen, wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**.

3. Gehen Sie **im** Bereich Bearbeiten **unter Notfallstandort** wie folgt vor:

    - Um einen Ort zuzuordnen, suchen Sie nach dem Speicherort oder Ort, und wählen Sie dann den Ort in den Suchergebnissen aus.

    - Wenn Sie den Ort ändern möchten, der dem Benutzer bereits zugewiesen ist, klicken Sie auf **X,** um die vorhandene Position zu entfernen, suchen Sie nach dem Ort, den Sie zuweisen möchten, und wählen Sie ihn aus.

4. Je nachdem, ob Sie dem Benutzer eine E-Mail mit seinen Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie **Dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden**. Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer](assign-change-emergency-location-user.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)