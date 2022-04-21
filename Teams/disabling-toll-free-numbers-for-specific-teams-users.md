---
title: Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie steuern können, wie Organisatoren gebührenfreie Nummern für ihre Besprechungen der Audiokonferenzbrücke verwenden können.
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016627"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer

Wenn Ihre Organisation gebührenfreie Nummern in der Microsoft-Audiokonferenzbrücke hat, können Sie deren Nutzung in den Besprechungen bestimmter Organisatoren zulassen oder verhindern.  

Standardmäßig sind alle Benutzer in Ihrer Organisation für die Verwendung gebührenfreier Nummern aktiviert. Dies bedeutet, dass diese Nummern, sofern verfügbar, von Teilnehmern für die Teilnahme an ihren Besprechungen verwendet werden können. Wenn dies für einige Benutzer in Ihrer Organisation nicht das gewünschte Verhalten ist, können Sie bestimmte Benutzer daran hindern, diese Nummern in ihren Besprechungen über ein gebührenfreies Nummernaktivierungssteuerelement zu verwenden.

Wenn gebührenfreie Telefonnummern für einen bestimmten Organisator deaktiviert sind:

- Eine gebührenfreie Nummer ist in den Besprechungseinladungen nicht mehr enthalten.
- Gebührenfreie Telefonnummern werden nicht mehr auf der Seite "Lokale Nummer suchen" aufgeführt, auf die in seinen Besprechungseinladungen verwiesen wird.
- Teilnehmer können nicht an der Besprechung des angegebenen Organisators teilnehmen, wenn sie eine gebührenfreie Nummer der Organisation wählen.
- Teilnehmer können weiterhin mit gebührenpflichtigen Nummern an Besprechungen des Organisators teilnehmen.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer

Sie können gebührenfreie Nummern für bestimmte Benutzer deaktivieren, indem Sie die Einstellung für *AllowTollFreeDialIn* innerhalb der diesen Benutzern *zugewiesenen TeamsAudioConferencingPolicy* in **"Aus**" ändern. Nachdem sie alle neuen Besprechungen deaktiviert haben, die von diesen Benutzern erstellt wurden, sind keine gebührenfreien Nummern enthalten. [Die Richtlinieneinstellungen für Audiokonferenzen für gebührenpflichtige und gebührenfreie Telefonnummern](audio-conferencing-toll-free-numbers-policy.md) enthalten weitere Informationen.

> [!IMPORTANT]
> Alte und zuvor geplante Besprechungsserien zeigen möglicherweise weiterhin gebührenfreie Nummern an, und die Teilnehmer können nicht über eine gebührenfreie Nummer an solchen Besprechungen teilnehmen. Sie können alle alten und wiederkehrenden Besprechungen für diese Benutzer neu planen und gebührenfreie Nummern mit mms entfernen.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
