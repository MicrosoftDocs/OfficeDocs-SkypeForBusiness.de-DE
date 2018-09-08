---
title: Gebührenfreie Nummern für bestimmte Teams Benutzer deaktivieren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Nummern für ihre Besprechungen verwenden können.
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887380"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Gebührenfreie Nummern für bestimmte Teams Benutzer deaktivieren

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

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer 

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.

4. Deaktivieren Sie **gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer gehören**. 

5. Klicken Sie auf **zu speichern.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Verwenden von PowerShell**  

Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
