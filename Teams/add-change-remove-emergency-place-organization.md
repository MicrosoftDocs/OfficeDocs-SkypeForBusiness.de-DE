---
title: Hinzufügen, Ändern, Entfernen von Orten für Notfallstandorte
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
description: Erfahren Sie, wie Sie einen Ort für einen Notfallstandort für Ihre Organisation im Microsoft Teams Admin Center hinzufügen, ändern oder entfernen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121503"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation

Abhängig von der Anzahl der physischen Standorte in Ihrer Organisation können Sie Orte für Gebäude, Stockwerke und Büros hinzufügen, um einen spezielleren Notfallstandort zu erstellen. Weitere [Informationen finden Sie unter](what-are-emergency-locations-addresses-and-call-routing.md) Verwalten von Notrufen.
  
Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel sie kosten, finden Sie unter [Teams-Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Hinzufügen eines Orts zu einem Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort hinzufügen möchten.
3. Klicken Sie **auf der** Registerkarte Orte auf **Hinzufügen.**
4. Geben Sie einen Ortsnamen ein, und klicken Sie dann auf **Übernehmen.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Ändern eines Orts für einen Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort ändern möchten.
3. Wählen Sie **auf der** Registerkarte Orte den Ort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten.**
4. Aktualisieren Sie die Ortsinformationen, und klicken Sie dann auf **Übernehmen.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Entfernen eines Orts von einem Notfallstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie in der Liste auf den Namen des Speicherorts, für den Sie einen Ort entfernen möchten.
3. Wählen Sie **auf der** Registerkarte Orte den Ort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Verwandte Themen

- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)