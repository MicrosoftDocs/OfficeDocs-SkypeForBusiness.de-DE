---
title: Deaktivieren von gebührenfreie Nummern für bestimmte Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Nummern für ihre Besprechungen verwenden können.
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreie Nummern für bestimmte Benutzer

Wenn Ihre Organisation gebührenfreie Nummern in der Microsoft Audio Conferencing Bridge verfügt, können Sie erlauben oder verhindern ihrer Verwendung in Besprechungen von bestimmten Organisatoren durch.  

Standardmäßig werden alle Benutzer in Ihrer Organisation aktiviert, für die Verwendung von gebührenfreier Nummern, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern verwendet werden können an einer Besprechung teilnehmen. Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer einschränken, verwenden Sie diese Nummern in ihre Besprechungen über eine gebührenfreie Nummern Aktivierung-Steuerelement. 

Wenn für einen bestimmten Organizer gebührenfreie Nummern deaktiviert sind: 
 - Eine gebührenfreie Nummer wird nicht mehr in seinem enthalten sein oder ihrer Besprechung eingeladen. 
 - Gebührenfreie Nummern werden nicht mehr auf der Seite mit "Hier finden Sie eine lokale Nummer", die in seinem verwiesen wird aufgelistet oder ihrer Besprechung eingeladen. 
 - Teilnehmer möglich nicht, der des angegebenen Organisators die Besprechung teilnehmen, wenn sie eine beliebige gebührenfreie Telefonnummer des Unternehmens wählen. 
 - Der Organisator alle Besprechungen werden automatisch neu geplant, und die gebührenfreie Telefonnummer daraus entfernt werden.  

    > [!IMPORTANT]
    > Dies erneut alle des Dialogfelds Organisieren der e-Mail-Einladungen an alle Teilnehmer der Besprechungen senden. 

 - Teilnehmer können weiterhin teilnehmen an Besprechungen des Dialogfelds Organisieren von gebührenfreie Nummern. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreie Nummern für bestimmte Benutzer 

![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie auf das Menü neben **Konferenz Brücken**, und klicken Sie dann auf **Bearbeiten** , in der Dropdown-Liste.

4. Deaktivieren Sie im Bereich **Konferenz Bridge Anbieter** **Zulassen gebührenfreie Nummern in die Konferenzbrücke Ihrer Organisation zur Teilnahme an Besprechungen dieses Benutzers verwenden**aus. 

5. Klicken Sie auf **anwenden.** 

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

1. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer. 

2. In the Action pane, click **Edit**. 

3. Deaktivieren **von gebührenfreie Nummern zum Teilnehmen an Besprechungen dieses Benutzers zulassen**. 
 
4. Klicken Sie auf **Speichern**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Verwenden von PowerShell**  

Den AllowTollFreeDialIn-Parameter des Set-CsOnlineDialInConferencingUser-Cmdlets können zum Aktivieren oder Deaktivieren dieses Steuerelement. Beispiel: 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
