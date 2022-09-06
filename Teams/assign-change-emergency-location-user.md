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
description: In diesem Artikel erfahren Sie, wie Sie Benutzern in Ihrer Organisation einen Notfallstandort zuweisen oder ändern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2562661a08c98c15a24a5e7db6a0f31dee864573
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606604"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer

Unabhängig von der [PSTN-Konnektivitätsoption](pstn-connectivity.md) wählen&mdash;Sie Microsoft-Anrufpläne, Telefonieanbieter, Telefonieanbieter mit Mobil (Öffentliche Vorschauversion) oder Direct Routing&mdash;, einem Notfallstandort muss jeder Telefonnummer oder jedem Benutzer zugewiesen werden.

Je nach Ihrer PSTN-Konnektivitätsoption kann jedoch variieren, wie Sie Notfallstandorte für einen Benutzer verwalten und zuweisen. Weitere Informationen finden [Sie unter Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md).

In diesem Artikel wird beschrieben, wie Sie einen Notfallstandort für einen Benutzer zuweisen oder ändern. 

Dieser Artikel bezieht sich auf Anrufpläne, Telefonieanbieter und Telefonieanbieter mit Mobil (Öffentliche Vorschauversion).
  
Sie können einen Notfallstandort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"VoIP-Telefonnummern** > **"**.

2. Klicken Sie auf der Seite **"Telefonnummern** " auf die Registerkarte " **Zahlen** ", wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **"Bearbeiten**".

3. **Führen Sie im Bereich "Bearbeiten"** unter **"Notfallstandort**" eine der folgenden Aktionen aus:

   - Um einen Notfallstandort zuzuweisen, suchen Sie nach einem Notfallstandort, und wählen Sie diesen aus.

   - Um den Notfallstandort zu ändern, der dem Benutzer bereits zugewiesen ist, klicken Sie auf **X** , um den vorhandenen Standort zu entfernen, und suchen Sie dann nach dem Standort, den Sie zuweisen möchten, und wählen Sie diesen aus.

4. Je nachdem, ob Sie dem Benutzer eine E-Mail mit Angabe seiner Telefonnummer senden möchten, deaktivieren oder aktivieren Sie die Option **Benutzer eine E-Mail mit Angabe der Telefonnummer senden**. Diese ist standardmäßig aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer](assign-change-emergency-place-user.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)
