---
title: Schichten für Teams
description: Erhalten Sie die Administratoranleitungen, die Sie zum Einrichten und Verwalten von Schichten, dem Zeitplanverwaltungstool, in Teams benötigen.
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
ms.openlocfilehash: f8980116dab90abd3c9c96ac17b577e6abf64f90
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598308"
---
# <a name="shifts-for-teams"></a>Schichten für Teams

Schichten, das Zeitplanverwaltungstool in Teams, halten Ihre Mitarbeiter in Service und Produktion in Verbindung und synchron. Es wurde zuerst für eine schnelle und effektive Terminplanung und Kommunikation entwickelt. Mit Schichten können Vorgesetzte und Mitarbeiter in Service und Produktion nahtlos Zeitpläne verwalten und in Kontakt bleiben.

Manager können Schichtpläne für ihre Teams erstellen, aktualisieren und verwalten. Sie können Schichten zuweisen, offene Schichten hinzufügen und Zeitplananforderungen von Mitarbeitern genehmigen. Mitarbeiter können ihre eigenen Zeitpläne und die Zeitpläne ihres Teams anzeigen, ihre Verfügbarkeit festlegen, eine Schicht tauschen oder anbieten, Abwesenheitszeiten anfordern und ein- und auschecken.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Verwenden Sie die folgenden Ressourcen, um Schichten in Ihrer Organisation einzurichten und zu verwalten.

## <a name="set-up-and-manage-shifts"></a>Einrichten und Verwalten von Schichten

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Schichten verwalten](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Erfahren Sie, wie Sie Schichten für Ihre Organisation verwalten.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Verwalten von Terminplanbesitzern für die Schichtverwaltung](shifts/schedule-owner-for-shift-management.md)** Mit diesem Feature können Sie die Berechtigungen eines Teammitglieds auf einen Zeitplanbesitzer erhöhen, ohne den Mitarbeiter zu einem Teambesitzer zu machen.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Häufig gestellte Fragen zu Schichten von Daten](shifts/shifts-data-faq.md)** Erfahren Sie, wo Shifts-Daten gespeichert werden, und andere Themen im Zusammenhang mit Schichtdaten, einschließlich Aufbewahrung, Abruf und Verschlüsselung.        |

## <a name="shifts-connectors"></a>Schichtenverbinder

Wenn Sie ein WFM-System (Third-Party Workforce Management) für die Planung verwenden, können Sie über verwaltete Schichtconnectors direkt in Schichten integriert werden. Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in Service und Produktion ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Übersicht über Schichtverbinder](shifts/shifts-connectors.md)** Verschaffen Sie sich einen Überblick über Schichtenconnectors und deren Funktionsweise. Erfahren Sie mehr über die verfügbaren verwalteten Connectors und die unterstützten WFM-Systeme.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Verbinder für verwaltete Schichten](shifts/shifts-connectors.md#managed-shifts-connectors)** Managed Shifts Connectors, die in Zusammenarbeit mit unseren Partnern entwickelt wurden, werden entweder von uns oder unseren Partnern gehostet und verwaltet. Weitere Informationen finden Sie [unter Microsoft Teams Verbinder "Schichten" für blue yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) und [Reflexis Shifts connector for Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Verwenden des Verbinder-Assistenten "Schichten" zum Verbinden von Schichten mit Blue Yonder Workforce Management](shifts/shifts-connector-wizard.md)** Der Assistent für schichtenverbinder in der Microsoft 365 Admin Center hilft Ihnen, schnell eine Verbindung mit Ihrem WFM-System einzurichten. Derzeit unterstützt der Assistent den Teams Shifts-Connector für Blue Yonder, um Schichten in Blue Yonder Workforce Management zu integrieren.
|  | **[Verwenden von PowerShell zum Verbinden von Schichten mit Blue Yonder Workforce Management](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Erfahren Sie, wie Sie powerShell verwenden, um eine Verbindung mit Blue Yonder Workforce Management über den Teams Shifts-Connector für Blue Yonder einzurichten.         |
|   | **[Verwenden von PowerShell zum Verwalten Ihrer Schichtverbindung mit Blue Yonder Workforce Management](shifts/shifts-connector-powershell-manage.md)** Erhalten Sie Anleitungen zur Verwendung von PowerShell, um Ihre Schichtverbindung mit Blue Yonder Workforce Management zu verwalten, nachdem Sie sie über den Connector-Assistenten für Schichten oder PowerShell eingerichtet haben.

## <a name="shifts-extensions"></a>Schichtenerweiterungen

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Schichten Graph APIs](/graph/api/resources/shift)** Schichten Graph APIs ermöglichen es Ihnen, Schichtdaten in WFM-Systeme (External Workforce Management) zu integrieren. Sie haben die Flexibilität, benutzerdefinierte Schichten im Back-End zu erstellen und benutzern gleichzeitig eine umfassende Front-End-Erfahrung in Teams zu bieten.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Mit Schichten + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Schichten + Power Automate können Sie Informationen aus Schichten abrufen und benutzerdefinierte Workflows mit anderen Apps erstellen und Vorgänge im großen Maßstab ausführen. Automatisieren Sie wichtige Prozesse mit wenig bis gar keinem Code. Die Trigger und Vorlagen unterstützen verschiedene Szenarien, z. B. das Aktivieren von automatischen Genehmigungen für Schichtanforderungen, wenn die Genehmigung eines Vorgesetzten nicht erforderlich ist. |

## <a name="featured-training"></a>Empfohlene Schulung

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Video: Was ist Schichten?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Video: Erstellen eines Schichtplans](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Video: Verwalten eines Schichtplans](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
