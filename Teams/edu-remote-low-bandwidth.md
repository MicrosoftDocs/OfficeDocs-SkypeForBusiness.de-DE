---
title: Problembehandlung bei Szenarien mit geringer Bandbreite für Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Erhalten Sie Hilfe bei Besprechungs- und Videoproblemen im Zusammenhang mit Problemen mit geringer Bandbreite in Teams. Unabhängig davon, ob Sie ein Elternteil, ein Dozent oder ein IT-Admin sind, haben Sie Optionen, um die Erfahrung mit Teams zu verbessern.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426812"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>Problembehandlung bei Szenarien mit geringer Bandbreite für Teams

In diesem Artikel erhalten IT-Administratoren die bewährten Methoden im Umgang mit Problemen mit geringer Bandbreite in Teams.

Zahlreiche Netzwerkelemente können sich auf die Leistung bei der Arbeit mit Microsoft Teams auswirken.

- Low-Speed-Internetverbindung für die Schule.
- Low-Speed-Internetverbindung für einen oder mehrere Kursteilnehmer.
- Tageszeiten, zu denen die Bandbreite aufgrund der Netzwerkauslastung in einem bestimmten Gebiet gering ist.
- Ausfälle, die nicht lokal an der Schule oder den Schülern/Studenten vorgenommen wurden, wirken sich jedoch auf die Leistung aus.
- Hardwareprobleme, die Probleme mit geringer Bandbreite verursachen.

> [!IMPORTANT]
> Lesen Sie [, wie Microsoft Teams Arbeitsspeicher](teams-memory-usage-perf.md) für Ressourceneinschränkungen auf Geräten verwendet.
>
>Anleitungen zum Teams-Netzwerk finden [Sie unter Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>Beheben von Problemen mit geringer Bandbreite für IT-Administratoren

Einige Probleme können nur mit einem eingeschränkten Fokus auf der Ebene einzelner Benutzer behoben werden.

Wenn Bandbreitenprobleme für viele Benutzer auftreten oder wenn Aktionen auf Benutzerebene nicht hilfreich waren, ist die schulweite Aktion der nächste Schritt.

> [!NOTE]
> Sie können auch den [Leitfaden zur Überprüfung der Qualität der Erfahrung](quality-of-experience-review-guide.md) lesen. Es ist nicht EDU-spezifisch, verfügt aber über wertvolle Informationen.

### <a name="meetings-and-video"></a>Besprechungen und Video

Berücksichtigen Sie die nachstehenden Aktionen, wenn Sie mit Besprechungsproblemen im Zusammenhang mit geringer Netzwerkbandbreite umgehen.

#### <a name="meeting-video-policies"></a>Richtlinien für Besprechungsvideos

Teams skaliert die Besprechungsqualität automatisch auf die erkannte Bandbreite eines Benutzers. Sie können jedoch weitere Einschränkungen festlegen, um die Bandbreite zu erhalten.

Einige Einschränkungen, die Sie über eine Richtlinie festlegen können, sind:

- Deaktivieren Sie das Video vollständig, damit niemand Video verwenden kann.
- Beschränken der Medienbitrate, die pro Benutzer festgelegt wird.

Weitere Richtlinien, die Sie für Besprechungen und Video festlegen sollten, finden Sie [in den Besprechungsrichtlinieneinstellungen in Teams: Audio und Video](meeting-policies-audio-and-video.md).

#### <a name="screen-sharing-policies"></a>Bildschirmfreigaberichtlinien

In Teams können Benutzer ihren gesamten Bildschirm oder einzelne Fenster freigeben.

Die Freigabe eines gesamten Bildschirms verbraucht mehr Bandbreite als nur die Freigabe eines Fensters.

- Einschränken der Freigabe des gesamten Bildschirms durch Benutzer über eine Richtlinie.
- Weisen Sie Lehrkräfte an, nur Anwendungen und nicht den gesamten Bildschirm freizugeben.

Erfahren Sie mehr über Bildschirmfreigaberichtlinien in den [Besprechungsrichtlinieneinstellungen in Teams: Audio und Video](meeting-policies-audio-and-video.md).

#### <a name="dial-in-number-for-meetings"></a>Einwahlnummer für Besprechungen

Es kann für einige Kursteilnehmer einfacher sein, sich in Kurssitzungen einzuwählen.

- Stellen Sie als Alternative zur Teilnahme an einer Videobesprechung eine Einwahlnummer für Teams-Besprechungen bereit.

Weitere Informationen finden Sie unter [Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Szenarien mit geringer Bandbreite für Lehrkräfte

Lehrkräfte bei der Behandlung von Bandbreitenproblemen zu haben, ist in den folgenden Situationen möglicherweise eine bessere Wahl als IT-Maßnahmen:

- Das Problem ist intermittierend.
- Es gibt eine bestimmte Tageszeit, zu der Sie davon ausgehen können, dass es ein Problem gibt.

Informationen zu den Schritten, die ein Dozent ausführen kann, um Bandbreitenprobleme zu beheben, finden [Sie unter Verwenden von Teams für Schularbeit, wenn die Bandbreite gering ist](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Szenarien mit geringer Bandbreite für Eltern oder Schüler/Studenten

Manchmal liegt das Bandbreitenproblem auf der Seite eines Schülers.

- Ihr Zuhause hat möglicherweise keinen Zugriff auf hohe Bandbreite.
- Möglicherweise verbrauchen viele Personen in ihrem unmittelbaren Bereich auch Bandbreite.
- Möglicherweise gibt es internetinterne Instabilität.

Wir haben anleitungen in unserem [Use Teams for school work zusammengestellt, wenn die Bandbreite](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) für Eltern und Schüler gering ist.
