---
title: Hinzufügen, Ändern, Entfernen von Notfallstandorten
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
description: 'Erfahren Sie, wie Sie einen Notfallstandort für Ihre Organisation im Microsoft Teams Admin Center hinzufügen, ändern oder entfernen. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b918cbcbebf8edb2cd54d08e0e4a3177867fa623
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121523"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation

Ein Notfallstandort muss mit einer Telefonnummer verknüpft sein, kann jedoch je nach Land und Region variieren. In den USA müssen Sie beispielsweise einen Notfallstandort zuordnen, wenn Sie dem Benutzer die Telefonnummer zuweisen. In Großbritannien müssen Sie der Telefonnummer einen Notfallstandort zuordnen, wenn Sie die Telefonnummern von Microsoft 365 oder Office 365 erhalten oder Telefonnummern von Ihrem aktuellen Dienstanbieter übertragen.

Unabhängig davon, in welchem Land oder in welcher Region Sie sich befinden, können Sie einem Notfallstandort einen Ort oder Orte hinzufügen und einen Notfallstandort entfernen. Abhängig von der Anzahl der physischen Standorte in Ihrer Organisation können Sie Orte für Gebäude, Stockwerke und Büros erstellen. Weitere Informationen [finden Sie unter Verwalten von Notrufen.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel sie kosten, finden Sie unter [Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.
  
## <a name="add-an-emergency-location"></a>Hinzufügen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für den Speicherort ein.
4. Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.

   > [!NOTE]
   > In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu verstehen, dass zum erfolgreichen Aktivieren einer Telefonnummer in Microsoft 365 oder Office 365 die am Notfallstandort eingerichtete Adresse, die zum Erwerben der Nummer verwendet wird, der Vorwahl der Telefonnummer entsprechen muss.

5. Wenn die Adresse nicht gefunden wurde und Sie die Adresse manuell bearbeiten möchten, aktivieren Sie **Die Adresse manuell bearbeiten.**
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Ändern eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf  >  **Notfalladressen für Standorte.**
2. Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können die Adressinformationen für einen Ort nur ändern, wenn die Adresse nicht überprüft wurde. Wenn die Adresse bereits überprüft wurde und Sie die Adresse ändern müssen, löschen Sie den Speicherort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Entfernen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf  >  **Notfalladressen für Standorte.**
2. Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)