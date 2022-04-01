---
title: Schichten für Teams
description: Erhalten Sie den Administratorleitfaden, den Sie zum Einrichten und Verwalten von Schichten, dem Tool für die Zeitplanverwaltung, in ihrer Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592771"
---
# <a name="shifts-for-teams"></a>Schichten für Teams

Schichten, das Zeitplanverwaltungstool in Teams, sorgt dafür, dass die Mitarbeiter an der Frontlinie verbunden und synchronisiert sind. Es wurde zuerst für die schnelle und effektive Verwaltung von Terminplänen und die Kommunikation auf mobilen Geräten erstellt. Mit Schichten können Frontlinienmanager und -mitarbeiter Zeitpläne nahtlos verwalten und in Kontakt bleiben.

Manager können Schichtzeitpläne für ihre Teams erstellen, aktualisieren und verwalten. Sie können Schichten zuweisen, offene Schichten hinzufügen und Zeitplananforderungen von Mitarbeitern genehmigen. Mitarbeiter können ihre eigenen Zeitpläne und die Zeitpläne ihres Teams anzeigen, ihre Verfügbarkeit festlegen, einen Schichttausch anfordern oder anbieten, freizeit anfragen sowie ein- und aussuhren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Die folgenden Ressourcen helfen Ihnen beim Einrichten und Verwalten von Schichten in Ihrer Organisation.

## <a name="set-up-and-manage-shifts"></a>Einrichten und Verwalten von Schichten

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Verwalten von Schichten](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Erfahren Sie, wie Sie Schichten für Ihre Organisation verwalten.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Verwalten von Zeitplanbesitzern für die Schichtverwaltung](shifts/schedule-owner-for-shift-management.md)** Mit diesem Feature können Sie die Berechtigungen eines Teammitglieds auf einen Zeitplanbesitzer erhöhen, ohne den Mitarbeiter zum Teambesitzer zu machen.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Häufig gestellte Fragen (FAQ) zum Verschieben von Daten](shifts/shifts-data-faq.md)** Erfahren Sie, wo Schichtendaten gespeichert werden und weitere Themen im Zusammenhang mit Schichtendaten, einschließlich Aufbewahrung, Abruf und Verschlüsselung.        |

## <a name="shifts-connectors"></a>Verschiebt Verbinder

Wenn Sie ein WFM-System (Personalverwaltung) von Drittanbietern für die Planung verwenden, können Sie Schichten direkt über verwaltete Schichten-Connectors und über Schichten Graph-APIs und SDK mit Open-Source-Connectors für Schichten integrieren. Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in der Frontlinie ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Übersicht über Verbinder "Schichten"](shifts/shifts-connectors.md)** Verschaffen Sie sich einen Überblick über Verbinder für Schichten und deren Funktionsweise. Hier finden Sie Informationen zu den verwalteten und Open-Source-Connectors, die verfügbar sind, sowie zu den unterstützten WFM-Systemen.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Connectors für verwaltete Schichten](shifts/shifts-connectors.md#managed-shifts-connectors)** Connectors für verwaltete Schichten, die in Zusammenarbeit mit unseren Partnern entwickelt wurden, werden entweder von uns oder von unseren Partnern gehostet und verwaltet. Weitere Informationen finden Sie Microsoft Teams Connector für Schichten [für Blue Yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) und [Reflexis Shifts Connector für Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Verwenden des Assistenten "Schichtenconnector", um Schichten mit der Personalverwaltung in Blue Yonder zu verbinden](shifts/shifts-connector-wizard.md)** Der Assistent für Schichtenconnector in Microsoft 365 Admin Center hilft Ihnen, schnell eine Verbindung mit Ihrem WFM-System herzustellen. Derzeit unterstützt der Assistent den Connector Teams Schichten für Blue Yonder, um Schichten in die Personalverwaltung von Blue Yonder zu integrieren.
|  | **[Verwenden von PowerShell zum Verbinden von Schichten mit der Personalverwaltung in Blue Yonder](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Erfahren Sie, wie Sie mithilfe von PowerShell eine Verbindung mit Blue Yonder Workforce Management über den Teams Shifts Connector für Blue Yonder einrichten.         |
|   | **[Verwenden von PowerShell zum Verwalten Ihrer Schichtenverbindung zur Personalverwaltung von Blue Yonder](shifts/shifts-connector-powershell-manage.md)** Erhalten Sie Anleitungen zur Verwendung von PowerShell zum Verwalten Ihrer Schichtenverbindung mit Blue Yonder Workforce Management, nachdem Sie sie über den Connector-Assistenten für Schichten oder PowerShell eingerichtet haben.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[Open-Source-Verbinder "Schichten"](/microsoftteams/platform/samples/shifts-wfm-connectors)** Hier erfahren Sie, wie [Sie Community-gesteuerte Open-Source-Connectors](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) verwenden, um Ihr Kroneos- oder JDA-WFM-System über Schichten Graph APIs und SDK zu integrieren.    |

## <a name="shifts-extensions"></a>Schichten-Erweiterungen

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Schicht- Graph-APIs](/graph/api/resources/shift)** Schichten Graph-APIs ermöglichen Ihnen die Integration von Schichtdaten in WFM-Systeme (Externe Mitarbeiterverwaltung). Sie haben die Flexibilität, benutzerdefinierte Schichten-Erfahrungen im Back-End zu erstellen, während Sie Benutzern gleichzeitig eine umfassende Front-End-Erfahrung in ihrer Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Mit Schichten + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Schichten + Power Automate können Sie Informationen aus Schichten übernehmen und benutzerdefinierte Workflows mit anderen Apps erstellen und Vorgänge im Maßstab durchführen. Automatisieren Sie wichtige Prozesse mit wenig bis gar keinem Code. Die Trigger und Vorlagen unterstützen verschiedene Szenarien, z. B. das Aktivieren der automatischen Genehmigung für Schichtanforderungen, wenn keine Genehmigung eines Vorgesetzten erforderlich ist. |

## <a name="featured-training"></a>Empfohlene Schulung

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Video: Was sind Schichten?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Video: Erstellen eines Schichtplans](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Video: Verwalten eines Schichtplans](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
