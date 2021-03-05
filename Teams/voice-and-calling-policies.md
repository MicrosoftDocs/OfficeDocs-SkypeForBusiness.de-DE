---
title: Verwalten von Sprach- und Anrufrichtlinien in Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Erfahren Sie mehr über Die Sprach- und Anrufrichtlinien von Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460585"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Verwalten von Sprach- und Anrufrichtlinien in Microsoft Teams

Sprach- und Anrufrichtlinien werden verwendet, um Sprach- und Anrufsteuerungen in Microsoft Teams zu steuern.

## <a name="emergency-calling-policies"></a>Richtlinien für Notrufe

Sie verwenden [Richtlinien für Notrufe,](manage-emergency-calling-policies.md) um zu konfigurieren, was geschieht, wenn ein Benutzer in Ihrer Organisation einen Notruf ab nimmt. Diese Richtlinien werden im Teams Admin Center oder mithilfe von Windows PowerShell.

![Screenshot der Richtlinie für Notrufe.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Richtlinien für das Routing von Notrufen

Wenn Ihre Organisation direktes Telefonsystemrouting [](manage-emergency-call-routing-policies.md) bereitgestellt **hat,** können Sie mithilfe von Richtlinien für das Routing von Notrufen ermitteln, wo Notrufe angerufen werden, ob erweiterte Notfalldienste aktiviert sind und welche Nummern für Notdienste verwendet werden. Diese Richtlinien werden mithilfe von PowerShell oder im Microsoft Teams Admin Center verwaltet.

![Screenshot der Routingrichtlinie für Notrufe.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Anrufer-ID-Richtlinien

[Anrufer-ID-Richtlinien](caller-id-policies.md) werden verwendet, um die Anrufer-ID zu ändern oder zu blockieren.

![Screenshot der Anrufer-ID-Richtlinie.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Sprachroutingrichtlinien

Eine [Sprachroutingrichtlinie](manage-voice-routing-policies.md) ist ein Container für PstN-Nutzungsdatensätze (Public Switched Telephone Network). Sie können diese Richtlinien verwenden, wenn Ihre Organisation **telefonsystem-direktes Routing bereitgestellt hat.** Sprachroutingrichtlinien können mit PowerShell oder im Teams Admin Center verwaltet werden.

![Screenshot der Sprachroutingrichtlinie.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Anrufpläne

[Anrufrichtlinien steuern,](teams-calling-policy.md) welche Anruf- und Anruf weiterleitungsfeatures für Benutzer verfügbar sind, einschließlich der Frage, ob ein Benutzer private Anrufe machen, Anrufe an Anrufgruppen senden und Anrufe an Voicemail weiterleiten kann.

![Screenshot der Anrufrichtlinie.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Anrufpark- und -abrufrichtlinien

[Durch das Parken](call-park-and-retrieve.md) und Abrufen von Anrufen können Benutzer andere Benutzer in den Halteraum setzen und es demselben Benutzer oder einer anderen Person ermöglichen, den Anruf weiter zu führen.

![Screenshot der Anrufpark- und -abrufrichtlinie.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wählplänen

[Wählpläne](create-and-manage-dial-plans.md) übersetzen wählte Telefonnummern für die Anrufautorisierung und -weiterleitung. Sie können Wählpläne über PowerShell oder im Microsoft Teams Admin Center erstellen und verwalten.

![Screenshot des Wählplans.](media/dial-plans.png)

## <a name="related-topics"></a>Verwandte Themen

* [Verwalten von Richtlinien für Notrufe in Microsoft Teams](manage-emergency-calling-policies.md)
* [Verwalten von Notfall-Anrufweiterleitungsrichtlinien](manage-emergency-call-routing-policies.md)
* [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md).
* [Verwalten von Sprachroutingrichtlinien](manage-voice-routing-policies.md)
* [Anrufrichtlinien in Microsoft Teams](teams-calling-policy.md)
* [Parken und Fortsetzen von Anrufen in Microsoft Teams](call-park-and-retrieve.md)
* [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)
* [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
