---
title: Verschiebt Verbinder
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über Verbinder für Schichten und deren Verwendung, um Schichten mit Ihrem Personalverwaltungssystem zu verbinden.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192486"
---
# <a name="shifts-connectors"></a>Verschiebt Verbinder

## <a name="overview"></a>Übersicht

Schichten-Connectors ermöglichen Ihnen die Integration von Schichten, dem Zeitplanungsverwaltungstool in Microsoft Teams, in Ihr Personalverwaltungssystem (WFM). Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in der Frontlinie ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

Wenn Sie Ihr WFM-System Teams, können die Mitarbeiter an der Frontlinie Zeitpläne effektiver verwalten und die täglichen Prozesse für ein höheres Engagement und höhere Produktivität rationalisieren. Ihre Mitarbeiter in der Front haben einen Ort für ihre Planung, Kommunikation und Zusammenarbeit, um Ihre Arbeit von überall aus und auf jedem Gerät erledigen zu können.

Wir bieten verwaltete und Open-Source-Schichten-Connectors an. Dieser Artikel bietet eine Übersicht über Verbinder für Schichten und deren Funktionsweise.

## <a name="how-shifts-connectors-work"></a>Funktionsweise von Schichten-Verbindern

Connectors synchronisieren Zeitplandaten zwischen Ihrem WFM-System und Schichten, um die Zeitpläne Ihrer Organisation in eine Teams. Schichten ist der Ort, an dem sich Ihre Mitarbeiter in der Front für ihre Planungsanforderungen engagieren. Ihr WFM-System ist das System der Datensatze für Geschäftsregeln, Compliance und Intelligence.

Datenflüsse über den Connector stellen beide Möglichkeiten sicher, dass Zeitpläne immer auf dem neuesten Stand sind. Zeitpläne in Ihrem WFM-System werden mit Schichten synchronisiert. Und Änderungen an Zeitplänen in Schichten werden in Echtzeit mit Ihrem WFM-System synchronisiert. Als Datensatzsystem werden alle Geschäftsregeln von Ihrem WFM-System erzwungen, bevor Daten in Schichten gespeichert werden.

## <a name="managed-shifts-connectors"></a>Connectors für verwaltete Schichten

Connectors für verwaltete Schichten sind Connectors, die in Zusammenarbeit mit unseren Partnern entwickelt wurden. Verwaltete Connectors werden entweder von uns oder unseren Partnern gehostet und verwaltet. Bei verwalteten Connectors ist nur eine minimale Einrichtung erforderlich.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Reflexis Shifts connector for Microsoft Teams

The Reflexis Shifts connector for Microsoft Teams is hosted and managed by Connectors. Mit diesem Connector können Sie Schichten in das Reflexis WFM-System integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten.

Mitarbeiter an der Frontlinie haben Zugriff auf ihren Zeitplan in Schichten in Teams, und ihre Anforderungen werden von Schichten zu Reflexis Workforce Scheduler (RWS) synchronisiert. Der Status von Anforderungen und Schichten, die in RWS erstellt wurden, wird mit Schichten in Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Screenshot mit einer Liste von Schichten auf einem mobilen Gerät und einem Zeitplan in Reflexis" lightbox="../../media/shifts-connector-reflexis.png":::

Frontline-Manager können:

- Veröffentlichen Sie Schichten und Zeitpläne in Reflexis, und zeigen Sie sie in Schichten an.
- Bearbeiten Sie Schichten sowohl in Reflexis als auch in Schichten.
- Erstellen, verwalten und weisen Sie offene Schichten sowohl in Reflexis als auch Schichten zu.
- Sie können Zeitplananforderungen von Mitarbeitern sowohl in Reflexis als auch in Schichten anzeigen und genehmigen.

Mitarbeiter an vorder frontline können:

- Sehen Sie sich die Schichten und Zeitpläne ihres Teams in Schichten an.
- Fordern Sie freie Zeit, offene Schichten, Tauschen und Anbieten von Schichten an.

Weitere Informationen finden Sie unter https://connect.zebra.com/microsoft-connectors .

## <a name="open-source-shifts-connectors"></a>Open-Source-Verbinder "Schichten"

Open-Source-Connectors für Schichten sind Community-gesteuerte Integrationen, die auf Schichten [und Graph-APIs aufgebaut sind.](/graph/api/resources/shift) Die folgenden Open-Source-Connectors sind verfügbar:

- Kroneos-to-Teams WFC lokal
- JDA-to-Teams Shifts Connector (für Blue Yonder Version 2017 bis 2020.2)

Jeder Connector verfügt über detaillierte Bereitstellungs- und Konfigurationsleitfäden. Sie enthalten Bereitstellungsskripts des Azure-Ressourcen-Managers (ARM), die Ihnen das Hosten aller erforderlichen Dienste in Microsoft Azure. Der Quellcode und die Bereitstellungsskripts stehen in einem Repository für GitHub [zum Download bereit.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) Sie können die Bereitstellung so anpassen oder erweitern, dass sie Ihren Anforderungen entspricht.

Weitere Informationen finden Sie unter [Produktionsfertige Schichten-Connectors.](/microsoftteams/platform/samples/shifts-wfm-connectors)

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
