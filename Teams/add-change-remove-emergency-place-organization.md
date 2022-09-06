---
title: Hinzufügen, Ändern, Entfernen von Orten für Notfallstandorte
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie einen Ort für einen Notfallstandort für Ihre Organisation hinzufügen, ändern oder entfernen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ccf72868819c515a2f7320b112f81f31f65a34
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606714"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation

Je nach Anzahl der physischen Standorte in Ihrer Organisation können Sie *Orte* für Gebäude, Stockwerke und Büros hinzufügen, um einen spezifischeren Notfallstandort zu erstellen.

Je nach Ihrer PSTN-Konnektivitätsoption kann jedoch die Verwaltung von Notfallstandorten und Standortanforderungen variieren. Weitere Informationen finden [Sie unter Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md).

In diesem Artikel wird beschrieben, wie Sie einen *Ort* für einen Notfallstandort für Ihre Organisation hinzufügen, ändern oder entfernen.

Dieser Artikel bezieht sich auf Microsoft Calling Plans, Operator Connect, Telefonieanbieter mit Mobil (Public Preview Release) und Direct Routing.

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Hinzufügen eines Orts zu einem Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Notfalladressen** für **Standorte** > .
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort hinzufügen möchten.
3. Klicken Sie auf der Registerkarte **"Orte** " auf **"Hinzufügen"**.
4. Geben Sie einen Ortsnamen ein, und klicken Sie dann auf **Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Ändern eines Orts für einen Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Notfalladressen** für **Standorte** > .
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort ändern möchten.
3. Wählen Sie auf der Registerkarte " **Orte** " die Stelle aus, die Sie ändern möchten, und klicken Sie dann auf **"Bearbeiten**".
4. Aktualisieren Sie die Ortsinformationen, und klicken Sie dann auf **Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Entfernen eines Orts aus einem Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Notfalladressen** für **Standorte** > .
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort entfernen möchten.
3. Wählen Sie auf der Registerkarte **"Orte** " die Stelle aus, die Sie entfernen möchten, und klicken Sie dann auf **"Löschen"**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)