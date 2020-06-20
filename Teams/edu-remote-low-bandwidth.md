---
title: Microsoft Teams für Bildungseinrichtungen – Anleitung zur geringen Bandbreite
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams für Bildungseinrichtungen – Artikel zur Unterstützung von Besprechungs- und Videoproblemen in Verbindung mit geringer Bandbreite. Ganz gleich, ob Sie Eltern, Lehrkraft oder ITAdmin sind, Sie haben die Möglichkeit, die Erfahrung mit Teams zu verbessern.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034075"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Hilfe zu Situationen mit geringer Bandbreite für Teams für Bildungseinrichtungen

Bei der Arbeit mit Microsoft-Teams gibt es viele Netzwerkelemente, die sich auf die Leistung auswirken können, und eine niedrige Bandbreite gehört zu den Situationen, die sich völlig unkontrollierbar anfühlen können. Berücksichtigen Sie dabei Folgendes:

- Eine langsame Internetverbindung für die Schule.
- Eine langsame Internetverbindung für einen oder mehrere Schüler/Studenten.
- Tageszeiten zu denen die Bandbreite aufgrund der Netzwerkauslastung in einem bestimmten Gebiet gering ist.
- Zeiten mit geringer Bandbreite aufgrund von Ausfällen, die weder in der Schule noch bei Schülern/Studenten vor Ort sind, die aber dennoch die Leistung beeinträchtigen.
- Probleme, die nicht mit der Bandbreite zusammenhängen (z. B. Probleme mit der Hardware), die mit Problemen mit geringer Bandbreite verwechselt werden können.

In diesem Artikel finden Sie bewährte Methoden für eine Vielzahl von Teams-Aktivitäten, wenn Sie mit einem Problem mit geringer Bandbreite konfrontiert sind.

> [!IMPORTANT]
> Hier finden Sie Informationen über die [Verwendung des Arbeitsspeichers durch Microsoft Teams](teams-memory-usage-perf.md), da es zusätzlich zu Problemen mit geringer Bandbreite auch zu Problemen mit den Ressourcen auf Ihrem Gerät kommen kann. Hinweise zum Thema Netzwerk in Verbindung mit Microsoft Teams finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>Beheben von Problemen mit geringer Bandbreite für ITAdmins

Wichtig ist, dass Sie als ITAdmin daran denken, dass Sie zwar Lösungen für weitreichende Probleme mit geringer Bandbreite zur Verfügung haben, die Probleme eventuell schnell beheben können, jeden Fall aber auch sorgfältig prüfen sollten, da einige Probleme möglicherweise mit einem engeren Fokus auf die Lehrkraft oder sogar auf der Ebene der Schüler/Studenten/Eltern behoben werden können.

Kurz gesagt: Wenn das Problem mit geringer Bandbreite bei einer großen Anzahl von Schülern/Studenten auftritt, ist das Eingreifen eines ITAdmins sinnvoll und es ist auch sinnvoll, wenn die auf der Ebene der Schüler/Studenten/Lehrkräfte ergriffenen Maßnahmen das Problem nicht behoben haben.

> [!NOTE]
> Wenn Sie ausreichend Zeit zur Verfügung haben, ist der [Leitfaden zur Überprüfung der Erlebnisqualität](quality-of-experience-review-guide.md) eine lohnende Lektüre (er ist nicht konkret auf die Version für Bildungseinrichtungen abgestimmt, aber er bietet trotzdem wertvolle Informationen). So können erfahrene ITAdmins die Erfahrung für ihre Lehrkräfte und Schüler/Studenten gründlicher studieren.

### <a name="meetings-and-video"></a>Besprechungen und Video

Ein primärer Schwerpunkt bei Problemen mit geringer Bandbreite sind Besprechungen und insbesondere Videos bei Besprechungen. Im Folgenden sind einige der Maßnahmen aufgeführt, die ein ITAdmin in Betracht ziehen sollte, wenn er sich mit Problemen befasst, die von Schülern/Studenten oder Lehrkräften gemeldet werden, um die beste Erfahrung bei Besprechungen im Bildungsbereich zu erzielen.

#### <a name="meeting-policies"></a>Besprechungsrichtlinien

