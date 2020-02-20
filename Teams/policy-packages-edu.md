---
title: Microsoft Teams-Richtlinienpakete für EDU-Administratoren
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Richtlinien Pakete in Microsoft Teams verwenden und verwalten.
ms.openlocfilehash: d4a11952ea65a5380abb3ba284e13bab6d5d4e90
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155047"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>Microsoft Teams-Richtlinienpakete für EDU-Administratoren

Ein Richtlinienpaket in Microsoft Teams sammelt vordefinierte Richtlinien und Richtlinieneinstellungen, die Sie Benutzern mit ähnlichen Rollen in Ihrer Institution zuweisen können. Richtlinien Pakete vereinfachen, rationalisieren und unterstützen die Konsistenz beim Verwalten von Richtlinien. In der Regel weisen Sie jedem Benutzer ein Richtlinienpaket zu, und bei Bedarf werden die Richtlinien in jedem Paket entsprechend den Anforderungen dieser Benutzergruppe neu definiert. Wenn Sie die Einstellungen in einem Paket aktualisieren, werden alle Benutzer, die diesem Paket zugewiesen sind, als Massenaktualisierung geändert.

Bildungseinrichtungen im Allgemeinen verfügen über viele Benutzertypen mit eindeutigen Anforderungen, die sich teilweise nach Alter und Reife der Kursteilnehmer richten. So können Sie beispielsweise Pädagogen und Mitarbeitern vollen Zugriff auf Microsoft Teams gewähren, aber die Microsoft Teams-Funktionen für Schüler einschränken, um eine sichere und zielgerichtete Lernumgebung zu fördern. Sie können Richtlinien Pakete verwenden, um Einstellungen basierend auf den Anforderungen unterschiedlicher Kohorten in ihrer Schulgemeinde anzupassen.

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinien Paketen können Sie Microsoft Teams-Funktionen steuern, die Microsoft Teams für bestimmte Gruppen von Personen in Ihrer Organisation verwenden oder einschränken. Jedes Richtlinienpaket ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen.

Richtlinien Pakete definieren Richtlinien für:
- Messaging
- Besprechungen
- App-Setup
- Anrufe
- Liveereignisse

Microsoft Teams umfasst derzeit die folgenden Richtlinien Pakete:

|Im Microsoft Teams Admin Center aufgeführter Paket Name |Am besten geeignet für  |Beschreibung |
|:--- |:--- |:--- |
|Education_Teacher| Lehrkräfte und Mitarbeiter| Verwenden Sie diesen Richtliniensatz und die Richtlinieneinstellungen, um Pädagogen und Mitarbeitern in Ihrer Organisation vollen Zugriff auf Chats, Anrufe und Besprechungen über Microsoft Teams zu gewähren. |
|Education_PrimaryStudent | Grundschule im Alter von Schülern  | Jüngere, Grundschüler/Studenten in ihrer Einrichtung benötigen möglicherweise mehr Einschränkungen innerhalb von Microsoft Teams. Verwenden Sie diesen Richtliniensatz und die Richtlinieneinstellungen, um Funktionen wie das Erstellen und Verwalten von Besprechungen, die Chat Verwaltung und private Anrufe zu begrenzen. |
|Education_SecondaryStudent| Schüler im Alter von sekundären Schulen | Schüler von sekundären Schulen in ihrer Einrichtung benötigen möglicherweise weitere Einschränkungen innerhalb von Microsoft Teams. Verwenden Sie diesen Richtliniensatz und die Richtlinieneinstellungen, um Funktionen wie das Erstellen und Verwalten von Besprechungen, die Chat Verwaltung und private Anrufe zu begrenzen. |
|Education_HigherEducationStudent | Hochschulstudenten | Hochschulstudenten in Ihrer Intuition benötigen möglicherweise weniger Einschränkungen als jüngere Schüler, aber einige Einschränkungen werden möglicherweise empfohlen. Sie können diesen Richtliniensatz und die Richtlinieneinstellungen verwenden, um den Zugriff auf Chats, Anrufe und Besprechungen in Ihrer Organisation zu gewähren, aber die Verwendung von Microsoft Teams mit externen Teilnehmern durch ihre Schüler zu begrenzen. |
|||

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie mit einem Richtlinienpaket verknüpfte Richtlinien einfach erkennen können. Wenn Sie beispielsweise Lehrern in ihrer Schule das Education_Teacher-Richtlinienpaket zuweisen, wird eine Richtlinie mit dem Namen Education_Teacher für jede Richtlinie im Paket erstellt.

![Screenshot des Education_Teacher-Richtlinienpakets](media/policy-packages-education_teacher.png)

> [!NOTE]
> Wenn Sie entscheiden, dass Lehrer und Mitarbeiter des administrativen Supports unterschiedliche Richtlinien benötigen, können Sie ein vorhandenes Paket wieder verwenden: identifizieren Sie ein Paket, das Sie derzeit nicht verwenden, und ändern Sie die Einstellungen, damit Sie für diese Gruppe geeignet sind. Möglicherweise müssen Sie sich selbst eine Notiz machen, welche Gruppe welches Paket hat, aber das ist das einzige Hindernis für die Neuzuweisung eines Pakets.

## <a name="why-use-policy-packages"></a>Gründe für das Verwenden von Richtlinien Paketen

Wenn Ihre Institution Hunderte oder sogar Tausende von Benutzern hat, Fragen Sie sich möglicherweise selbst: "Warum sollten Sie sich die Zeit nehmen, allen diesen Benutzern ein Paket oder ein anderes zu zuweisen?"

Das Zuweisen von Paketen zu Hunderten von Benutzern ist eine Investition in administrative Zeit ohne Frage. Wichtig bei Investitionen ist, dass Sie sich im Laufe der Zeit und nicht sofort amortisieren.

In einer Bildungsumgebung gibt es viele Benutzer mit den gleichen oder ähnlichen Rollen. Sie verbringen weniger Aufwand im Laufe der Zeit, wenn Sie die Benutzeroberfläche auf die gleiche Weise verwalten. Pakete gruppieren eine Reihe von Richtlinien, die für die verschiedenen Rollen in der Institution spezifisch sind. Benutzern mit der gleichen Lizenz, aber unterschiedlichen Rollen können entsprechend ihrer Rolle relevante Richtlinien zugewiesen werden, was effizienter ist als das Optimieren von Richtlinien für einzelne Benutzer.

Sobald alle Benutzer in der Institution in Gruppen sortiert sind und Pakete angewendet werden, müssen Sie die Paketeinstellungen einmal für alle Benutzer ändern, die dem Paket zugewiesen sind. Sie können festlegen, dass die Richtlinien innerhalb eines Pakets vor oder nach dem Zuweisen von Benutzern zum Paket optimiert werden.

Informationen dazu finden Sie unter [Verwalten von Richtlinien Paketen in Microsoft Teams](manage-policy-packages.md) für schrittweise Anleitungen zum Zuweisen einzelner Benutzer zu einem Paket, zum Zuweisen von Paketen in einer Bulk-Version für bis zu 20 Benutzer sowie zum Verwalten und Aktualisieren der mit den einzelnen Paketen verknüpften Richtlinien.
