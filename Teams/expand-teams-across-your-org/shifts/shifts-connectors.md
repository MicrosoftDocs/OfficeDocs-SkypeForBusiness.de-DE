---
title: Schichtenverbinder
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über Schichtenconnectors und deren Verwendung, um Schichten mit Ihrem Mitarbeiterverwaltungssystem zu verbinden.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2022
ms.locfileid: "64592890"
---
# <a name="shifts-connectors"></a>Schichtenverbinder

## <a name="overview"></a>Übersicht

Schichtenconnectors ermöglichen Ihnen die Integration von Schichten, dem Zeitplanverwaltungstool in Microsoft Teams, in Ihr Personalverwaltungssystem (WFM). Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in Service und Produktion ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

Wenn Sie Ihr WFM-System mit Teams verbinden, können Ihre Mitarbeiter in Service und Produktion Zeitpläne effektiver verwalten und alltägliche Prozesse für mehr Engagement und Produktivität optimieren. Ihre Mitarbeiter in Service und Produktion haben einen Zentralen für ihre Planung, Kommunikation und Zusammenarbeit, um ihre Arbeit von praktisch überall und auf jedem Gerät erledigen zu können.

Wir bieten verwaltete und Open Source Shifts-Connectors an. In diesem Artikel erhalten Sie einen Überblick über Schichtenconnectors und deren Funktionsweise.

## <a name="how-shifts-connectors-work"></a>Funktionsweise von Schichtenconnectors

Connectors synchronisieren Zeitplandaten zwischen Ihrem WFM-System und Schichten, wodurch die Zeitpläne Ihrer Organisation in Teams. Schichten sind der Ort, an dem Sich Ihre Mitarbeiter in Service und Produktion für ihre Terminplanungsanforderungen engagieren. Ihr WFM-System ist das System des Datensatzes für Geschäftsregeln, Compliance und Intelligenz.

Datenflüsse über den Connector bieten beide Möglichkeiten, um sicherzustellen, dass Zeitpläne immer auf dem neuesten Stand sind. Zeitpläne in Ihrem WFM-System werden mit Schichten synchronisiert. Und Änderungen an Zeitplänen in Schichten werden in Echtzeit wieder mit Ihrem WFM-System synchronisiert. Als Datensatzsystem werden alle Geschäftsregeln von Ihrem WFM-System erzwungen, bevor Daten in Schichten gespeichert werden.

## <a name="managed-shifts-connectors"></a>Verbinder für verwaltete Schichten

Managed Shifts Connectors sind Connectors, die in Zusammenarbeit mit unseren Partnern entwickelt wurden. Verwaltete Connectors werden entweder von uns oder unseren Partnern gehostet und verwaltet. Bei verwalteten Connectors ist nur ein minimales Setup erforderlich.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams Shifts-Verbinder für Blue Yonder
<a name="blue_yonder"> </a>

Der Teams Shifts-Connector für Blue Yonder ist ein Erstanbieterangebot, das von Microsoft gehostet und verwaltet wird. Mit diesem Connector können Sie Schichten in die Blue Yonder Workforce Management (Blue Yonder WFM)-Versionen 2020.3, 2021.1 oder 2021.2 integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten.  

> [!NOTE]
> Wenn Sie über Blue Yonder WFM Version 2020.3 oder 2021.1 verfügen, wenden Sie den Patch 2020.3.0.4 oder 2021.1.0.3 an. Dieser Patch behebt ein Problem, bei dem Benutzer eine dauerhafte Fehlermeldung in Schichten erhalten. Außerdem wird ein Problem behoben, das verhindert, dass Benutzer ihre Verfügbarkeit in Schichten aktualisieren.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Screenshot mit einer Swapanfrage in Schichten auf einem mobilen Gerät, einer Anforderungsgenehmigung in Teams auf dem Desktop und einem Zeitplan in Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Vorgesetzte in Service und Produktion können:

- Veröffentlichen Sie Schichten und Zeitpläne in Blue Yonder WFM, und zeigen Sie sie in Schichten an.
- Erstellen, verwalten und zuweisen Sie offene Schichten in Blue Yonder WFM, und zeigen Sie sie in Schichten an.
- Weisen Sie offene Schichten zu, die in Blue Yonder WFM in Schichten erstellt wurden.
- Erstellen, Bearbeiten und Löschen von Abwesenheitszeiten in Blue Yonder WFM und Anzeigen in Schichten.
- Anzeigen und Genehmigen von Terminplananforderungen von Mitarbeitern in Blue Yonder WFM und Schichten.
- Legen Sie die Verfügbarkeit der Mitarbeiter in Blue Yonder WFM fest, und aktualisieren Sie sie, und zeigen Sie sie in Schichten an.

Mitarbeiter in Service und Produktion können:

- Sehen Sie die Schichten und Zeitpläne ihrer Eigenen und ihres Teams in Schichten.
- Fordern Sie Abwesenheitszeiten an, öffnen Sie Schichten, und tauschen Sie Schichten in Schichten aus.
- Legen Sie ihre Verfügbarkeit in Schichten fest.

Die folgenden Aktionen werden derzeit nicht unterstützt:

- Schichten in Schichten hinzufügen, bearbeiten, löschen, speichern oder veröffentlichen.
- Sie können abwesenheitsfreie Zeiten in Schichten hinzufügen, bearbeiten, löschen, speichern oder veröffentlichen.
- Offene Schichten in Schichten hinzufügen, bearbeiten, löschen, speichern oder veröffentlichen.

Wenn ein Vorgesetzter oder Mitarbeiter in Service und Produktion versucht, eine dieser Aktionen in Schichten auszuführen, wird eine Meldung angezeigt, die ihn darüber informieren soll, dass die Aktion nicht unterstützt wird.

