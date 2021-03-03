---
title: Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie einen Notfallstandort für Benutzer in Ihrer Organisation zuweisen oder ändern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809565"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer

Wenn Sie Anrufpläne einrichten, müssen Sie jeder Telefonnummer oder jedem Benutzer einen Notfallstandort zuweisen. In europäischen Ländern wird der Notfallstandort der Telefonnummer zugeordnet, wenn Sie diese von Microsoft 365 oder Office 365 erhalten oder wenn Sie eine Telefonnummer zu Microsoft 365 oder Office 365 übertragen. In den USA ist der Notfallstandort der Telefonnummer zugeordnet, wenn er dem Benutzer zugewiesen wird. Die Notfalladresse kann geändert werden, wenn der Benutzer, dem sie zugewiesen ist, an einen neuen Standort wechselt. Weitere Informationen zu Notfalladressen und -standorten finden Sie unter "Was [sind Notfallstandorte, Standorte und Anrufrouting?".](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)
  
Informationen zum Erhalten von Anrufplänen und deren Kosten finden Sie unter [Teams-Add-On-Lizenzierung.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
Sie können einen Notfallstandort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Voice**  >  **phone numbers".**

2. Klicken Sie **auf der Seite "Telefonnummern"** auf die Registerkarte "Zahlen", wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **"Bearbeiten".** 

3. Gehen Sie **im Bereich** **"Bearbeiten"** unter "Notfallstandort" wie folgt vor:

   - Um einen Notfallstandort zuzuordnen, suchen Sie einen Notfallstandort, und wählen Sie diesen aus.

   - Wenn Sie den dem Benutzer bereits zugewiesenen Notfallstandort ändern möchten, klicken Sie auf **"X",** um den vorhandenen Standort zu entfernen. Suchen Sie dann den Standort, den Sie zuweisen möchten, und wählen Sie ihn aus.

4. Je nachdem, ob Sie eine E-Mail mit den Telefonnummerninformationen an den Benutzer senden möchten, deaktivieren oder aktivieren Sie den E-Mail-Benutzer mit **Telefonnummerninformationen.** Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer](assign-change-emergency-place-user.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
