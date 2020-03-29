---
title: Microsoft Teams für Bildungseinrichtungen – Anleitung zur geringen Bandbreite
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams für Bildungseinrichtungen – Artikel zur Unterstützung von Besprechungs- und Videoproblemen in Verbindung mit geringer Bandbreite. Ganz gleich, ob Sie Eltern, Pädagoge oder ITAdmin sind, Sie haben die Möglichkeit, die Erfahrung mit Teams zu verbessern.
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
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Hilfe zu Situationen mit geringer Bandbreite für Teams für das Bildungswesen

Bei der Arbeit mit Microsoft-Teams gibt es viele Netzwerkelemente, die sich auf die Leistung auswirken können, und eine niedrige Bandbreite ist eine der Situationen, die sich völlig unkontrollierbar anfühlen kann. Berücksichtigen Sie dabei Folgendes:

- Eine langsame Internetverbindung für die Schule.
- Eine langsame Internetverbindung für die einen oder mehrere Schüler.
- Zeiten des Tages, in denen die Bandbreite aufgrund einer Netzwerknutzung in einem bestimmten Gebiet gering ist.
- Zeiten mit geringer Bandbreite aufgrund von Ausfällen, die weder in der Schule noch bei Schülern vor Ort sind, die aber dennoch die Leistung beeinträchtigen.
- Probleme, die nicht mit der Bandbreite zusammenhängen (z. B. Probleme mit der Hardware), die mit Problemen mit niedriger Bandbreite verwechselt werden können.

In diesem Artikel finden Sie bewährte Methoden für eine Vielzahl von Teams-Aktivitäten, wenn Sie mit einem Problem mit geringer Bandbreite konfrontiert sind.

> [!IMPORTANT]
> Hier finden Sie Informationen über die [Verwendung des Arbeitsspeichers durch Microsoft Teams](teams-memory-usage-perf.md)verwendet, da es zusätzlich zu Problemen mit geringer Bandbreite möglicherweise zu Problemen mit den Ressourcen auf Ihrem Gerät kommt. Wenn Sie Hinweise zum Thema Netzwerk in Verbindung mit Microsoft Teams bräuchten, schauen Sie sich [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md) an.

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>Beheben von Problemen mit geringer Bandbreite für ITAdmins

Wichtig ist, dass Sie sich als ITAdmin daran erinnern, dass Sie Lösungen für Probleme mit geringer Bandbreite, die weit verbreitet sind und sich schnell lösen lassen, auch sorgfältig prüfen sollten, da einige Probleme möglicherweise mit einem engeren Fokus auf den Lehrer oder sogar auf die Ebene von Schülern/Eltern behoben werden können.

Kurz gesagt: Wenn das Problem mit geringer Bandbreite für eine große Gruppe von Schülern auftritt, ist das Handeln als ITAdmin sinnvoll und es ist auch sinnvoll, wenn die auf der Ebene "Schüler/Lehrer" getroffenen Aktionen nicht hilfreich waren.

> [!NOTE]
> Wenn Sie ausreichen Zeit haben, ist der [Leitfaden zur Überprüfung der Erlebnisqualität](quality-of-experience-review-guide.md) eine lohnende Lektüre (er ist nicht konkret auf die Version für Bildungseinrichtungen abgestimmt, aber er bietet trotzdem wertvolle Informationen). So können erfahrene ITAdmins die Erfahrung für ihre Lehrer und Schüler gründlicher studieren.

### <a name="meetings-and-video"></a>Besprechungen und Video

Ein primärer Schwerpunkt bei Problemen mit geringer Bandbreite sind Besprechungen und speziell Video in Besprechungen. Im Folgenden sind einige der Maßnahmen aufgeführt, die ein ITAdmin in Betracht ziehen sollte, wenn er sich mit Problemen befasst, die von Studenten oder Pädagogen gemeldet werden, um die beste Erfahrung mit Treffen in einem Bildungsumfeld zu erzielen.

#### <a name="meeting-policies"></a>Besprechungsrichtlinien

