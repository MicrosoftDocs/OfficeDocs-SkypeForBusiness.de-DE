---
title: Notfallstandorte hinzufügen, ändern, entfernen
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
description: Erfahren Sie, wie Sie einen Notfallstandort für Ihre Organisation hinzufügen, ändern oder entfernen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bcbe811ecdb7ac9377e4798a2cdcb7334188aa1e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267600"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation

Unabhängig von der Option für die [PSTN-Konnektivität](pstn-connectivity.md) können&mdash;Sie Microsoft-Anrufpläne, Telefonieanbieter oder Direct Routing-Notfallstandorte&mdash;einer Telefonnummer zuordnen.

Je nach Ihrer PSTN-Konnektivitätsoption kann die Verwaltung von Notfallstandorten und Standortanforderungen jedoch variieren. Weitere Informationen finden [Sie unter Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md).

In diesem Artikel wird beschrieben, wie Sie einen Notfallstandort für Ihre Organisation hinzufügen, ändern oder entfernen. 

Dieser Artikel bezieht sich auf Microsoft-Anrufpläne, Telefonieanbieter und Direct Routing.

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.

Um einen Notfallstandort zuzuweisen, müssen sich Benutzer, Telefonnummern und Notfallstandorte alle im selben Land befinden. Weitere Informationen finden Sie unter [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Hinzufügen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Notfalladressen** für **Standorte** > .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für den Speicherort ein.
4. Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.

   > [!NOTE]
   > In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu verstehen, dass die adresse, die am Notfallstandort eingerichtet ist, um eine Telefonnummer in Microsoft 365 erfolgreich zu aktivieren, mit der Ortsvorwahl der Telefonnummer übereinstimmen muss.

5. Wenn die Adresse nicht gefunden wird und Sie die Adresse manuell bearbeiten möchten, aktivieren **Sie "Adresse manuell bearbeiten**".
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Ändern eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Notfalladressen** für **Standorte** > .
2. Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **"Bearbeiten"**.
3. Nehmen Sie die gewünschten Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können die Adressinformationen für einen Speicherort nur ändern, wenn die Adresse nicht überprüft wird. Wenn die Adresse bereits überprüft wurde und Sie die Adresse ändern müssen, löschen Sie den Speicherort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Entfernen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Notfalladressen** für **Standorte** > .
2. Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **"Löschen"**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)