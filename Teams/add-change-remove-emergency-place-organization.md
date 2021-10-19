---
title: Hinzufügen, Ändern und Entfernen von Orten für Notfallstandorte
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie einen Ort für einen Notfallstandort für Ihre Organisation im Microsoft Teams Admin Center hinzufügen, ändern oder entfernen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2bf3e2fad1ee0f0182e2b3a25f2be78f5ef68823
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465965"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation

Je nach Anzahl physischer Standorte in Ihrer Organisation können Sie Orte für Gebäude, Stockwerke und Büros hinzufügen, um einen spezielleren Notfallstandort zu erstellen. Weitere [Informationen finden Sie unter Verwalten von](what-are-emergency-locations-addresses-and-call-routing.md) Notrufen.

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Hinzufügen eines Orts zu einem Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie in der Liste auf den Namen des Orts, für den Sie einen Ort hinzufügen möchten.
3. Klicken Sie **auf** der Registerkarte Orte auf **Hinzufügen**.
4. Geben Sie einen Ortsnamen ein, und klicken Sie dann auf **Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsOnlineLisLocation.](/powershell/module/skype/new-csonlinelislocation)
    
## <a name="change-a-place-for-an-emergency-location"></a>Ändern eines Orts für einen Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie in der Liste auf den Namen des Orts, für den Sie einen Ort ändern möchten.
3. Wählen Sie **auf** der Registerkarte Orte den Ort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.
4. Aktualisieren Sie die Ortsinformationen, und klicken Sie dann auf **Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="remove-a-place-from-an-emergency-location"></a>Entfernen eines Orts aus einem Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort entfernen möchten.
3. Wählen Sie **auf** der Registerkarte Orte den Ort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Remove-CsOnlineLisLocation.](/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>Verwandte Themen

- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)