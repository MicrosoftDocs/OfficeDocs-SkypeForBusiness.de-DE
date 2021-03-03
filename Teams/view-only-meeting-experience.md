---
title: Besprechungserfahrung nur anzeigen
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die Besprechungserfahrung in Teams, in der nur die Ansicht angezeigt wird, für Administratoren, Sprechteilnehmer und Teilnehmer.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237455"
---
# <a name="teams-view-only-meeting-experience"></a>Besprechungserfahrung in Teams, nur anzeigen

> [!Note]
> Besprechungen, die nur zum Anzeigen verfügbar sind, werden Anfang März 2021 zur Verfügung stehen.

> [!Note]
> Wir haben die Anzeige für 20.000 Teilnehmer vorübergehend erhöht, doch wird die Unterstützung am 30. Juni 2021 auf 10.000 Teilnehmer zurückgesetzt.

Microsoft Teams ermöglicht bis zu 10.000 Teilnehmern die Teilnahme an einer Teams-Besprechung. Nachdem die Kapazität der Haupt besprechung erreicht wurde, werden weitere Teilnehmer mit einer 6-ansichts-Ansicht teilnehmen.

Teilnehmer, die zuerst an der Besprechung teilnehmen, erhalten die volle Teambesprechungserfahrung. Sie können Audio und Video teilen, freigegebene Videos anzeigen und an einem Besprechungschat teilnehmen.

Teilnehmer, die beitreten, nachdem die Hauptkapazität der Besprechung erreicht wurde, verfügen über eine 6-Jahres-Ansicht.

Wir bieten umfassende Unterstützung für mobile Android- und iOS-Geräte, an der ein Teilnehmer teilnehmen kann.

> [!Note]
> Die aktuelle Grenze für die Anzahl der Personen, die chatten und sich in eine Besprechung einrufen können, beträgt 300 im WW und 250 in GCC, GCC High und DoD.

Die Option "Nur anzeigen" ist standardmäßig für jeden Organisator aktiviert, der über E3/E5/A3/A5-SKU verfügt. Es ist keine weitere Konfiguration oder Einrichtung erforderlich.

### <a name="disable-teams-view-only-experience"></a>Deaktivieren der 6-6-Ansicht von Teams

Administratoren können die Anzeige mithilfe von PowerShell deaktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In Zukunft können Administratoren auch die Ansichtserfahrung im Teams Admin Center deaktivieren.

## <a name="impact-to-users"></a>Auswirkungen für Benutzer

Die Benutzerfreundlichkeit hängt von mehreren Faktoren ab.

Wenn die Kapazität der Haupt besprechung erreicht wurde, kann ein Teilnehmer nicht mehr an der Besprechung teilnehmen, wenn eine der folgenden Bedingungen zutrifft:

- Ein Administrator hat die Barrierefreiansicht in Teams deaktiviert.
- Der Teilnehmer verfügt nicht über die Berechtigung zum Umgehen des Wartebereichs.

Wenn die Kapazität der Haupt besprechung erreicht wurde, sehen der Besprechungsorganisator und die Organisator ein Banner mit der Information, dass die Kapazität der Besprechung erreicht wurde und dass neue Teilnehmer einem nur für die Ansicht bestimmten Teilnehmer beitreten werden.

  ![Das Teamclient- und Bannerchaos für Organisatoren und Organisatoren](media/chat-and-banner-message.png)

Wenn die Kapazität der Hauptbesprechung erreicht wurde, werden die Besprechungsteilnehmer auf dem Bildschirm für die Vorabteil am Besprechungsbildschirm informiert, dass sie nur über den Ansichtsmodus teilnehmen.

  ![der Bildschirm "Teams vorab teilnehmen" und die Meldung an die Teilnehmer, dass sie nur im Ansichtsmodus teilnehmen werden](media/view-only-pre-join-screen.png)

Wenn speicherplatz ist, wird ein Benutzer immer an der Haupt besprechung teilnehmen. Wenn die Haupt besprechung Kapazität erreicht und mindestens ein Teilnehmer die Haupt besprechung verlässt, verfügt die Haupt besprechung über verfügbare Kapazität. Teilnehmer, die der Besprechung beitreten (oder erneut beitreten) nehmen an der Haupt besprechung teil, bis wieder die Kapazität erreicht ist. Teilnehmer, die nur über die Ansicht zu sehen sind, werden nicht automatisch zur Haupt besprechung heraufgestuft und können derzeit nicht manuell zur Haupt besprechung heraufgestuft werden.

