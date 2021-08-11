---
title: Deaktivieren von gebührenfreien Telefonnummern für Skype for Business Online-Benutzer
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Nummern für Ihre Besprechungen verwenden können.
ms.openlocfilehash: aabc72f5e413b8f760981b8fac364afc836be5ce058d5999e2c19f96109141b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310274"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Deaktivieren von gebührenfreien Telefonnummern für Skype for Business Online-Benutzer

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> Informationen zum Deaktivieren von gebührenfreien Nummern für Teams Benutzer finden Sie unter Deaktivieren von gebührenfreien Telefonnummern [für Teams Benutzer.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)

Wenn Ihre Microsoft Audio Conferencing Bridge gebührenfreie Telefonnummern verwendet, können Sie deren Nutzung in Besprechungen bestimmter Organisatoren zulassen oder verhindern.  

Standardmäßig sind alle Benutzer in Ihrer Organisation für die Verwendung von gebührenfreien Nummern aktiviert, was bedeutet, dass diese Nummern, sofern verfügbar, von den Teilnehmern für die Teilnahme an ihren Besprechungen verwendet werden können. Wenn dies für einige Benutzer in Ihrer Organisation nicht das gewünschte Verhalten ist, können Sie mithilfe eines Aktivierungssteuerelements für gebührenfreie Nummern verhindern, dass bestimmte Benutzer diese Nummern in Ihren Besprechungen verwenden. 

Wenn gebührenfreie Telefonnummern für einen bestimmten Organisator deaktiviert sind: 
 - Eine gebührenfreie Nummer wird in den Besprechungs-Einladungen nicht mehr enthalten sein. 
 - Gebührenfreie Nummern werden nicht mehr auf der Seite "Lokale Rufnummer suchen" aufgeführt, auf die in den Besprechungs-Einladungen verwiesen wird. 
 - Teilnehmer können nicht an der Besprechung des angegebenen Organisators teilnehmen, wenn sie eine gebührenfreie Nummer der Organisation wählen. 
 - Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Nummer wird entfernt.  

    > [!IMPORTANT]
    > Dadurch werden alle E-Mail-Einladungen des Organisators an alle Teilnehmer dieser Besprechungen erneut gesendet. 

 - Teilnehmer können weiterhin über gebührenpflichtige Telefonnummern an Besprechungen des Organisators teilnehmen. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer 

Im **Microsoft Teams Admin Center:**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **neben Audiokonferenz** auf **Bearbeiten**.

3. Legen **Sie gebührenfreie Nummern in Besprechungsanfragen dieses** Benutzers ein auf **Aus.** 

4. Klicken Sie **auf Speichern.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Verwendung von PowerShell**  

Sie können den Parameter AllowBenachrichtigungFreeDialIn des cmdlets Set-CsOnlineDialInConferencingUser verwenden, um dieses Steuerelement zu aktivieren oder zu deaktivieren. Zum Beispiel: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowUhrFreeDialIn $false
