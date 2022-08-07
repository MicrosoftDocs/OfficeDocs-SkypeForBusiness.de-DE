---
title: Verwalten von VoIP- und Anrufrichtlinien in Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Erfahren Sie mehr über Die VoIP- und Anrufrichtlinien von Teams.
audience: admin
ms.localizationpriority: medium
ms.collection:
- M365-voice
ms.openlocfilehash: 5a6676d29a439ed978385d096c6e8b0584049557
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270290"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Verwalten von VoIP- und Anrufrichtlinien in Microsoft Teams

VoIP- und Anrufrichtlinien werden verwendet, um VoIP und Anrufe in Microsoft Teams zu steuern.

## <a name="emergency-calling-policies"></a>Richtlinien für Notrufe

Sie verwenden [Notrufrichtlinien](manage-emergency-calling-policies.md) , um zu konfigurieren, was geschieht, wenn ein Benutzer in Ihrer Organisation einen Notruf abnimmt. Diese Richtlinien werden im Teams Admin Center oder mithilfe von Windows PowerShell verwaltet.

![Screenshot der Richtlinie für Notrufe.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Richtlinien für die Notrufweiterleitung

Wenn Ihre Organisation **Direct Routing für Telefonsysteme** bereitgestellt hat, können Sie mithilfe von Richtlinien für die [Notrufweiterleitung](manage-emergency-call-routing-policies.md) ermitteln, wo Notrufe weitergeleitet werden, ob erweiterte Notrufdienste aktiviert sind und welche Nummern für Notrufdienste verwendet werden. Diese Richtlinien werden mithilfe von PowerShell oder im Microsoft Teams Admin Center verwaltet.

![Screenshot der Richtlinie für die Notrufweiterleitung.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Anrufer-ID-Richtlinien

[Anrufer-ID-Richtlinien](caller-id-policies.md) werden verwendet, um die Anrufer-ID zu ändern oder zu blockieren.

![Screenshot der Anrufer-ID-Richtlinie.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>VoIP-Routingrichtlinien

Eine [VoIP-Routingrichtlinie](manage-voice-routing-policies.md) ist ein Container für PSTN-Verwendungsdatensätze (Public Switched Telephone Network). Sie können diese Richtlinien verwenden, wenn Ihre Organisation **Direct Routing für Telefonsysteme** bereitgestellt hat. VoIP-Routingrichtlinien können mit PowerShell oder im Teams Admin Center verwaltet werden.

![Screenshot der VoIP-Routingrichtlinie.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Anrufpläne

[Anrufrichtlinien](teams-calling-policy.md) steuern, welche Anruf- und Anrufweiterleitungsfeatures benutzern zur Verfügung stehen, einschließlich, ob ein Benutzer private Anrufe tätigen, Anrufe an Anrufgruppen senden und Anrufe an Voicemail weiterleiten kann.

![Screenshot der Anrufrichtlinie.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Richtlinien für das Parken und Abrufen von Anrufen

[Mit dem Parken und Abrufen](call-park-and-retrieve.md) von Anrufen können Benutzer andere Benutzer in die Warteschleife setzen und demselben Benutzer oder einer anderen Person ermöglichen, den Anruf fortzusetzen.

![Screenshot der Richtlinie zum Parken und Abrufen von Anrufen.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wählplänen

[Wählpläne](create-and-manage-dial-plans.md) übersetzen gewählte Telefonnummern für die Anrufautorisierung und -weiterleitung. Sie können Wählpläne über PowerShell oder im Microsoft Teams Admin Center erstellen und verwalten.

![Screenshot des Wählplans.](media/dial-plans.png)

## <a name="related-topics"></a>Verwandte Themen

* [Verwalten von Notrufrichtlinien in Microsoft Teams](manage-emergency-calling-policies.md)
* [Verwalten von Notfall-Anrufweiterleitungsrichtlinien](manage-emergency-call-routing-policies.md)
* [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md).
* [Verwalten von VoIP-Routingrichtlinien](manage-voice-routing-policies.md)
* [Anrufrichtlinien in Microsoft Teams](teams-calling-policy.md)
* [Parken und Fortsetzen von Anrufen in Microsoft Teams](call-park-and-retrieve.md)
* [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)
* [Verwalten von Microsoft Teams mit Richtlinien](manage-teams-with-policies.md)
