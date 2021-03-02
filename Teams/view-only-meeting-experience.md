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
description: Erfahren Sie mehr über die Nur-Ansichts-Besprechungserfahrung von Teams für Administratoren, Presenter und Teilnehmer
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed7221192fdc3588856755b8be651065fdbf15ab
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397560"
---
# <a name="teams-view-only-meeting-experience"></a>Nur-Ansichts-Besprechungserfahrung in Teams

> [!Note]
> Die Besprechungserfahrung nur anzeigen wird Anfang März 2021 verfügbar sein. Dieses Feature wird am 1. März 2021 als Standardmäßiges AUS aktiviert. Sie müssen die Standardrichtlinie nach diesem Datum ändern, wenn das Feature standardmäßig EIN sein soll. Verwenden Sie PowerShell, um die Richtlinie zu `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled` aktivieren.

> [!Note]
> Wir haben die Ansichtserfahrung für 20.000 Teilnehmer vorübergehend erhöht, aber wir werden den Support am 30. Juni 2021 auf 10.000 Teilnehmer zurücksetzen.

Microsoft Teams ermöglicht bis zu 10.000 Teilnehmern die Teilnahme an einer Teams-Besprechung. Nachdem die Kapazität der Hauptsitzung erreicht wurde, nehmen weitere Teilnehmer mit einer Nur-Ansicht-Erfahrung teil.

Teilnehmer, die zuerst an der Besprechung teilnehmen, erhalten bis zur Kapazität der Besprechung die vollständige Teambesprechungserfahrung. Sie können Audio und Video freigeben, freigegebene Videos anzeigen und an Besprechungschats teilnehmen.

Teilnehmer, die teilnehmen, nachdem die Hauptkapazität der Besprechung erreicht wurde, haben eine Nur-Ansicht-Erfahrung.

Wir haben vollständigen Android- und iOS-Mobile-Support für einen Teilnehmer, der teilnehmen kann.

> [!Note]
> Der aktuelle Grenzwert für die Anzahl der Personen, die chatten und sich in eine Besprechung ein- und einrufen können, beträgt 300 im Ww und 250 in GCC, GCC High und DoD.

Die Ansichtserfahrung ist standardmäßig für jeden Organisator deaktiviert, der über E3/E5/A3/A5-SKU verfügt. Es ist keine weitere Konfiguration oder Einrichtung erforderlich.

## <a name="disable-teams-view-only-experience"></a>Deaktivieren der Ansichtserfahrung von Teams

Administratoren können die Ansichtserfahrung mit PowerShell deaktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In Zukunft können Administratoren auch die Ansichtserfahrung im Teams Admin Center deaktivieren.

## <a name="impact-to-users"></a>Auswirkungen für Benutzer

Die Benutzererfahrung hängt von mehreren Faktoren ab.

Wenn die Kapazität der Haupt besprechung erreicht wurde, kann ein Teilnehmer nicht an der Besprechung teilnehmen, wenn eine der folgenden Bedingungen zutrifft:

- Ein Administrator hat die Ansichtserfahrung von Teams deaktiviert.
- Der Teilnehmer verfügt nicht über die Berechtigung zum Umgehen des Wartebereichs.

Wenn die Kapazität der Hauptsitzung erreicht ist, sehen der Besprechungsorganisator und die Organisatorin ein Banner, das sie darüber informiert, dass die Besprechungskapazität erreicht wurde und dass neue Teilnehmer an einem Nur-Ansicht-Teilnehmer teilnehmen.

  ![der Teams-Client- und Bannersysage für Organisatoren und Organisatoren](media/chat-and-banner-message.png)

Wenn die Kapazität der Hauptbesprechung erreicht ist, werden die Besprechungsteilnehmer auf dem Bildschirm vor der Teilnahme darüber informiert, dass sie nur im Ansichtsmodus teilnehmen.

  ![der Bildschirm "Teams pre-join" und die Meldung für Teilnehmer, die ihnen mitteilt, dass sie im Nur-Ansicht-Modus teilnehmen werden](media/view-only-pre-join-screen.png)

Wenn Platz ist, wird ein Benutzer immer an der Haupt besprechung teilnehmen. Wenn die Haupt besprechung kapazität erreicht und ein oder mehrere Teilnehmer die Hauptsitzung verlassen, verfügt die Hauptsitzung über verfügbare Kapazität. Teilnehmer, die an der Besprechung teilnehmen (oder erneut teilnehmen), nehmen an der Hauptsitzung teil, bis sie die Kapazität wieder erreicht hat. Teilnehmer, die die Ansichtserfahrung haben, werden nicht automatisch zur Hauptsitzung heraufgestuft und können zurzeit nicht manuell zur Haupt besprechung heraufgestuft werden.

