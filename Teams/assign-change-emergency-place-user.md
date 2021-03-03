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
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809525"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern des Orts für einen Notfallstandort für einen Benutzer

Jeder aktiven Telefonnummer muss ein Notfallstandort zugeordnet sein, wenn Sie die Telefonnummer einem Benutzer zuweisen. (Sie ordnen die Adresse zu, wenn Sie in Office 365 eine Telefonnummer erhalten oder eine Telefonnummer übertragen.) Wenn Sie die Nummer einem Notfallstandort zuordnen, können Sie auch einen Ort hinzufügen, um einen genaueren Standort innerhalb eines physischen Standorts anzuordnen. Ein Ort kann der Boden, der Gebäudeflügel oder die Büronummer sein, unter der sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von Orten für einen bestimmten Notfallstandort haben, und Sie können den Ort ändern, wenn der Benutzer zu einem anderen Büro oder Gebäude wechselt. Beispiel: Der Benutzer wechselt von Stockwerk 34 in 35.
  
Informationen zum Erhalten von Anrufplänen und deren Kosten finden Sie unter [Teams-Add-On-Lizenzierung.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
Sie können den Ort für einen Notfallstandort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Voice**  >  **phone numbers".**

2. Klicken Sie **auf der Seite "Telefonnummern"** auf die Registerkarte "Zahlen", wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **"Bearbeiten".** 

3. Gehen Sie **im Bereich** **"Bearbeiten"** unter "Notfallstandort" wie folgt vor:

    - Um einen Ort zuzuordnen, suchen Sie nach dem Speicherort oder Ort, und wählen Sie dann den Ort in den Suchergebnissen aus.

    - Wenn Sie den Dem Benutzer bereits zugewiesenen Ort ändern möchten, klicken Sie auf **"X",** um den vorhandenen Ort zu entfernen, suchen Sie nach dem Ort, den Sie zuweisen möchten, und wählen Sie ihn aus.

4. Je nachdem, ob Sie eine E-Mail mit den Telefonnummerninformationen an den Benutzer senden möchten, deaktivieren oder aktivieren Sie den E-Mail-Benutzer mit **Telefonnummerninformationen.** Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)
    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer](assign-change-emergency-location-user.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
