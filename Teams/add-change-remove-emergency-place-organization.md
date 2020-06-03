---
title: Hinzufügen, ändern und Entfernen von Orten für Notfall Standorte
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie einen Ort für einen Notfall Standort für Ihre Organisation im Microsoft Teams Admin Center hinzufügen, ändern oder entfernen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539432"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation

Je nach der Anzahl der physikalischen Standorte in Ihrer Organisation können Sie Orte für Gebäude, Etagen und Büros hinzufügen, um einen spezifischeren Notfall Standort zu erstellen. Weitere Informationen finden Sie unter [Verwalten von Notruf anrufen](what-are-emergency-locations-addresses-and-call-routing.md) .
  
Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Sie können Notfall Speicherorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.
  
## <a name="add-a-place-to-an-emergency-location"></a>Hinzufügen eines Orts zu einem Notfall Standort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.
2. Klicken Sie in der Liste auf den Namen des Standorts, für den Sie einen Ort hinzufügen möchten.
3. Klicken Sie auf der Registerkarte **Orte** auf **Hinzufügen**.
4. Geben Sie einen Ortsnamen ein, und klicken Sie dann auf über **nehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Ändern eines Orts für einen Notfall Standort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.
2. Klicken Sie in der Liste auf den Namen des Standorts, für den Sie einen Ort ändern möchten.
3. Wählen Sie auf der Registerkarte **Orte** den Ort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.
4. Aktualisieren Sie die Ortsinformationen, und klicken Sie dann auf über **nehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Entfernen eines Orts aus einem Notfall Standort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.
2. Klicken Sie in der Liste auf den Namen des Standorts, für den Sie einen Ort entfernen möchten.
3. Wählen Sie auf der Registerkarte **Orte** den Ort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Verwandte Themen

- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