Wenn keine Rollen für Presenter/Teilnehmer festgelegt wurden, werden Die Leerzeichen in der Hauptsitzung nach dem Ersten Kommen und der erstgesenkten Basis ausgefüllt. Sobald die Besprechungskapazität erreicht ist, werden alle anderen Benutzer mit einer Ansichtserfahrung teilnehmen.

## <a name="impact-to-meeting-presenters"></a>Auswirkungen auf Besprechungs presenter

Zu den Einschränkungen für Besprechungs presenter gehören:

- Sie haben keine Informationen zum Nur-Ansicht-Teilnehmer. Wir unterstützen E-Discovery nicht für Nur-Ansicht-Teilnehmer.
- Die Benutzer können die Nur-Ansicht-Teilnehmer nicht sehen.
- Sie können einen Nur-Ansicht-Teilnehmer nicht aus der Besprechung entfernen.

> [!Note]
> Die Teilnehmeranzahl gibt nur die Personen in der Besprechung und nicht die Personen im Überlaufraum wieder. Daher können Presenter keine genaue Anzahl der Personen erhalten, die sich in der Ansichtserfahrung befindet.

## <a name="experience-for-view-only-attendees"></a>Benutzererfahrung für Nur-Ansicht-Teilnehmer

Die Nur-Ansichtserfahrung von Teams ermöglicht Teilnehmern:

- Hören Sie sich die Teilnehmer an der Haupt-Teams-Besprechung an.
- Sehen Sie sich den Videofeed für den aktiven Lautsprecher an (wenn der aktive Lautsprecher Video teilt).
- Anzeigen von Inhalten, die mithilfe der Desktopfunktion "Freigeben" freigegeben werden.

Der Nur-Ansicht-Teilnehmer kann in Besprechungen nicht die folgenden Optionen anzeigen:

- Nehmen Sie an der Besprechung teil, wenn der Teilnehmer nicht über die Berechtigung zum Umgehen des Wartebereichs basierend auf festgelegten Lobbyrichtlinien oder Optionen verfügt.
- Nehmen Sie über Audiokonferenzen am Überlaufraum teil.
- Nehmen Sie über das Microsoft Teams Room System oder über Cloud Video Interop (CVI)-Dienste am Überlaufraum teil.
- Teilen Sie ihre Audio- oder Videodaten.
- Sie können den Besprechungschat sehen oder daran teilnehmen.
- Sehen Sie sich den Videofeed der Besprechungsteilnehmer an, es sei denn, der Teilnehmer ist der aktive Sprecher.
- Weitere Informationen finden Sie unter PowerPoint-Dateien, die mit der systemeigenen PowerPoint-Freigabefunktion oder einzelnen Anwendungsfreigaben (mit anderen Als Desktopfreigaben) freigegeben werden.

## <a name="view-only-feature-limitations"></a>Einschränkungen für Nur-Ansicht-Features

- Nur-Ansichtsteilnehmer sehen immer Liveuntertitel, unabhängig von der Einstellung für die Liveuntertitel für diese Besprechung. Zurzeit werden nur englische Beschriftungen unterstützt.
- Nur-Ansicht-Teilnehmer werden von der Streamingtechnologie unterstützt.
- Nur anzeigende Teilnehmer werden nicht in den Anwesenheitsbericht aufgenommen.
- Nur-Ansichtsteilnehmer verfügen über eine einzelne Videoerfahrung. Sie können entweder den aktiven Lautsprecher oder den freigegebenen Inhalt sehen, aber nicht beides.
- Wir unterstützen derzeit keine Layouts im **Gallery-,** **Large Gallery-** oder **Together-Modus** für Nur-Ansicht-Teilnehmer.  
- Nur-Ansichtsteilnehmer haben nicht die gleiche Latenz wie normale Teilnehmer. <sup>1</sup>

  <sup>1</sup> Nur Anzeigende Teilnehmer werden bei einer Video- und Audioverzögerung von 30 Sekunden in der Besprechung angezeigt.  

## <a name="related-topics"></a>Verwandte Themen

- [Advanced Communications Add-On für Teams](teams-add-on-licensing/advanced-communications.md)
- [Grenzwerte und -Daten für Teams](limits-specifications-teams.md)