#### <a name="example-scenario"></a>Beispielszenario

Eden, ein Manager, veröffentlicht einen Zeitplan in Blue Yonder WFM, der mit Schichten in Teams über den Connector synchronisiert wird. Alex, ein Mitarbeiter, wird in Teams auf seinem mobilen Gerät benachrichtigt und zeigt seinen Zeitplan und die zugewiesenen Schichten an.

Alex muss sich etwas Freizeit nehmen und fordert einen freien Tag mithilfe von Schichten an. Die Anforderung wird über den Connector in Echtzeit an Blue Yonder WFM gesendet. Blue Yonder WFM stellt sicher, dass die Anforderung den Geschäftsregeln entspricht und die Anforderung erstellt wird. Eden sieht und genehmigt die Anforderung in Blue Yonder WFM, und die Genehmigung wird mit Teams synchronisiert. (Eden kann die Anforderung auch in Schichten anzeigen und genehmigen). Alex wird in Teams benachrichtigt, dass seine Anfrage genehmigt wurde, und zeigt seinen aktualisierten Zeitplan an.

Alex möchte eine Schicht mit einem Kollegen tauschen. In Schichten sieht Alex eine Liste aller Schichten, die für einen Tausch berechtigt sind, basierend auf Geschäftsregeln in Blue Yonder WFM. Alex wählt eine Schicht aus, die derzeit Gena zugewiesen ist. Gena wird in Teams auf ihrem mobilen Gerät benachrichtigt und akzeptiert die Swapanfrage. Eden sieht und genehmigt die Anforderung in Schichten, und die Genehmigung wird mit Blue Yonder WFM synchronisiert. (Eden kann die Anfrage auch in Blue Yonder WFM anzeigen und genehmigen). Alex und Gena werden in Teams benachrichtigt und zeigen ihre aktualisierten Zeitpläne an.

#### <a name="set-up-a-connection"></a>Einrichten einer Verbindung

Die Integration von Schichten mit Blue Yonder WFM mithilfe des Connectors erfordert nur ein paar Schritte. Sie können den Verbinder-Assistenten für Schichten im Microsoft 365 Admin Center verwenden, um schnell eine Verbindung einzurichten. Der Assistent konfiguriert den Connector basierend auf den von Ihnen ausgewählten Einstellungen und erstellt die Verbindung. Wenn Sie PowerShell verwenden möchten, stellen wir auch PowerShell-Skripts bereit, mit denen Sie eine Verbindung herstellen können.

Eine schrittweise Anleitung finden Sie unter:

- [Verwenden des Verbinder-Assistenten "Schichten" zum Verbinden von Schichten mit Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Verwenden von PowerShell zum Verbinden von Schichten mit Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Nachdem eine Verbindung eingerichtet wurde, können Sie PowerShell verwenden, um die Verbindungseinstellungen jederzeit nach Bedarf zu aktualisieren und zu ändern. Was den Connector selbst betrifft, müssen Sie sich keine Gedanken über Upgrades oder Wartung machen. Wir kümmern uns darum.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Reflexis Shifts-Verbinder für Microsoft Teams

Der Reflexis Shifts Connector für Microsoft Teams wird von Zebra gehostet und verwaltet. Mit diesem Connector können Sie Schichten in das Reflexis WFM-System integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten.

Mitarbeiter in Service und Produktion haben Zugriff auf ihren Zeitplan in Schichten in Teams, und ihre Anforderungen werden von Schichten zu Reflexis Workforce Scheduler (RWS) synchronisiert. Der Status von Anforderungen und Schichten, die in RWS erstellt wurden, wird mit Schichten in Teams synchronisiert.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Screenshot mit einer Liste der Schichten auf einem mobilen Gerät und einem Zeitplan in Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Vorgesetzte in Service und Produktion können:

- Veröffentlichen Sie Schichten und Zeitpläne in Reflexis, und zeigen Sie sie in Schichten an.
- Bearbeiten Sie Schichten sowohl in Reflexis als auch in Schichten.
- Erstellen, Verwalten und Zuweisen von offenen Schichten in Reflexis und Schichten.
- Anzeigen und Genehmigen von Terminplananforderungen von Mitarbeitern sowohl in Reflexis als auch in Schichten.

Mitarbeiter in Service und Produktion können:

- Sehen Sie die Schichten und Zeitpläne ihrer Eigenen und ihres Teams in Schichten.
- Fordern Sie Abwesenheitszeiten an, öffnen Sie Schichten, tauschen Sie Schichten und bieten Sie Schichten in Schichten an.

Weitere Informationen finden Sie unter https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Open-Source-Schichtenconnectors

Open Source Shifts Connectors sind communitygesteuerte Integrationen, die auf [Schichten Graph APIs](/graph/api/resources/shift) basieren. Die folgenden Open Source-Connectors sind verfügbar:

- Kronos-to-Teams WFC lokal
- JDA-to-Teams Shifts Connector (für Blue Yonder Version 2017 bis 2020.2)

Jeder Connector enthält detaillierte Bereitstellungs- und Konfigurationsanleitungen. Dazu gehören Azure Resource Manager (ARM)-Bereitstellungsskripts, mit denen Sie alle erforderlichen Dienste in Microsoft Azure hosten können. Der Quellcode und die Bereitstellungsskripts stehen in einem [GitHub-Repository](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) zum Download zur Verfügung. Sie können die Bereitstellung wie besehen oder anpassen oder erweitern, um Ihre Anforderungen zu erfüllen.

Weitere Informationen finden Sie unter ["Produktionsbereite Schichtenconnectors](/microsoftteams/platform/samples/shifts-wfm-connectors)".

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
