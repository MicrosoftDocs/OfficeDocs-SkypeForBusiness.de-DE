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
ms.openlocfilehash: 7f9cb76e12671425ee2b7b0543263195796e04d5
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713353"
---
# <a name="meeting-policy-settings---participants--guests"></a>Besprechungsrichtlinieneinstellungen – Teilnehmer und Gäste

<a name="bkmeetingparticipants"> </a>

Diese Einstellungen steuern, welche Besprechungsteilnehmer im Wartebereich warten, bevor sie zur Besprechung zugelassen werden, und die Teilnahmestufe, die sie an einer Besprechung zulassen.

- [Zulassen, dass anonyme Personen an einer Besprechung teilnehmen](#let-anonymous-people-join-a-meeting)
- [Anonymen Personen das Starten einer Besprechung gestatten](#let-anonymous-people-start-a-meeting)
- [Personen automatisch zulassen](#automatically-admit-people)
- [Einwahlbenutzern das Umgehen des Wartebereichs gestatten](#allow-dial-in-users-to-bypass-the-lobby)
- [Liveuntertitel](#live-captions)
- [Chatten in Besprechungen](#chat-in-meetings)

> [!NOTE]
>Die Optionen zur Teilnahme an einer Besprechung variieren je nach den Einstellungen für die einzelnen Microsoft Teams-Gruppen und der Verbindungsmethode. Wenn Ihre Gruppe über Audiokonferenzen verfügt und sie für die Verbindung verwendet, sehen Sie sich [Audiokonferenzen](/microsoftteams/audio-conferencing-in-office-365) an. Wenn Ihre Microsoft Teams-Gruppe nicht über Audiokonferenzen verfügt, finden Sie weitere Informationen unter [Teilnehmen an einer Besprechung in Microsoft Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Zulassen, dass anonyme Personen an einer Besprechung teilnehmen

Mit dieser Einstellung pro Organisator kann jeder als anonymer Benutzer an Besprechungen teilnehmen, indem er den Link in der Besprechungseinladung auswählt. Weitere Informationen hierzu finden Sie unter [Teilnehmen an einer Besprechung ohne ein Teams-Konto](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). Die Möglichkeit anonymer Benutzer, an Besprechungen teilzunehmen, wird auch auf Organisationsebene gesteuert. Die restriktivere Einstellung ist effektiv. Weitere Informationen finden Sie unter [Verwenden des Microsoft Teams Admin Centers zum Konfigurieren organisationsweiter Richtlinien](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Anonymen Personen das Starten einer Besprechung gestatten

Diese Einstellung ist eine organisatorspezifische Richtlinie, die führende Einwahlkonferenzbesprechungen ohne Führungskraft ermöglicht. Über diese Einstellung wird gesteuert, ob Einwahlbenutzer an einer Besprechung teilnehmen können, ohne dass ein authentifizierter Benutzer aus der Organisation teilnimmt. Standardmäßig ist diese Einstellung deaktiviert, was bedeutet, dass Einwahlbenutzer im Wartebereich warten, bis ein authentifizierter Benutzer aus der Organisation an der Besprechung teilnimmt.

> [!NOTE]
> Wenn diese Einstellung deaktiviert ist und ein Einwahlbenutzer als erster der Besprechung beitritt und in den Wartebereich gesetzt wird, muss ein Benutzer der Organisation der Besprechung mit einem Microsoft Teams-Client beitreten, um den Benutzer aus dem Wartebereich zur Besprechung zuzulassen. Den Einwahlbenutzern stehen keine Steuerelemente für den Wartebereich zur Verfügung.

## <a name="automatically-admit-people"></a>Personen automatisch zulassen

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Diese Einstellung steuert, ob Personen direkt an einer Besprechung teilnehmen oder im Wartebereich warten, bis sie von einem authentifizierten Benutzer zugelassen werden. Diese Einstellung gilt nicht für Einwahlbenutzer.

![Screenshot zeigt eine Besprechung mit einem Benutzer im Wartebereich.](media/meeting-policies-lobby.png)

 Besprechungsorganisatoren können in der Besprechungseinladung auf **Besprechungsoptionen** klicken, um diese Einstellung für jede von ihnen geplante Besprechung zu ändern.

> [!NOTE]
> In den Besprechungsoptionen lautet die Einstellung "Wer kann den Wartebereich umgehen?" Wenn Sie die Standardeinstellung für einen Benutzer ändern, gilt diese für alle neuen Besprechungen, die von diesem Benutzer organisiert werden, sowie für alle vorherigen Besprechungen, in denen der Benutzer die Besprechungsoptionen nicht geändert hatte.
  
|Einstellungswert  |Verhalten bei Teilnahme |
|---------|---------|
|**Jeder**   |Alle Besprechungsteilnehmer nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Dazu gehören authentifizierte Benutzer, Benutzer aus vertrauenswürdigen Organisationen, Gäste und anonyme Benutzer.     |
|**Personen in meiner Organisation und Gäste**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gäste, nehmen direkt an der Besprechung teil, ohne im Wartebereich zu warten. Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer müssen im Wartebereich warten. Dies ist die Standardeinstellung.    |
|**Personen in meiner Organisation oder vertrauenswürdigen Organisationen und Gäste**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gäste und die Benutzer aus vertrauenswürdigen Organisationen, nehmen direkt an der Besprechung teil, ohne im Wartebereich zu warten.  Anonyme Benutzer müssen im Wartebereich warten.   |
|**Personen in meiner Organisation**    |Authentifizierte Benutzer aus der Organisation nehmen direkt an der Besprechung teil, ohne im Wartebereich zu warten.  Benutzer aus vertrauenswürdigen Organisationen, Gästen und anonymen Benutzern warten im Wartebereich.          |
|**Nur Organisatoren**    |Alle Besprechungsorganisatoren nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Alle anderen Benutzer, einschließlich authentifizierter Benutzer innerhalb der Organisation, Gäste, Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer müssen im Wartebereich warten. Auf der Seite "Optionen für Microsoft Teams-Clientbesprechungsoptionen" wird sie als "Nur ich" angezeigt.          |
|**Nur eingeladene Benutzer**    |Nur eingeladene Benutzer und Besprechungsorganisatoren können direkt an der Besprechung teilnehmen, ohne im Wartebereich zu warten. Alle anderen Benutzer, einschließlich authentifizierter Benutzer innerhalb der Organisation, Gäste, Benutzer aus vertrauenswürdigen Organisationen und anonyme Benutzer müssen im Wartebereich warten. Auf der Seite "Optionen für Microsoft Teams-Clientbesprechungsoptionen" wird sie als "Personen, die ich einlädt" angezeigt. Benutzer, die als Teil einer Verteilergruppe hinzugefügt wurden, müssen den Wartebereich durchlaufen.      |

 > [!NOTE]
> Vertrauenswürdige Organisationen sind Domänen, mit denen Sie die Verbundkommunikation in Teams zulassen. Wenn Sie **alle externen Domänen** für den externen Zugriff im Teams Admin Center zulassen aktivieren, wird jedem authentifizierten Benutzer innerhalb einer Teams-Organisation vertraut. Wenn Sie externe Domänen angeben, die zulässig sind, und alle anderen blockieren, werden die zulässigen Domänen zu vertrauenswürdigen Organisationen. Jede blockierte Domäne wird als keine vertrauenswürdige Organisation betrachtet.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Einwahlbenutzern das Umgehen des Wartebereichs gestatten

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Personen, die sich per Telefon in die Besprechung einwählen, direkt an der Besprechung teilnehmen können oder im Wartebereich warten müssen – unabhängig von der Einstellung **Personen automatisch zulassen**. Diese Einstellung ist standardmäßig deaktiviert. Wenn diese Einstellung deaktiviert ist, müssen Einwahlbenutzer im Wartebereich bleiben, bis ein Benutzer der Organisation der Besprechung mit einem Microsoft Teams-Client beitritt und sie zulässt. Wenn diese Einstellung aktiviert ist, nehmen Einwahlbenutzer automatisch an der Besprechung teil, wenn ein Benutzer der Organisation mit einem Teams-Client an der Besprechung teilnimmt.

> [!NOTE]
> Wenn ein Einwahlbenutzer einer Besprechung beitritt, bevor ein Benutzer aus der Organisation beitritt, wird er in den Wartebereich gesetzt, bis ein Benutzer aus der Organisation der Besprechung mit einem Microsoft Teams-Client beitritt und ihn zulässt. Wenn Sie die Standardeinstellung für einen Benutzer ändern, gilt diese für alle neuen Besprechungen, die von diesem Benutzer organisiert werden, sowie für alle vorherigen Besprechungen, in denen der Benutzer die Besprechungsoptionen nicht geändert hatte.

## <a name="live-captions"></a>Liveuntertitel

Diese Einstellung ist eine Benutzerrichtlinie und gilt während einer Besprechung. Über diese Einstellung wird gesteuert, ob die Option zum **Aktivieren von Liveuntertiteln** verfügbar ist, damit die Benutzer die Liveuntertitel während einer Besprechung aktivieren bzw. deaktivieren können.  

![Screenshot zeigt die Option zum Aktivieren von Liveuntertiteln.](media/meeting-policies-live-captions.png)

|Einstellungswert |Verhalten  |
|---------|---------|
|**Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen**     | Standardmäßig sind Liveuntertitel während einer Besprechung nicht automatisch für Benutzende aktiviert. Die Benutzer sehen die Option **Liveuntertitel aktivieren** im Menü-Überlauf (**...**), über die sie eingeschaltet werden können. Dies ist die Standardeinstellung. |
|**Nicht aktiviert**     | Liveuntertitel sind während einer Besprechung für den Benutzer deaktiviert. Der Benutzer kann sie nicht aktivieren.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chatten in Besprechungen

Diese Einstellung ist eine Einstellung pro Teilnehmer. Über diese Einstellung wird gesteuert, ob in der Besprechung des Benutzers das Chatten zulässig ist.

Diese Einstellung gilt nicht für Kanalbesprechungen. Sobald diese Besprechungschatrichtlinie auf Benutzer angewendet wurde, kann ein Organisator diese Richtlinie nicht über Besprechungsoptionen außer Kraft setzen.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Aktivieren sie für alle Benutzer**     | Alle Teilnehmer können Chatnachrichten schreiben und anzeigen. |
|**Deaktivieren sie für alle Benutzer**     | Der Besprechungschat ist für alle Teilnehmer deaktiviert.  |
|**Aktivieren sie für alle, aber für anonyme Benutzer**     | Der Schreibzugriff auf Besprechungschats ist nur für anonyme Teilnehmer deaktiviert.  |

<a name="bkparticipantsandguests"> </a>

## <a name="qa-in-meetings"></a>F&A in Besprechungen

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Mit dieser Einstellung können Microsoft 365-Mandantenadministratoren die Benutzeroberfläche "Fragen & Antworten" aktivieren oder deaktivieren (F&A).

Die Einstellung wird erzwungen, wenn eine Besprechung erstellt oder von Organisatoren aktualisiert wird. Diese Einstellung ist standardmäßig deaktiviert. Weitere Informationen zu Q&A [finden Sie hier](/manage-qna-for-meetings).

Der Parameter QnAEngagementMode steuert diese Richtlinie in PowerShell. F&A kann auch im Verwaltungsportal angepasst werden.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Aktiviert**     | Organisatoren können beim Erstellen von Besprechungen Q&A hinzufügen. |
|**Deaktiviert**     | Organisatoren haben nicht die Möglichkeit, beim Erstellen von Besprechungen Q&A hinzuzufügen.  |

## <a name="enable-meeting-policy-settings"></a>Aktivieren von Besprechungsrichtlinieneinstellungen

Um Besprechungsrichtlinieneinstellungen zu aktivieren, können Sie das [Teams Admin Center](https://admin.teams.microsoft.com/policies/meetings) (**Besprechungsrichtlinien** > **bearbeiten einer Richtlinie** > **Teilnehmer & Gäste**) oder das Cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) in Teams PowerShell verwenden. 

In diesem Beispiel verwenden wir PowerShell, um die globale Besprechungsrichtlinie so zu ändern, dass jeder eine Besprechung starten oder daran teilnehmen kann.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Nachdem Sie eine Richtlinie eingerichtet haben, müssen Sie sie auf Benutzer anwenden. Wenn Sie die globale Richtlinie (organisationsweite Standardrichtlinie) geändert haben, gilt sie automatisch für Benutzer. Sie müssen mindestens 4 Stunden warten, bis alle Richtlinienänderungen wirksam werden, es kann jedoch bis zu 24 Stunden dauern.


## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
