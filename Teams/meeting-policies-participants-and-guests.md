---
title: Verwalten von Besprechungsrichtlinien für Teilnehmer und Gäste
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für Teilnehmer und Gäste verwalten.
ms.openlocfilehash: 30ef20368adeb7b0f14ff0c811a1c6ec9d4ce29b6debeeb198f0b74ae75d441d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293272"
---
# <a name="meeting-policy-settings---participants--guests"></a>Besprechungsrichtlinieneinstellungen – Teilnehmer und Gäste

<a name="bkmeetingparticipants"> </a>

Über diese Einstellungen können Sie steuern, welche Besprechungsteilnehmer im Wartebereich bleiben müssen, bevor sie zur Besprechung zugelassen werden. Außerdem wird die Berechtigungsstufe während ihrer Teilnahme an Besprechungen festgelegt.

- [Anonymen Personen das Starten einer Besprechung gestatten](#let-anonymous-people-start-a-meeting)
- [Personen automatisch zulassen](#automatically-admit-people)
- [Einwahlbenutzern das Umgehen des Wartebereichs gestatten](#allow-dial-in-users-to-bypass-the-lobby)
- [Liveuntertitel aktivieren](#enable-live-captions)
- [Chat in Besprechungen zulassen](#allow-chat-in-meetings)

> [!NOTE]
>Die Optionen zur Teilnahme an einer Besprechung variieren je nach den Einstellungen für die einzelnen Microsoft Teams-Gruppen und der Verbindungsmethode. Wenn Ihre Gruppe über Audiokonferenzen verfügt und sie für die Verbindung verwendet, sehen Sie sich [Audiokonferenzen](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365) an. Wenn Ihre Microsoft Teams-Gruppe nicht über Audiokonferenzen verfügt, finden Sie weitere Informationen unter [Teilnehmen an einer Besprechung in Microsoft Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-start-a-meeting"></a>Anonymen Personen das Starten einer Besprechung gestatten

Bei dieser Einstellung handelt es sich um eine Richtlinie pro Organisator, die besprechungsfreie Einwahlkonferenzen ohne Vorzeichen ermöglicht. Über diese Einstellung wird gesteuert, ob Einwahlbenutzer an einer Besprechung teilnehmen können, ohne dass ein authentifizierter Benutzer aus der Organisation teilnimmt. Diese Einstellung ist standardmäßig deaktiviert, d. h., Einwahlbenutzer warten im Wartebereich, bis ein authentifizierter Benutzer aus der Organisation der Besprechung beitritt.

> [!NOTE]
> Wenn diese Einstellung deaktiviert ist und ein Einwahlbenutzer als erster der Besprechung beitritt und in den Wartebereich gesetzt wird, muss ein Benutzer der Organisation der Besprechung mit einem Microsoft Teams-Client beitreten, um den Benutzer aus dem Wartebereich zur Besprechung zuzulassen. Den Einwahlbenutzern stehen keine Steuerelemente für den Wartebereich zur Verfügung.

## <a name="automatically-admit-people"></a>Personen automatisch zulassen

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Personen direkt an einer Besprechung teilnehmen können oder im Wartebereich bleiben müssen, bis sie von einem authentifizierten Benutzer zugelassen werden. Diese Einstellung gilt nicht für Einwahlbenutzer.

![Screenshot einer Besprechung mit einem Benutzer im Wartebereich](media/meeting-policies-lobby.png)

 Besprechungsorganisatoren können in der Besprechungseinladung auf **Besprechungsoptionen** klicken, um diese Einstellung für jede von ihnen geplante Besprechung zu ändern.

> [!NOTE]
> In den Besprechungsoptionen lautet die Einstellung "Wer kann den Wartebereich umgehen?" Wenn Sie die Standardeinstellung für einen Benutzer ändern, gilt diese für alle neuen Besprechungen, die von diesem Benutzer organisiert werden, sowie für alle vorherigen Besprechungen, in denen der Benutzer die Besprechungsoptionen nicht geändert hatte.
  
|Einstellungswert  |Verhalten bei Teilnahme |
|---------|---------|
|**Jeder**   |Alle Besprechungsteilnehmer nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Dazu gehören authentifizierte Benutzer, externe Benutzer aus vertrauenswürdigen Organisationen (Verbundorganisationen), Gäste und anonyme Benutzer.     |
|**Personen in meiner Organisation und Gäste**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer, nehmen direkt an der Besprechung teil, ohne im Wartebereich warten zu müssen.  Anonyme Benutzer müssen im Wartebereich warten.   |
|**Personen in meiner Organisation oder vertrauenswürdigen Organisationen und Gäste**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer und Benutzer aus vertrauenswürdigen Organisationen, nehmen an der Besprechung direkt teil, ohne im Wartebereich warten zu müssen.  Anonyme Benutzer müssen im Wartebereich warten.   |
|**Jeder in meiner Organisation**    |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer, nehmen an der Besprechung direkt teil, ohne im Wartebereich warten zu müssen.  Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer müssen im Wartebereich warten. Dies ist die Standardeinstellung.           |
|**Nur Organisatoren**    |Alle Besprechungsorganisatoren nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Alle anderen Benutzer, einschließlich authentifizierter Benutzer innerhalb der Organisation, Gastbenutzer, Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer, müssen im Wartebereich warten.           |
|**Nur eingeladene Benutzer**    |Nur eingeladene Benutzer und Besprechungsorganisatoren können direkt an der Besprechung teilnehmen, ohne im Wartebereich warten zu müssen. Alle anderen Benutzer, einschließlich authentifizierter Benutzer innerhalb der Organisation, Gastbenutzer, Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer, müssen im Wartebereich warten.           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Einwahlbenutzern das Umgehen des Wartebereichs gestatten

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Personen, die sich per Telefon in die Besprechung einwählen, direkt an der Besprechung teilnehmen können oder im Wartebereich warten müssen – unabhängig von der Einstellung **Personen automatisch zulassen**. Diese Einstellung ist standardmäßig deaktiviert. Wenn diese Einstellung deaktiviert ist, müssen Einwahlbenutzer im Wartebereich bleiben, bis ein Benutzer der Organisation der Besprechung mit einem Microsoft Teams-Client beitritt und sie zulässt. Wenn diese Einstellung aktiviert ist, treten die Einwahlbenutzer automatisch der Besprechung bei, wenn ein Benutzer aus der Organisation beitritt.

> [!NOTE]
> Wenn ein Einwahlbenutzer einer Besprechung beitritt, bevor ein Benutzer aus der Organisation beitritt, wird er in den Wartebereich gesetzt, bis ein Benutzer aus der Organisation der Besprechung mit einem Microsoft Teams-Client beitritt und ihn zulässt. Wenn Sie die Standardeinstellung für einen Benutzer ändern, gilt diese für alle neuen Besprechungen, die von diesem Benutzer organisiert werden, sowie für alle vorherigen Besprechungen, in denen der Benutzer die Besprechungsoptionen nicht geändert hatte.

## <a name="enable-live-captions"></a>Liveuntertitel aktivieren

Diese Einstellung ist eine Benutzerrichtlinie und gilt während einer Besprechung. Über diese Einstellung wird gesteuert, ob die Option zum **Aktivieren von Liveuntertiteln** verfügbar ist, damit die Benutzer die Liveuntertitel während einer Besprechung aktivieren bzw. deaktivieren können.  

![Screenshot mit der Option zum Aktivieren von Liveuntertiteln](media/meeting-policies-live-captions.png)

|Einstellungswert |Verhalten  |
|---------|---------|
|**Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen**     | Standardmäßig sind Liveuntertitel während einer Besprechung nicht automatisch für Benutzende aktiviert. Die Benutzer sehen die Option **Liveuntertitel aktivieren** im Menü-Überlauf (**...**), über die sie eingeschaltet werden können. Dies ist die Standardeinstellung. |
|**Deaktiviert**     | Liveuntertitel sind während einer Besprechung für den Benutzer deaktiviert. Der Benutzer kann sie nicht aktivieren.          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>Chat in Besprechungen zulassen

Bei dieser Einstellung handelt es sich um eine Einstellung pro Teilnehmer. Über diese Einstellung wird gesteuert, ob in der Besprechung des Benutzers das Chatten zulässig ist.

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