Im Hinblick auf Besprechungen sind bei Situationen mit geringer Bandbreite vor allem Videos betroffen. Glücklicherweise kann Teams nicht nur automatisch auf die erkannte Bandbreite skalieren, sondern Sie als ITAdmin haben auch Richtlinienoptionen, die Sie auf der Ebene der einzelnen Organisatoren und/oder Benutzer einstellen können, um für alle Beteiligten die bestmögliche Erfahrung mit der Bandbreite zu gewährleisten, die ihnen zu einem bestimmten Zeitpunkt zur Verfügung steht.

Einige Dinge, die Sie über Richtlinien festlegen können, sind:

- Video vollständig deaktivieren, sodass es niemand aktivieren kann.
- Medienbitrate (diese wird für jeden Benutzer festgelegt).

Wenn Sie mehr über Ihre Optionen erfahren und die Einzelheiten der Richtlinien, die Sie für Besprechungen und Videos festlegen müssten, durchgehen möchten, schauen Sie sich [Einstellungen zu Besprechungsrichtlinien in Teams: Audio und Video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) an, um detaillierte Informationen zum Verfahren zu erhalten.

#### <a name="screen-sharing-policies"></a>Bildschirmfreigaberichtlinien

Darüber hinaus kann es vorkommen, dass Lehrkräfte ihren gesamten Bildschirm für die Schüler/Studenten freigeben, obwohl die Freigabe auf eine ganz bestimmte Anwendung beschränkt sein sollte, die für die zu unterrichtende Lektion relevant ist. Dies kann ebenfalls über eine Richtlinie festgelegt werden, wenn dies wünschenswerter ist, als dass die Lehrkräfte diese Entscheidung individuell treffen müssen.

Einen guten Überblick darüber, was Sie tun können, um die Bildschirmfreigabe über Richtlinieneinstellungen einzuschränken, finden Sie unter [Einstellungen für Besprechungsrichtlinien in Teams: Bildschirmfreigabe](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).

#### <a name="dial-in-number-for-meetings"></a>Einwahlnummer für Besprechungen

Es kann für einige Schüler/Studenten einfacher sein, zu versuchen, sich in einige Unterrichtssitzungen einzuwählen. Sie können eine Einwahlnummer für Teams-Besprechungen angeben, sodass Schüler/Studenten mit Problemen als Alternative zur Teilnahme an einer Videobesprechung stattdessen anrufen können.

Weitere Informationen hierzu finden Sie unter [Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Szenarien mit geringer Bandbreite für Lehrkräfte

Lehrkräfte sollten sich in der Lage fühlen, Maßnahmen zur Lösung von Problemen mit geringer Bandbreite zu ergreifen. In den folgenden Situationen kann dies eine bessere Wahl sein als das Eingreifen eines ITAdmins:

- Wenn das Problem zeitweilig oder relativ vorübergehend ist.
- Wenn es eine bestimmte Tageszeit gibt, zu der man mit einem Problem rechnen kann, oder wenn der Zeitraum mit geringer Bandbreite einigermaßen vorhersehbar ist.

In diesen Fällen können Sie einige Maßnahmen ergreifen.

Weitere Informationen finden Sie unter [Verwendung von Teams für Schularbeiten bei geringer Bandbreite](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Szenarien mit geringer Bandbreite für Eltern oder Schüler/Studenten

Es gibt auch Situationen, und Sie sollten diese im Voraus mit Ihren Lehrkräften besprechen, in denen das Bandbreitenproblem auf der Seite der Schüler/Studenten liegen kann (z. B. kann es vorkommen, dass ein Großteil der Schüler/Studenten die Video-Lektionen ohne Probleme ansehen kann, aber eine kleine Anzahl von Schülern/Studenten dabei Schwierigkeiten hat).

Es ist nicht realistisch zu erwarten, dass viele Eltern in der Lage sind, diese Probleme zu beheben, und Probleme mit niedriger Bandbreite können außerhalb der Kontrolle eines Schülers/Studenten oder Elternteils liegen (ihr Zuhause hat vielleicht keinen Zugang zu hoher Bandbreite, sie haben möglicherweise viele Menschen in ihrer unmittelbaren Umgebung, die die Bandbreite verbrauchen und somit beeinflussen, was sie tun können, die Internetverbindung könnte instabil sein usw.).

Wir haben in unserem Artikel [Verwendung von Teams für Schularbeiten bei geringer Bandbreite](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) einige Hinweise für Eltern und Schüler/Studenten zusammengestellt. Sie können diese Empfehlungen durchgehen und ausprobieren, wenn Sie Probleme haben.
