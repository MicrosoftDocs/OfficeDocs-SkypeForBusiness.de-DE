---
title: Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie steuern können, wie Organisatoren gebührenfreie Nummern für ihre Audiokonferenzbrücke-Besprechungen verwenden können.
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096345"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer

Wenn Ihre Organisation gebührenfreie Nummern in ihrer Microsoft Audio Conferencing Bridge hat, können Sie deren Verwendung in Besprechungen bestimmter Organisatoren zulassen oder verhindern.  

Standardmäßig sind alle Benutzer in Ihrer Organisation für die Verwendung gebührenfreier Nummern aktiviert, d. h., dass diese Nummern, sofern verfügbar, von Teilnehmern verwendet werden können, um an ihren Besprechungen teilzunehmen. Wenn dies für einige Benutzer in Ihrer Organisation nicht das gewünschte Verhalten ist, können Sie bestimmte Benutzer davon einschränken, diese Nummern in ihren Besprechungen über ein gebührenfreies Nummern-Enablement-Steuerelement zu verwenden. 

Wenn gebührenfreie Nummern für einen bestimmten Organisator deaktiviert sind: 
 - Eine gebührenfreie Nummer wird nicht mehr in die Besprechungsbesprechungen einbezogen. 
 - Gebührenfreie Nummern werden nicht mehr auf der Seite "Lokale Nummer suchen" aufgeführt, auf die in den Besprechungsbesprechungen verwiesen wird. 
 - Teilnehmer können nicht an der Besprechung des angegebenen Organisators teilnehmen, wenn sie eine gebührenfreie Nummer der Organisation wählen. 
 - Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Nummer wird entfernt.  

    > [!IMPORTANT]
    > Dadurch werden alle E-Mail-Einladungen des Organisators an alle Teilnehmer dieser Besprechungen erneut gesendet. 

 - Teilnehmer können weiterhin an Besprechungen des Organisators mithilfe von Gebührennummern teilnehmen. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer 

Im **Microsoft Teams Admin Center:**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **neben Audiokonferenzen** auf **Bearbeiten.**

3. Legen **Sie gebührenfreie Nummern in Besprechungsanfragen** dieses Benutzers auf **Aus ein.** 

4. Klicken Sie **auf Speichern.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Verwendung von PowerShell**  

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)