Wenn die Rollen für Stellgärte/Teilnehmer nicht festgelegt wurden, werden die Räume in der Hauptsitzung nach dem "First Come, First-Served"-Basis ausgefüllt. Sobald die Besprechungskapazität erreicht ist, nehmen alle anderen Benutzer mit einer 6-6-n-Ansicht teil.

## <a name="impact-to-meeting-presenters"></a>Auswirkungen auf Besprechungs- Presenter

Wir reservieren in der normalen Besprechung Platz für Benutzer, die in den Besprechungsoptionen explizit als Helfer angegeben werden. Wenn ein Presenter die Besprechung verlässt und später erneut an der Besprechung teilt, wird er als Moderator in die Besprechung eingeladen.

Einschränkungen für Besprechungs presenter sind:

- Sie haben keine Informationen zu dem Nur-Anzeigen-Teilnehmer. E-Discovery wird für Nur-Ansicht-Teilnehmer nicht unterstützt.
- Die Benutzer können die Nur-Ansicht-Teilnehmer nicht sehen.
- Sie können einen Nur-Ansicht-Teilnehmer nicht aus der Besprechung entfernen.

> [!Note]
> Die Teilnehmeranzahl gibt nur die Personen in der Besprechung und nicht die Personen im Überlaufraum wieder. Daher können Moderatoren nicht die genaue Anzahl der Personen in der 2-Ansicht-Erfahrung erhalten.

## <a name="experience-for-view-only-attendees"></a>Benutzererfahrung für Nur-Anzeigen-Teilnehmer

Die 1-n-Ansicht von Teams ermöglicht Teilnehmern:

- Hören Sie den Teilnehmern an der Haupt-Teams-Besprechung zu.
- Sehen Sie sich den Videofeed für den aktiven Sprecher an (wenn der aktive Sprecher Video frei gibt).
- Anzeigen von geteilten Inhalten mithilfe der Desktopfunktion "Freigeben".

Die folgenden Optionen können von den Teilnehmern, die nur die Ansicht verwenden, in Besprechungen nicht angezeigt werden:

- Nehmen Sie an der Besprechung teil, wenn der Teilnehmer nicht über die Berechtigung zum Umgehen des Wartebereichs basierend auf festgelegten Lobbyrichtlinien oder Optionen verfügt.
- Nehmen Sie über Audiokonferenzen am Überlaufraum teil.
- Nehmen Sie über das Microsoft Teams Room System oder über Cloud Video Interop (CVI)-Dienste am Überlaufraum teil.
- Nehmen Sie über die mobile Teams -Android-App am Überlaufraum teil.
- Geben Sie ihr Audio oder Videosignal weiter.
- Sehen Sie den Besprechungschat an, oder nehmen Sie daran teil.
- Sehen Sie sich den Videofeed der Besprechungsteilnehmer an, es sei denn, der Teilnehmer ist der aktive Sprecher.
- Anzeigen von PowerPoint-Dateien, die mithilfe der nativen Freigabefunktion von PowerPoint oder einzelner Anwendungsfreigaben freigegeben wurden (andere als Desktopfreigaben).

## <a name="view-only-feature-limitations"></a>Einschränkungen bei N-2-Features

- Teilnehmern, die nur die Ansicht haben, werden immer Liveuntertitel angezeigt, unabhängig von der Einstellung für Liveuntertitel für diese Besprechung. Zurzeit werden nur englische Beschriftungen unterstützt.
- Teilnehmer, die nur anzeigen können, werden von der Streamingtechnologie unterstützt.
- Nur anzeigende Teilnehmer werden nicht in den Anwesenheitsbericht aufgenommen.
- Teilnehmer, die nur die Ansicht haben, haben nur eine Videoerfahrung. Sie können entweder den aktiven Lautsprecher oder den freigegebenen Inhalt sehen, aber nicht beides.
- Das Layout des Modus "Katalog",  **"Großer Katalog"** oder "Zusammen", das nur für die Anzeige verfügbar ist, wird derzeit nicht unterstützt.   
- Nur anzeigende Teilnehmer haben nicht dieselbe Latenz wie ein normaler Teilnehmer. <sup>1</sup>

  <sup>1</sup> Nur anzeigende Teilnehmer erhalten eine Video- und Audioverzögerung von 30 Sekunden in der Besprechung.  

## <a name="related-topics"></a>Verwandte Themen

- [Erweitertes Kommunikations-Add-On für Teams](teams-add-on-licensing/advanced-communications.md)
- [Grenzwerte und -Daten für Teams](limits-specifications-teams.md)
