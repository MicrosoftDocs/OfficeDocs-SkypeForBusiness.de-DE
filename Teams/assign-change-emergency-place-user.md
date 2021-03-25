---
title: Zuweisen, Ändern von Orten für Notfallstandorte für Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie den Ort für einen Notfallstandort für Benutzer in Ihrer Organisation zuweisen oder ändern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120827"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern des Orts für einen Notfallstandort für einen Benutzer

Jede aktive Telefonnummer muss über einen zugeordneten Notfallstandort verfügen, wenn Sie die Telefonnummer einem Benutzer zuweisen. (Sie ordnen die Adresse zu, wenn Sie eine Telefonnummer in Office 365 erhalten oder wenn Sie eine Telefonnummer übertragen.) Wenn Sie die Nummer einem Notfallstandort zuordnen, können Sie auch einen Ort hinzufügen, an dem Sie einen genaueren Ort an einem physischen Ort bereitstellen können. Ein Ort kann der Boden, der Gebäudetrakt oder die Büronummer sein, in der sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von Orten für einen bestimmten Notfallstandort haben, und Sie können den Ort ändern, wenn der Benutzer zu einem anderen Büro oder Gebäude wechselt. Wenn der Benutzer z. B. von Stockwerk 34 in Stockwerk 35 wechselt.
  
Informationen dazu, wie Sie Anrufpläne erhalten und wie viel sie kosten, finden Sie unter [Teams-Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
Sie können den Ort für einen Notfallstandort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **Voice**  >  **phone numbers**.

2. Klicken Sie **auf der** Seite Telefonnummern auf **die** Registerkarte Zahlen, wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten.**

3. Gehen Sie **im Bereich** Bearbeiten unter **Notfallstandort** eine der folgenden Schritte aus:

    - Um einen Ort zuzuordnen, suchen Sie nach dem Speicherort oder Ort, und wählen Sie dann den Ort in den Suchergebnissen aus.

    - Wenn Sie den Ort ändern möchten, der dem Benutzer bereits zugewiesen ist, klicken Sie auf **X,** um den vorhandenen Speicherort und ort zu entfernen, suchen Sie nach dem Ort, und wählen Sie dann den Ort aus, den Sie zuweisen möchten.

4. Je nachdem, ob Sie dem Benutzer eine E-Mail mit seinen Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie **Dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden**. Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer](assign-change-emergency-location-user.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)