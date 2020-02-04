---
title: Deaktivieren von gebührenfreien Nummern für bestimmte Skype for Business Online-Benutzer
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
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695680"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Deaktivieren von gebührenfreien Nummern für bestimmte Skype for Business Online-Benutzer
 
> [!Note]
> Informationen zum Deaktivieren von Tool freien Nummern für Team Benutzer finden Sie unter [Deaktivieren von gebührenfreien Nummern für bestimmte Teams-Benutzer](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Wenn in Ihrer Organisation gebührenfreie Nummern in der Microsoft-Audiokonferenz-Brücke zur Verfügung stehen, können Sie deren Verwendung in den Besprechungen bestimmter Organisatoren zulassen oder verhindern.  

Standardmäßig sind alle Benutzer in Ihrer Organisation für die Verwendung von gebührenfreien Nummern aktiviert, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern zur Teilnahme an Besprechungen verwendet werden können. Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer davon abhalten, diese Nummern in ihren Besprechungen über eine gebührenfreie Nummer-Aktivierung-Steuerung zu verwenden. 

Wenn gebührenfreie Nummern für einen bestimmten Organisator deaktiviert sind: 
 - Eine gebührenfreie Nummer wird nicht mehr in Ihre Besprechungseinladungen aufgenommen. 
 - Gebührenfreie Nummern werden nicht mehr auf der Seite "Ortsnummer suchen" aufgelistet, auf die in den Einladungen zu ihren Besprechungen verwiesen wird. 
 - Teilnehmer können an der Besprechung des angegebenen Organisators nicht teilnehmen, wenn Sie eine gebührenfreie Nummer der Organisation wählen. 
 - Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Nummer wird von Ihnen entfernt.  

    > [!IMPORTANT]
    > Dadurch werden alle e-Mail-Einladungen des Organisators an alle Teilnehmer dieser Besprechungen erneut gesendet. 

 - Teilnehmer können mit gebührenpflichtigen Nummern weiterhin an Besprechungen des Organisators teilnehmen. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer 

Im **Microsoft Teams Admin Center**:

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.

3. Legen Sie **gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer** auf **aus**. 

4. Klicken Sie auf **speichern.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Verwenden von PowerShell**  

Sie können den AllowTollFreeDialIn-Parameter des Cmdlets "Satz-csonlinedialinconferencinguser zeigt" verwenden, um dieses Steuerelement zu aktivieren oder zu deaktivieren. Beispiel: 

- Satz-csonlinedialinconferencinguser zeigt user@contoso.com – AllowTollFreeDialIn $false
