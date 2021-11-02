---
title: Hinzufügen, Ändern und Entfernen von Notfallstandorten
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
description: 'Erfahren Sie, wie Sie einen Notfallstandort für Ihre Organisation hinzufügen, ändern oder entfernen. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634854"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation

Unabhängig von [](pstn-connectivity.md) der PstN-Konnektivitätsoption, die Sie für Microsoft-Anrufpläne, Operator Verbinden oder Direct Routing-Notfallstandorte auswählen, kann eine Telefonnummer &mdash; &mdash; zugeordnet werden.

Je nach Ihrer PSTN-Konnektivitätsoption kann die Art und Weise, wie Sie Notfallstandorte und Standortanforderungen verwalten, jedoch variieren. Weitere Informationen finden Sie unter [Verwalten von Notrufen.](what-are-emergency-locations-addresses-and-call-routing.md)

In diesem Artikel wird beschrieben, wie Sie einen Notfallstandort für Ihre Organisation hinzufügen, ändern oder entfernen. 

Dieser Artikel bezieht sich auf Microsoft-Anrufpläne, Operatoren Verbinden direktes Routing.

Sie verwalten Notfallstandorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell.

Um einen Notfallstandort zuzuordnen, müssen sich Benutzer, Telefonnummern und Notfallstandorte im selben Land befinden. Weitere Informationen finden Sie unter [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer.](assign-change-emergency-location-user.md)
  
## <a name="add-an-emergency-location"></a>Hinzufügen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für den Ort ein.
4. Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.

   > [!NOTE]
   > In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu wissen, dass zum erfolgreichen Aktivieren einer Telefonnummer in Microsoft 365 die Für den Notfallstandort eingerichtete Adresse, mit der die Nummer beschafft wird, mit der Vorwahl der Telefonnummer übereinstimmen muss.

5. Wenn die Adresse nicht gefunden wird und Sie die Adresse manuell bearbeiten möchten, aktivieren Sie Adresse **manuell bearbeiten.**
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsOnlineLisCivicAddress.](/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Ändern eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte**.
2. Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können die Adressinformationen für einen Standort nur ändern, wenn die Adresse nicht überprüft wurde. Wenn die Adresse bereits überprüft wurde und Sie sie ändern müssen, löschen Sie den Standort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineLisCivicAddress.](/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Entfernen eines Notfallstandorts

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf  >  **Notfalladressen für Standorte**.
2. Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Remove-CsOnlineLisCivicAddress.](/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)