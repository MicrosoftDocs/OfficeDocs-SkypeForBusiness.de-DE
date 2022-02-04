---
title: Microsoft Teams für Bildungseinrichtungen – Anleitung zur Problemlösung aufgrund geringer Bandbreite
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams für Bildungseinrichtungen – Artikel zur Unterstützung bei Besprechungs- und Videoproblemen in Verbindung mit geringer Bandbreite. Ganz gleich, ob Sie Elternteil, Lehrkraft oder IT-Administrator sind, Sie haben die Möglichkeit, die Erfahrung mit Microsoft Teams zu verbessern.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: f95cb60f28a81c2feb10fb01c6088fa0799e119c
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2022
ms.locfileid: "62362971"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Microsoft Teams für Bildungseinrichtungen – Hilfe bei Situationen mit geringer Bandbreite

Es gibt viele Netzwerkelemente, die sich im Hinblick auf die Nutzung von Microsoft Teams auf die Leistung auswirken können. Eine geringe Bandbreite gehört zu den Situationen, die sich völlig unkontrollierbar anfühlen können. Berücksichtigen Sie die folgenden Situationen:

- Eine langsame Internetverbindung für die Schule.
- Eine langsame Internetverbindung für einen oder mehrere Schüler/Studenten.
- Tageszeiten, zu denen die Bandbreite aufgrund der Netzwerkauslastung in einem bestimmten Gebiet gering ist.
- Zeiten mit geringer Bandbreite aufgrund von Ausfällen, die weder in der Schule noch bei Schülern/Studenten vor Ort auftreten, die aber dennoch die Leistung beeinträchtigen.
- Probleme, die nicht mit der Bandbreite zusammenhängen (z. B. Probleme mit der Hardware), die mit Problemen mit geringer Bandbreite verwechselt werden können.

In diesem Artikel werden bewährte Methoden für eine Vielzahl von Microsoft Teams-Aktivitäten erläutert, die Sie bei Problemen mit geringer Bandbreite anwenden können.

> [!IMPORTANT]
> Hier finden Sie Informationen über die [Verwendung des Arbeitsspeichers durch Microsoft Teams](teams-memory-usage-perf.md), da es zusätzlich zu Problemen mit geringer Bandbreite auch zu Problemen mit den Ressourcen auf Ihrem Gerät kommen kann. Hinweise zum Thema Netzwerk in Verbindung mit Microsoft Teams finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-admins"></a>Beheben von Problemen aufgrund geringer Bandbreite für Administratoren

Der wichtigste Punkt, an den Sie als IT-Administrator denken sollten: Obwohl Sie über Lösungen für verbreitete Probleme aufgrund geringer Bandbreite verfügen, die Probleme schnell beheben, sollten Lösungen sorgfältig bedacht werden. Einige Probleme können möglicherweise mit einem stärker eingeengten Schwerpunkt auf der Ebene der Lehrkräfte oder sogar der Schüler/Studenten/Eltern behoben werden.

Kurz gesagt: Wenn das durch geringe Bandbreite bedingte Problem bei einer großen Anzahl von Schülern/Studenten auftritt, ist das Eingreifen eines IT-Admins sinnvoll, und ebenso sinnvoll ist es, wenn das Problem durch auf der Ebene der Schüler/Studenten/Lehrkräfte ergriffene Maßnahmen nicht behoben werden konnte.

> [!NOTE]
> Wenn Sie ausreichend Zeit zur Verfügung haben, ist der [Leitfaden zur Überprüfung der Erlebnisqualität](quality-of-experience-review-guide.md) eine lohnende Lektüre (er ist nicht konkret auf die Version für Bildungseinrichtungen abgestimmt, aber er bietet trotzdem wertvolle Informationen). Mithilfe dieses Leitfadens können erfahrene IT-Administratoren die Benutzererfahrung von Lehrkräften und Schülern/Studenten eingehender studieren.

### <a name="meetings-and-video"></a>Besprechungen und Video

Ein primärer Schwerpunkt bei Problemen aufgrund geringer Bandbreite sind Besprechungen und insbesondere Videos im Rahmen von Besprechungen. Im Folgenden sind Maßnahmen aufgeführt, die ein IT-Administrator in Betracht ziehen sollte, wenn er sich mit Problemen befasst, die von Schülern/Studenten oder Lehrkräften gemeldet werden, um die bestmögliche Benutzererfahrung bei Besprechungen im Bildungsbereich zu erzielen.

#### <a name="meeting-policies"></a>Besprechungsrichtlinien

