---
title: Verwalten von Besprechungsrichtlinien für Teilnehmer und Gäste
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
ms.openlocfilehash: ac77ab8b032fa792b0b137c84679912768e3b1b6
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457375"
---
# <a name="meeting-policy-settings---participants--guests"></a>Besprechungsrichtlinieneinstellungen – Teilnehmer und Gäste

<a name="bkmeetingparticipants"> </a>

Über diese Einstellungen können Sie steuern, welche Besprechungsteilnehmer im Wartebereich bleiben müssen, bevor sie zur Besprechung zugelassen werden. Außerdem wird die Berechtigungsstufe während ihrer Teilnahme an Besprechungen festgelegt.

- [Anonymen Personen das Starten einer Besprechung gestatten](#let-anonymous-people-start-a-meeting)
- [Personen automatisch zulassen](#automatically-admit-people)
- [Einwahlbenutzern das Umgehen des Wartebereichs gestatten](#allow-dial-in-users-to-bypass-the-lobby)
- [Liveuntertitel](#live-captions)
- [Chatten in Besprechungen](#chat-in-meetings)

> [!NOTE]
>Die Optionen zur Teilnahme an einer Besprechung variieren je nach den Einstellungen für die einzelnen Microsoft Teams-Gruppen und der Verbindungsmethode. Wenn Ihre Gruppe über Audiokonferenzen verfügt und sie für die Verbindung verwendet, sehen Sie sich [Audiokonferenzen](/microsoftteams/audio-conferencing-in-office-365) an. Wenn Ihre Microsoft Teams-Gruppe nicht über Audiokonferenzen verfügt, finden Sie weitere Informationen unter [Teilnehmen an einer Besprechung in Microsoft Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).


## <a name="let-anonymous-people-start-a-meeting"></a>Anonymen Personen das Starten einer Besprechung gestatten

Bei dieser Einstellung handelt es sich um eine Richtlinie pro Organisator, die besprechungsfreie Einwahlkonferenzen ohne Vorzeichen ermöglicht. Über diese Einstellung wird gesteuert, ob Einwahlbenutzer an einer Besprechung teilnehmen können, ohne dass ein authentifizierter Benutzer aus der Organisation teilnimmt. Diese Einstellung ist standardmäßig deaktiviert, d. h., Einwahlbenutzer warten im Wartebereich, bis ein authentifizierter Benutzer aus der Organisation der Besprechung beitritt.

> [!NOTE]
> Wenn diese Einstellung deaktiviert ist und ein Einwahlbenutzer als erster der Besprechung beitritt und in den Wartebereich gesetzt wird, muss ein Benutzer der Organisation der Besprechung mit einem Microsoft Teams-Client beitreten, um den Benutzer aus dem Wartebereich zur Besprechung zuzulassen. Den Einwahlbenutzern stehen keine Steuerelemente für den Wartebereich zur Verfügung.

## <a name="automatically-admit-people"></a>Personen automatisch zulassen

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Personen direkt an einer Besprechung teilnehmen können oder im Wartebereich bleiben müssen, bis sie von einem authentifizierten Benutzer zugelassen werden. Diese Einstellung gilt nicht für Einwahlbenutzer.

![Screenshot zeigt eine Besprechung mit einem Benutzer im Wartebereich.](media/meeting-policies-lobby.png)

 Besprechungsorganisatoren können in der Besprechungseinladung auf **Besprechungsoptionen** klicken, um diese Einstellung für jede von ihnen geplante Besprechung zu ändern.

> [!NOTE]
> In den Besprechungsoptionen lautet die Einstellung "Wer kann den Wartebereich umgehen?" Wenn Sie die Standardeinstellung für einen Benutzer ändern, gilt diese für alle neuen Besprechungen, die von diesem Benutzer organisiert werden, sowie für alle vorherigen Besprechungen, in denen der Benutzer die Besprechungsoptionen nicht geändert hatte.
  
|Einstellungswert  |Verhalten bei Teilnahme |
|---------|---------|
|**Jeder**   |Alle Besprechungsteilnehmer nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Dazu gehören authentifizierte Benutzer, externe Benutzer aus vertrauenswürdigen Organisationen (Verbundorganisationen), Gäste und anonyme Benutzer.     |
|**Personen in meiner Organisation und Gäste**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer, nehmen direkt an der Besprechung teil, ohne im Wartebereich warten zu müssen. Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer warten im Wartebereich. Dies ist die Standardeinstellung.    |
|**Personen in meiner Organisation oder vertrauenswürdigen Organisationen und Gäste**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer und Benutzer aus vertrauenswürdigen Organisationen, nehmen an der Besprechung direkt teil, ohne im Wartebereich warten zu müssen.  Anonyme Benutzer müssen im Wartebereich warten.   |
|**Personen in meiner Organisation**    |Authentifizierte Benutzer innerhalb der Organisation nehmen direkt an der Besprechung teil, ohne im Wartebereich zu warten.  Benutzer von vertrauenswürdigen Organisationen, Gastbenutzern und anonymen Benutzern warten im Wartebereich.          |
|**Nur Organisatoren**    |Alle Besprechungsorganisatoren nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Alle anderen Benutzer, einschließlich authentifizierter Benutzer innerhalb der Organisation, Gastbenutzer, Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer, müssen im Wartebereich warten. Auf der Teams für Client-Besprechungsoptionen wird sie als "Nur ich" angezeigt.          |
|**Nur eingeladene Benutzer**    |Nur eingeladene Benutzer und Besprechungsorganisatoren können direkt an der Besprechung teilnehmen, ohne im Wartebereich warten zu müssen. Alle anderen Benutzer, einschließlich authentifizierter Benutzer innerhalb der Organisation, Gastbenutzer, Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer, müssen im Wartebereich warten. Auf der Teams optionen für Client-Besprechungen wird sie als "Personen, die ich lade" angezeigt. Benutzer, die als Teil einer Verteilergruppe hinzugefügt wurden, müssen den Wartebereich durchgehen.      |

 > [!NOTE]
> Bei vertrauenswürdigen Organisationen handelt es sich um Domänen, mit denen Sie Verbundkommunikation in Teams. Wenn **Sie Alle externen** Domänen für externen Zugriff zulassen im Teams Admin Center aktivieren, werden alle authentifizierten Benutzer innerhalb einer Teams Organisation als vertrauenswürdig eingestuft. Wenn Sie externe Domänen angeben, die zulässig sind, und alle anderen blockieren, werden die zulässigen Domänen zu vertrauenswürdigen Organisationen. Jede blockierte Domäne wird als keine vertrauenswürdige Organisation betrachtet.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Einwahlbenutzern das Umgehen des Wartebereichs gestatten

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Personen, die sich per Telefon in die Besprechung einwählen, direkt an der Besprechung teilnehmen können oder im Wartebereich warten müssen – unabhängig von der Einstellung **Personen automatisch zulassen**. Diese Einstellung ist standardmäßig deaktiviert. Wenn diese Einstellung deaktiviert ist, müssen Einwahlbenutzer im Wartebereich bleiben, bis ein Benutzer der Organisation der Besprechung mit einem Microsoft Teams-Client beitritt und sie zulässt. Wenn diese Einstellung aktiviert ist, treten die Einwahlbenutzer automatisch der Besprechung bei, wenn ein Benutzer aus der Organisation beitritt.

> [!NOTE]
> Wenn ein Einwahlbenutzer einer Besprechung beitritt, bevor ein Benutzer aus der Organisation beitritt, wird er in den Wartebereich gesetzt, bis ein Benutzer aus der Organisation der Besprechung mit einem Microsoft Teams-Client beitritt und ihn zulässt. Wenn Sie die Standardeinstellung für einen Benutzer ändern, gilt diese für alle neuen Besprechungen, die von diesem Benutzer organisiert werden, sowie für alle vorherigen Besprechungen, in denen der Benutzer die Besprechungsoptionen nicht geändert hatte.

## <a name="live-captions"></a>Liveuntertitel

Diese Einstellung ist eine Benutzerrichtlinie und gilt während einer Besprechung. Über diese Einstellung wird gesteuert, ob die Option zum **Aktivieren von Liveuntertiteln** verfügbar ist, damit die Benutzer die Liveuntertitel während einer Besprechung aktivieren bzw. deaktivieren können.  

![Screenshot zeigt die Option zum Aktivieren von Liveuntertiteln.](media/meeting-policies-live-captions.png)

|Einstellungswert |Verhalten  |
|---------|---------|
|**Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen**     | Standardmäßig sind Liveuntertitel während einer Besprechung nicht automatisch für Benutzende aktiviert. Die Benutzer sehen die Option **Liveuntertitel aktivieren** im Menü-Überlauf (**...**), über die sie eingeschaltet werden können. Dies ist die Standardeinstellung. |
|**Deaktiviert**     | Liveuntertitel sind während einer Besprechung für den Benutzer deaktiviert. Der Benutzer kann sie nicht aktivieren.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chatten in Besprechungen

Bei dieser Einstellung handelt es sich um eine Einstellung pro Teilnehmer. Über diese Einstellung wird gesteuert, ob in der Besprechung des Benutzers das Chatten zulässig ist.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Für jeden aktivieren**     | Alle Teilnehmer können Chatnachrichten schreiben und anzeigen. |
|**Für jeden deaktivieren**     | Der Besprechungschat ist für alle Teilnehmer deaktiviert.  |
|**Aktivieren Sie dies für alle Benutzer, jedoch für anonyme Benutzer.**| Anonyme Benutzer können in Besprechungen nicht chatten, aber Nachrichten lesen. |

<a name="bkparticipantsandguests"> </a>

## <a name="enable-meeting-policy-settings"></a>Aktivieren von Besprechungsrichtlinieneinstellungen

Zum Aktivieren von Besprechungsrichtlinieneinstellungen können Sie das [Teams Admin Center](https://admin.teams.microsoft.com/policies/meetings) **(** > BesprechungsrichtlinienBearbeiten einer **RichtlinieTeilipants** >  & Gäste) oder das [Set-CsTeamsMeetingPolicy-Cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) in Teams PowerShell verwenden. 

In diesem Beispiel verwenden wir PowerShell, um die globale Besprechungsrichtlinie so zu ändern, dass jeder Besprechung beginnen oder teilnehmen kann.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Nachdem Sie eine Richtlinie eingerichtet haben, müssen Sie diese auf Benutzer anwenden. Wenn Sie die Globale (organisationsweite Standardrichtlinie) geändert haben, gilt sie automatisch für Benutzer. Sie müssen mindestens 4 Stunden warten, bis Richtlinienänderungen wirksam werden, es kann jedoch bis zu 24 Stunden dauern.


## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