Im Hinblick auf Besprechungen ist einer der am meisten betroffenen Bereiche bei niedrigen Bandbreiten mit Videos verbunden. Glücklicherweise kann Teams nicht nur automatisch auf die erkannte Bandbreite skalieren, sondern Sie als ITAdmin haben auch Richtlinienoptionen, die Sie auf der Ebene der einzelnen Organisatoren und/oder Benutzer einstellen können, um für alle Beteiligten die beste Erfahrung im Hinblick auf die Bandbreite, mit der sie zu einem bestimmten Zeitpunkt arbeiten müssen, zu gewährleisten.

Einige der Einstellungen, die Sie über die Richtlinie vornehmen können, sind:

- Video wird vollständig deaktiviert, sodass es niemand aktivieren kann.
- Media-Bitrate (diese wird pro Benutzer festgelegt).

Wenn Sie mehr über Ihre Optionen erfahren und die Einzelheiten der Richtlinien, die Sie für Besprechungen und Videos festlegen müssten, durchlaufen möchten, schauen Sie sich [Einstellungen zu Besprechungsrichtlinien in Teams: Audio und Video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) an, um detaillierte Informationen zum Verfahren zu erhalten.

#### <a name="screen-sharing-policies"></a>Bildschirmfreigaberichtlinien

In anderen Fällen kann es vorkommen, dass Pädagogen ihren gesamten Bildschirm für die Schüler freigeben, wobei die Freigabe auf eine Anwendung beschränkt sein sollte, die für die zu unterrichtende Lektion relevant ist. Dies kann auch über eine Richtlinie festgelegt werden, wenn dies wünschenswerter ist, als wenn die Pädagogen diese Entscheidung individuell treffen müssen.

Einen guten Überblick darauf, was Sie tun können, um die Bildschirmfreigabe über Richtlinieneinstellungen zu begrenzen, gewinnen Sie unter [Einstellungen für Besprechungsrichtlinien in Teams: Bildschirmfreigabe](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).

#### <a name="dial-in-number-for-meetings"></a>Einwahlnummer für Besprechungen

Es kann für einige Schüler einfacher sein, zu versuchen, sich in einige Unterrichtssitzungen einzuwählen. Sie können eine Einwahlnummer für Teams-Besprechungen angeben, so dass Studenten mit Problemen als Alternative zur Teilnahme an einer Videobesprechung anrufen können.

Weitere Informationen hierzu finden Sie unter [Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Szenarien mit geringer Bandbreite als Pädagoge

Pädagogen sollten sich befähigt fühlen, Maßnahmen zur Lösung von Problemen mit geringer Bandbreite zu ergreifen, und dies kann in den folgenden Situationen eine bessere Wahl als die Maßnahmen der ITAdmin sein:

- Wenn das Problem zeitweilig oder relativ vorübergehend ist.
- Wenn es eine bestimmte Tageszeit gibt, in der man mit einem Problem rechnen kann, oder wenn der Zeitraum mit geringer Bandbreite eine gewisse Vorhersehbarkeit hat.

In diesen Fällen können Sie einige Aktionen ausführen.

Weitere Informationen finden Sie unter [Teams für Schularbeiten verwenden, wenn die Bandbreite gering ist](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Szenarien mit geringer Bandbreite für Eltern und Schüler

Es gibt auch Situationen, und Sie sollten diese proaktiv mit Ihren Lehrkräften besprechen, in denen das Bandbreitenproblem auf der Seite der Schüler liegen kann (z. B. kann eine große Anzahl von Schülern die Video-Lektionen ohne Probleme ansehen, aber eine kleine Anzahl von Schülern hat Schwierigkeiten).

Es ist nicht zumutbar, von vielen Eltern zu erwarten, dass sie in der Lage sind, diese Probleme zu beheben, und Probleme mit niedriger Bandbreite können außerhalb der Kontrolle eines Schülers oder Elternteils liegen (ihr Zuhause hat vielleicht keinen Zugang zu hoher Bandbreite, sie haben möglicherweise viele Menschen in ihrer unmittelbaren Umgebung, die die Bandbreite verbrauchen und beeinflussen, was sie tun können, es kann eine Instabilität des Internets vorliegen usw.).

Wir haben in unserem Artikel [Teams für die Schularbeiten bei geringer Bandbreite nutzen](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) für Eltern und Schüler einige Hinweise zur Verfügung gestellt. Sie können diese Empfehlungen durchgehen und ausprobieren, wenn Sie Probleme haben.