Im Hinblick auf Besprechungen sind bei Situationen mit geringer Bandbreite vor allem Videos betroffen. Glücklicherweise kann Microsoft Teams nicht nur automatisch auf die erkannte Bandbreite skalieren, sondern Sie als IT-Administrator haben auch Richtlinienoptionen, die Sie auf der Ebene der einzelnen Organisatoren und/oder Benutzer einstellen können. Über diese Optionen können Sie für alle Beteiligten die bestmögliche Benutzererfahrung im Hinblick auf die Bandbreite erzielen, die zu einem bestimmten Zeitpunkt zur Verfügung steht.

Einige Dinge, die Sie über Richtlinien festlegen können, sind:

- Video vollständig deaktivieren, sodass es niemand aktivieren kann.
- Medienbitrate (diese wird für jeden Benutzer festgelegt).

Wenn Sie mehr über Ihre Optionen und dazu, welche Richtlinien Sie für Besprechungen und Videos einrichten sollten, erfahren möchten, schauen Sie sich [Einstellungen für Besprechungsrichtlinien in Microsoft Teams: Audio und Video](meeting-policies-audio-and-video.md) an.

#### <a name="screen-sharing-policies"></a>Bildschirmfreigaberichtlinien

Darüber hinaus kann es vorkommen, dass Lehrkräfte ihren gesamten Bildschirm für die Schüler/Studenten freigeben, obwohl die Freigabe auf eine ganz bestimmte Anwendung beschränkt sein sollte, die für die zu unterrichtende Lektion relevant ist. Dies kann ebenfalls über eine Richtlinie festgelegt werden, wenn dies wünschenswerter ist, als dass die Lehrkräfte diese Entscheidung individuell treffen müssen.

Einen guten Überblick darüber, was Sie tun können, um die Bildschirmfreigabe über Richtlinieneinstellungen einzuschränken, finden Sie unter [Einstellungen für Besprechungsrichtlinien in Microsoft Teams: Audio und Video](meeting-policies-audio-and-video.md).

#### <a name="dial-in-number-for-meetings"></a>Einwahlnummer für Besprechungen

Es kann für einige Schüler/Studenten einfacher sein, zu versuchen, sich in einige Unterrichtssitzungen einzuwählen. Sie können eine Einwahlnummer für Teams-Besprechungen angeben, sodass Schüler/Studenten mit Problemen als Alternative zur Teilnahme an einer Videobesprechung stattdessen anrufen können.

Weitere Informationen hierzu finden Sie unter [Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Szenarien mit geringer Bandbreite für Lehrkräfte

Lehrkräfte sollten sich in der Lage fühlen, Maßnahmen zur Lösung von Problemen aufgrund geringer Bandbreite zu ergreifen. In den folgenden Situationen kann dies eine bessere Wahl sein als das Eingreifen eines IT-Administrators:

- Wenn das Problem zeitweilig oder relativ vorübergehend ist.
- Wenn es eine bestimmte Tageszeit gibt, zu der man mit einem Problem rechnen kann, oder wenn der Zeitraum mit geringer Bandbreite einigermaßen vorhersehbar ist.

In diesen Fällen können Sie einige Maßnahmen ergreifen.

Weitere Informationen finden Sie unter [Verwendung von Teams für Schularbeiten bei geringer Bandbreite](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Szenarien mit geringer Bandbreite für Eltern oder Schüler/Studenten

Es gibt auch Situationen, und Sie sollten diese im Voraus mit Ihren Lehrkräften besprechen, in denen das Bandbreitenproblem auf der Seite der Schüler/Studenten liegen kann (z. B. kann es vorkommen, dass ein Großteil der Schüler/Studenten die Video-Lektionen ohne Probleme ansehen kann, aber eine kleine Anzahl von Schülern/Studenten dabei Schwierigkeiten hat).

Es ist unrealistisch zu erwarten, dass viele Eltern in der Lage sind, solche Probleme zu lösen. Probleme aufgrund niedriger Bandbreite können außerhalb der Kontrolle eines Schülers/Studenten oder Elternteils liegen (ihr Zuhause hat vielleicht keinen Zugang zu hoher Bandbreite, in ihrer unmittelbaren Umgebung könnte es viele Menschen geben, die Bandbreite verbrauchen und somit beeinflussen, was sie tun können, die Internetverbindung könnte instabil sein usw.).

Wir haben in unserem Artikel [Verwendung von Teams für Schularbeiten bei geringer Bandbreite](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) einige Hinweise für Eltern und Schüler/Studenten zusammengestellt. Sie können diese Empfehlungen durchgehen und ausprobieren, wenn Sie Probleme haben.