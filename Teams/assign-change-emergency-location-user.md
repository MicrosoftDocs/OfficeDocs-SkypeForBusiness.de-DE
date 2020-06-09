---
title: Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie einen Notfall Standort für Benutzer in Ihrer Organisation zuweisen oder ändern können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 450fe848052af1e331964da3d7b695daf0f1567a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610994"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer

Wenn Sie Anrufpläne einrichten, müssen Sie jeder Telefonnummer oder einem Nutzer einen Notfall Standort zuweisen. In europäischen Ländern ist der Notfall Standort mit der Telefonnummer verbunden, wenn Sie ihn von Microsoft 365 oder Office 365 erhalten oder wenn Sie eine Telefonnummer an Microsoft 365 oder Office 365 übertragen. In den Vereinigten Staaten ist der Notfall Standort mit der Telefonnummer verbunden, wenn Sie dem Benutzer zugewiesen ist. Die Notfalladresse kann geändert werden, wenn der Benutzer, dem Sie zugewiesen wurde, an einen neuen Speicherort wechselt. Weitere Informationen zu Notfalladressen und-Standorten finden Sie unter [Was sind Notfall Standorte, Orte und Anrufweiterleitung?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).
  
Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
Sie können einen Notfall Standort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **VoIP**-Rufnummern  >  **Phone numbers**.

2. Klicken Sie auf der Seite **Telefonnummern** auf die Registerkarte **Zahlen** , wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**.

3. Führen Sie im **Bearbeitungs** Bereich unter **Notfall Speicherort**eine der folgenden Aktionen aus:

   - Wenn Sie einen Notfall Standort zuweisen möchten, suchen Sie nach einem Notfall Standort, und wählen Sie ihn aus.

   - Wenn Sie den Notfall Standort ändern möchten, der dem Benutzer bereits zugewiesen ist, klicken Sie auf **X** , um den vorhandenen Speicherort zu entfernen, und suchen Sie dann nach dem Speicherort, den Sie zuweisen möchten, und wählen Sie ihn aus.

4. Je nachdem, ob Sie dem Benutzer eine e-Mail mit den Informationen zur Telefonnummer senden möchten, deaktivieren oder aktivieren Sie **e-Mail-Nutzer mit Telefonnummerninformationen**. Standardmäßig ist dies aktiviert.

5. Klicken Sie auf **Anwenden**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation](add-change-remove-emergency-place-organization.md)
- [Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer](assign-change-emergency-place-user.md)
- [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
