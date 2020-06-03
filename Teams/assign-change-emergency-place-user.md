---
title: Zuweisen, Ändern von Orten für Notfall Standorte für Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie den Ort für einen Notfall Standort für Benutzer in Ihrer Organisation zuweisen oder ändern können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539512"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern des Orts eines Notfall Standorts für einen Benutzer

Jede aktive Telefonnummer muss über einen zugehörigen Notfall Standort verfügen, wenn Sie die Telefonnummer einem Benutzer zuweisen. (Sie ordnen die Adresse zu, wenn Sie in Office 365 eine Telefonnummer erhalten oder wenn Sie eine Telefonnummer übertragen.) Wenn Sie die Nummer mit einem Notfall Standort verknüpfen, können Sie auch einen Ort hinzufügen, um eine genauere Position innerhalb eines physikalischen Standorts bereitzustellen. Bei einem Ort kann es sich um den Boden, den Gebäudetrakt oder die Office-Nummer handeln, in der sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von Orten für einen bestimmten Notfall Standort haben, und Sie können den Ort ändern, wenn der Benutzer zu einer anderen Niederlassung oder einem anderen Gebäude wechselt. Wenn der Benutzer beispielsweise von Floor 34 auf Floor 35 umzieht.
  
Informationen dazu, wie Sie Anrufpläne erhalten und wie viel Sie Kosten, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
Sie können den Ort für einen Notfall Standort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **VoIP**-Rufnummern  >  **Phone numbers**.

2. Klicken Sie auf der Seite **Telefonnummern** auf die Registerkarte **Zahlen** , wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**.

3. Führen Sie im **Bearbeitungs** Bereich unter **Notfall Speicherort**eine der folgenden Aktionen aus:

    - Wenn Sie einen Ort zuweisen möchten, suchen Sie nach dem Ort oder Ort, und wählen Sie dann die Stelle in den Suchergebnissen aus.

    - Wenn Sie die Position ändern möchten, die dem Benutzer bereits zugewiesen ist, klicken Sie auf **X** , um die vorhandene Position zu entfernen, suchen Sie nach dem Ort, den Sie zuweisen möchten, und wählen Sie ihn aus.

4. Je nachdem, ob Sie dem Benutzer eine e-Mail mit den Informationen zur Telefonnummer senden möchten, deaktivieren oder aktivieren Sie **e-Mail-Nutzer mit Telefonnummerninformationen**. Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer](assign-change-emergency-location-user.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
