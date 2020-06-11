---
title: Hinzufügen, ändern und Entfernen von Notfall Standorten
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
description: 'Hier erfahren Sie, wie Sie im Microsoft Teams Admin Center einen Notfall Standort für Ihre Organisation hinzufügen, ändern oder entfernen. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5758d79325cd83579e2a650db47c9913a0cda26b
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690841"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation

Ein Notfall Standort muss einer Telefonnummer zugeordnet sein, aber wenn dies der Fall ist, kann dies zwischen Ländern und Regionen variieren. In den Vereinigten Staaten müssen Sie beispielsweise einen Notfall Standort zuordnen, wenn Sie dem Benutzer die Telefonnummer zuweisen. Im Vereinigten Königreich müssen Sie der Telefonnummer einen Notfall Standort zuordnen, wenn Sie die Telefonnummern von Microsoft 365 oder Office 365 erhalten oder Telefonnummern von Ihrem aktuellen Dienstanbieter übertragen.

Unabhängig davon, in welchem Land oder in welcher Region Sie sich befinden, können Sie einen Ort oder eine Stelle zu einem Notfall Standort hinzufügen und einen Notfall Standort entfernen. Je nach Anzahl der physikalischen Standorte in Ihrer Organisation können Sie Orte für Gebäude, Etagen und Büros erstellen. Siehe [Notfall Anruf verwalten](what-are-emergency-locations-addresses-and-call-routing.md).
  
Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Sie können Notfall Speicherorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.
  
## <a name="add-an-emergency-location"></a>Hinzufügen eines Notfall Standorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für den Ort ein.
4. Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.

   > [!NOTE]
   > In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu verstehen, dass für eine erfolgreiche Aktivierung einer Telefonnummer in Microsoft 365 oder Office 365 die Adresse des Notfall Standorts, die zum Abrufen der Nummer verwendet wird, mit der Ortsvorwahl der Telefonnummer übereinstimmen muss.

5. Wenn die Adresse nicht gefunden wird und Sie die Adresse manuell bearbeiten möchten, aktivieren Sie **die Option Adresse manuell bearbeiten**.
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Ändern eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.
2. Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.
3. Nehmen Sie die gewünschten Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können die Adressinformationen für einen Speicherort nur ändern, wenn die Adresse nicht überprüft wurde. Wenn die Adresse bereits überprüft wurde und Sie die Adresse ändern müssen, löschen Sie den Speicherort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Entfernen eines Notfall Standorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.
2. Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
