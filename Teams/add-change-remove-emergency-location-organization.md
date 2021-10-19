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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 'Informationen zum Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation finden Sie im Microsoft Teams Admin Center. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6523a3a3f19b2c3145bb6e89f47029c4d982ab1
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465791"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation

**Unabhängig von der von Ihnen [verwendeten PSTN-Konnektivitätsoption](pstn-connectivity.md) können Microsoft-Anrufpläne, Operator Verbinden- oder Direct Routing-Notfallstandorte einer Telefonnummer zugeordnet werden. Je nach Ihrer PSTN-Konnektivitätsoption können die Standortanforderungen jedoch variieren.**

**Bei Anrufplänen muss ein** Notfallstandort einer Telefonnummer zugeordnet sein, aber in diesem Fall kann dies je nach Land oder Region variieren. In den USA müssen Sie z. B. einen Notfallstandort zuordnen, wenn Sie dem Benutzer die Telefonnummer zuweisen. Im Vereinigten Königreich müssen Sie der Telefonnummer einen Notfallstandort zuordnen, wenn Sie die Telefonnummern von Microsoft 365 erhalten oder Telefonnummern von Ihrem aktuellen Dienstanbieter übertragen.

**Für Operatoren Verbinden...**

**Für direktes Routing...**

**TRIFFT DIES AUF ALLE 3 ZU?**
Unabhängig davon, in welchem Land bzw. in welcher Region Sie sich befinden, können Sie einem Notfallstandort einen oder mehrere Orte hinzufügen und einen Notfallstandort entfernen. Je nach Anzahl physischer Standorte in Ihrer Organisation können Sie Orte für Gebäude, Stockwerke und Büros erstellen. Weitere Informationen [finden Sie unter Verwalten von Notrufen.](what-are-emergency-locations-addresses-and-call-routing.md)

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.

**Um einen Notfallstandort zuzuordnen, müssen sich Benutzer, Telefonnummern und Notfallstandorte im selben Land befinden.**  Weitere Informationen finden Sie unter [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer.](assign-change-emergency-location-user.md)
  
## <a name="add-an-emergency-location"></a>Hinzufügen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für den Ort ein.
4. Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.

   > [!NOTE]
   > In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu wissen, dass zum erfolgreichen Aktivieren einer Telefonnummer in Microsoft 365 die Adresse, die für den Notfallstandort zum Erwerben der Nummer verwendet wird, mit der Orts vorwahl der Telefonnummer übereinstimmen muss.

5. Wenn die Adresse nicht gefunden wird und Sie die Adresse manuell bearbeiten möchten, aktivieren Sie Adresse **manuell bearbeiten.**
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsOnlineLisCivicAddress.](/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Ändern eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte.**
2. Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können die Adressinformationen für einen Standort nur ändern, wenn die Adresse nicht überprüft wurde. Wenn die Adresse bereits überprüft wurde und Sie sie ändern müssen, löschen Sie den Standort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineLisCivicAddress.](/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Entfernen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte.**
2. Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Remove-CsOnlineLisCivicAddress.](/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)