---
title: Verwalten von Sprach- und Anrufrichtlinien in Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Erfahren Sie mehr Teams Richtlinien für Sprach- und Anrufanrufe.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b3cea712fee971ce441e5406bc32c1304c4a53374baf290046945595d3bea1f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335805"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Verwalten von Sprach- und Anrufrichtlinien in Microsoft Teams

Sprach- und Anrufrichtlinien werden verwendet, um Die Sprach- und Anrufsteuerung in Microsoft Teams.

## <a name="emergency-calling-policies"></a>Richtlinien für Notrufe

Mithilfe von [Richtlinien für Notrufe](manage-emergency-calling-policies.md) können Sie konfigurieren, was passiert, wenn ein Benutzer in Ihrer Organisation einen Notruf ablaget. Diese Richtlinien werden im Teams Admin Center verwaltet oder mithilfe Windows PowerShell.

![Screenshot der Richtlinie für Notrufe](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Richtlinien für die Weiterleitung von Notrufen

Wenn Ihre Organisation Telefonsystem **Direct Routing** bereitgestellt hat, [](manage-emergency-call-routing-policies.md) können Sie mithilfe von Richtlinien für das Routing von Notrufen ermitteln, wohin Notrufe umgeschaltet werden, ob erweiterte Notdienste aktiviert sind und welche Nummern für Notdienste verwendet werden. Diese Richtlinien werden mithilfe von PowerShell oder im Microsoft Teams Admin Center verwaltet.

![Screenshot der Richtlinie für die Weiterleitung von Notrufen](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Richtlinien für Anrufer-IDs

[Anrufer-ID-Richtlinien](caller-id-policies.md) werden verwendet, um die Anrufer-ID zu ändern oder zu blockieren.

![Screenshot der Anrufer-ID-Richtlinie](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Richtlinien für das Voice Routing

Eine [Voice Routing-Richtlinie](manage-voice-routing-policies.md) ist ein Container für PSTN-Nutzungsdatensätze (Public Switched Telephone Network). Sie können diese Richtlinien verwenden, wenn Ihre Organisation das **Direct-Routing Telefonsystem hat.** Richtlinien für das Sprachrouting können mit PowerShell oder im admin center Teams verwaltet werden.

![Screenshot der Voice Routing-Richtlinie](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Anrufpläne

[Anrufrichtlinien steuern,](teams-calling-policy.md) welche Anruf- und Anruf weiterleitungsfunktionen benutzern zur Verfügung stehen, z. B. ob ein Benutzer private Anrufe machen, Anrufe an Anrufgruppen senden und Anrufe an die Voicemail weiterleiten kann.

![Screenshot der Anrufrichtlinie](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Parken von Anrufen und Abrufen von Richtlinien

[Durch das Parken und Abrufen](call-park-and-retrieve.md) von Anrufen können Benutzer andere Benutzer in die Warteschleife setzen und den Anruf mit demselben Benutzer oder einer anderen Person fortsetzen.

![Screenshot von Anruf parken und Richtlinie abrufen](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wählplänen

[Wählpläne](create-and-manage-dial-plans.md) übersetzen gewählte Telefonnummern für die Anrufautorisierung und Weiterleitung. Sie können Wählpläne über PowerShell oder im Microsoft Teams Admin Center erstellen und verwalten.

![Screenshot des Wählplans](media/dial-plans.png)

## <a name="related-topics"></a>Verwandte Themen

* [Verwalten von Richtlinien für Notrufe in Microsoft Teams](manage-emergency-calling-policies.md)
* [Verwalten von Notfall-Anrufweiterleitungsrichtlinien](manage-emergency-call-routing-policies.md)
* [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md).
* [Verwalten von Voice Routing-Richtlinien](manage-voice-routing-policies.md)
* [Anrufrichtlinien in Microsoft Teams](teams-calling-policy.md)
* [Parken und Fortsetzen von Anrufen in Microsoft Teams](call-park-and-retrieve.md)
* [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)
* [Verwalten Teams mit Richtlinien](manage-teams-with-policies.md)
