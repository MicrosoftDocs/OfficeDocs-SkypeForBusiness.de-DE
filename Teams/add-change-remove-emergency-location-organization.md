---
title: Hinzufügen, Ändern und Entfernen von Notfallstandorten
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
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799945"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation

Einem Notfallstandort muss eine Telefonnummer zugeordnet sein, aber wann dies geschieht, kann je nach Land und Region variieren. In den USA müssen Sie beispielsweise einen Notfallstandort zuordnen, wenn Sie dem Benutzer die Telefonnummer zuweisen. Im Vereinigten Königreich müssen Sie der Telefonnummer einen Notfallstandort zuordnen, wenn Sie die Telefonnummern von Microsoft 365 oder Office 365 erhalten oder Telefonnummern von Ihrem aktuellen Dienstanbieter übertragen.

Unabhängig davon, in welchem Land bzw. in welcher Region Sie sich befinden, können Sie einen oder mehrere Orte zu einem Notfallstandort hinzufügen und einen Notfallstandort entfernen. Je nach Anzahl physischer Standorte in Ihrer Organisation können Sie Orte für Gebäude, Stockwerke und Büros erstellen. Weitere Informationen [finden Sie unter "Verwalten von Notrufen".](what-are-emergency-locations-addresses-and-call-routing.md)
  
Informationen zum Erhalten eines Anrufplans und deren Kosten finden Sie unter [Teams-Add-On-Lizenzierung.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.
  
## <a name="add-an-emergency-location"></a>Hinzufügen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf Notfalladressen  >  **für Standorte.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für den Speicherort ein.
4. Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.

   > [!NOTE]
   > In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu wissen, dass die adresse, die für den Erwerb der Nummer verwendet wird, der Vorwahl der Telefonnummer entsprechen muss, um eine Telefonnummer in Microsoft 365 oder Office 365 erfolgreich zu aktivieren.

5. Wenn die Adresse nicht gefunden wurde und Sie die Adresse manuell bearbeiten möchten, aktivieren Sie **"Adresse manuell bearbeiten".**
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter ["New-CsOnlineLisCi selbstAddress".](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Ändern eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf Notfalladressen  >  **für Standorte.**
2. Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **"Bearbeiten".**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können die Adressinformationen für einen Ort nur ändern, wenn die Adresse nicht überprüft wurde. Wenn die Adresse bereits überprüft wurde und Sie die Adresse ändern müssen, löschen Sie den Ort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe ["Set-CsOnlineLisCi selbstAddress".](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Entfernen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf Notfalladressen  >  **für Standorte.**
2. Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **"Löschen".**

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe ["Remove-CsOnlineLisCi selbstAddress".](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
