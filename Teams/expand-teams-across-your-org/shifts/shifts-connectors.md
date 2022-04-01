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
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592890"
---
# <a name="shifts-connectors"></a>Verschiebt Verbinder

## <a name="overview"></a>Übersicht

Schichten-Connectors ermöglichen Ihnen die Integration von Schichten, dem Zeitplanungsverwaltungstool in Microsoft Teams, in Ihr Personalverwaltungssystem (Personalverwaltung, WFM). Nachdem Sie eine Verbindung eingerichtet haben, können Ihre Mitarbeiter in der Frontlinie ihre Zeitpläne in Ihrem WFM-System nahtlos in Schichten anzeigen und verwalten.

Wenn Sie Ihr WFM-System Teams, können die Mitarbeiter an der Frontlinie Zeitpläne effektiver verwalten und die täglichen Prozesse für ein höheres Engagement und höhere Produktivität rationalisieren. Ihre Mitarbeiter in der Front haben einen Ort für ihre Planung, Kommunikation und Zusammenarbeit, um Ihre Arbeit von überall aus und auf jedem Gerät erledigen zu können.

Wir bieten verwaltete und Open-Source-Schichten-Connectors an. Dieser Artikel bietet eine Übersicht über Verbinder für Schichten und deren Funktionsweise.

## <a name="how-shifts-connectors-work"></a>Funktionsweise von Schichten-Verbindern

Connectors synchronisieren Zeitplandaten zwischen Ihrem WFM-System und Schichten, um die Zeitpläne Ihrer Organisation in Teams. Schichten ist der Ort, an dem sich Ihre Mitarbeiter in der Front für ihre Planungsanforderungen engagieren. Ihr WFM-System ist das System der Datensatze für Geschäftsregeln, Compliance und Intelligence.

Datenflüsse über den Connector stellen beide Möglichkeiten sicher, dass Zeitpläne immer auf dem neuesten Stand sind. Zeitpläne in Ihrem WFM-System werden mit Schichten synchronisiert. Und Änderungen an Zeitplänen in Schichten werden in Echtzeit mit Ihrem WFM-System synchronisiert. Als Datensatzsystem werden alle Geschäftsregeln von Ihrem WFM-System erzwungen, bevor Daten in Schichten gespeichert werden.

## <a name="managed-shifts-connectors"></a>Connectors für verwaltete Schichten

Connectors für verwaltete Schichten sind Connectors, die in Zusammenarbeit mit unseren Partnern entwickelt wurden. Verwaltete Connectors werden entweder von uns oder unseren Partnern gehostet und verwaltet. Bei verwalteten Connectors ist nur eine minimale Einrichtung erforderlich.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams Schichten-Connector für Blue Yonder
<a name="blue_yonder"> </a>

Der Teams Schichten Connector für Blue Yonder ist ein First-Party-Angebot, das von Microsoft gehostet und verwaltet wird. Mit diesem Connector können Sie Schichten in die Blue Yonder Workforce Management-Versionen 2020.3, 2021.1 oder 2021.2 integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten.  

> [!NOTE]
> Wenn Sie über Blue Yonder WFM Version 2020.3 oder 2021.1 verfügen, wenden Sie das Patch 2020.3.0.4 oder 2021.1.0.3 an. Dieser Patch behebt ein Problem, bei dem Benutzer in Schichten eine dauerhafte Fehlermeldung erhalten. Außerdem wird ein Problem behoben, das verhindert, dass Benutzer ihre Verfügbarkeit in Schichten aktualisieren.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Der Screenshot zeigt eine Tauschanfrage in Schichten auf einem mobilen Gerät, eine Genehmigungsanforderung in Teams auf dem Desktop und einen Zeitplan in Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Frontline-Manager können:

- Veröffentlichen Sie Schichten und Zeitpläne in Blue Yonder WFM, und zeigen Sie sie in Schichten an.
- Erstellen, verwalten und weisen Sie offene Schichten in Blue Yonder WFM zu, und zeigen Sie sie in Schichten an.
- Weisen Sie offene Schichten zu, die in Blue Yonder WFM in Schichten erstellt wurden.
- Erstellen, bearbeiten und löschen Sie Freizeit in Blue Yonder WFM, und zeigen Sie sie in Schichten an.
- Anzeigen und Genehmigen von Zeitplananforderungen von Mitarbeitern in Blue Yonder WFM und Schichten.
- Festlegen und Aktualisieren der Verfügbarkeit von Workern in Blue Yonder WFM und Anzeigen in Schichten.

Mitarbeiter an vorder frontline können:

- Sehen Sie sich die Schichten und Zeitpläne ihres Teams in Schichten an.
- Anfragen von freien Zeit, offenen Schichten und Tauschen von Schichten in Schichten
- Legen Sie deren Verfügbarkeit in Schichten festgelegt.

Die folgenden Aktionen werden derzeit nicht unterstützt:

- Sie können Schichten in Schichten hinzufügen, bearbeiten, löschen, speichern oder veröffentlichen.
- Sie können in Schichten Zeiten hinzufügen, bearbeiten, löschen, speichern oder veröffentlichen.
- Sie können offene Schichten in Schichten hinzufügen, bearbeiten, löschen, speichern oder veröffentlichen.

Wenn ein Frontline-Manager oder -Mitarbeiter in Schichten eine dieser Aktionen ausführen möchte, erhält er eine Meldung, dass die Aktion nicht unterstützt wird.

#### <a name="example-scenario"></a>Beispielszenario

Eden, ein Manager, veröffentlicht einen Zeitplan in Blue Yonder WFM, der über den Connector mit Schichten in Teams synchronisiert wird. Alex, ein Mitarbeiter, wird in einem Teams Gerät benachrichtigt, und sein Zeitplan und die zugewiesenen Schichten werden angezeigt.

Alex muss sich etwas Zeit nehmen und bittet um einen Tag mit Schichten. Die Anforderung wird über den Connector in Echtzeit an Blue Yonder WFM gesendet. Blue Yonder WFM stellt sicher, dass die Anforderung den Geschäftsregeln entspricht und die Anforderung erstellt wird. Eden sieht und genehmigt die Anforderung in Blue Yonder WFM, und die Genehmigung wird mit Teams. (Eden kann die Anfrage auch in Schichten sehen und genehmigen.) Alex wird in Teams, dass seine Anfrage genehmigt wurde, und der aktualisierte Zeitplan wird angezeigt.

Alex möchte eine Schicht mit einem Kollegen tauschen. In Schichten sieht Alex eine Liste aller Schichten, die aufgrund der Geschäftsregeln in Blue Yonder WFM für einen Tausch geeignet sind. Alex wählt eine Schicht aus, die derzeit Gena zugewiesen ist. Gena wird in Teams mobilen Gerät benachrichtigt und akzeptiert die Tauschanfrage. Eden sieht und genehmigt die Anfrage in Schichten, und die Genehmigung wird mit Blue Yonder WFM synchronisiert. (Eden kann die Anfrage auch in Blue Yonder WFM sehen und genehmigen. Alex und Gena werden in Teams benachrichtigt und zeigen ihre aktualisierten Zeitpläne an.

#### <a name="set-up-a-connection"></a>Einrichten einer Verbindung

Zum Integrieren von Schichten in Blue Yonder WFM mithilfe des Connectors sind nur ein paar Schritte erforderlich. Sie können den Assistenten "Schichten Verbinder" in Microsoft 365 Admin Center, um schnell eine Verbindung herzustellen. Der Assistent konfiguriert den Connector basierend auf den von Ihnen festgelegten Einstellungen und erstellt die Verbindung. Wenn Sie lieber PowerShell verwenden, stellen wir auch PowerShell-Skripts zur Verfügung, die Sie für die Verbindung verwenden können.

Eine Schritt-für-Schritt-Anleitung finden Sie unter:

- [Verwenden des Assistenten "Schichtenconnector", um Schichten mit der Personalverwaltung in Blue Yonder zu verbinden](shifts-connector-wizard.md)
- [Verwenden von PowerShell zum Verbinden von Schichten mit der Personalverwaltung in Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)

Nachdem eine Verbindung eingerichtet wurde, können Sie PowerShell verwenden, um die Verbindungseinstellungen jederzeit zu aktualisieren und zu ändern. Für den Connector selbst müssen Sie sich keine Gedanken über Upgrades oder Wartungen machen. Darum kümmern wir uns.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Reflexis Shifts connector for Microsoft Teams

The Reflexis Shifts connector for Microsoft Teams is hosted and managed by Connectors. Mit diesem Connector können Sie Schichten in das Reflexis WFM-System integrieren, um Ihre Zeitpläne zu verwalten und auf dem neuesten Stand zu halten.

Mitarbeiter an vorder frontline haben in Schichten in Teams Zugriff auf ihren Zeitplan, und ihre Anfragen werden von Schichten zu Reflexis Workforce Scheduler (RWS) synchronisiert. Der Status von Anforderungen und Schichten, die in RWS erstellt wurden, wird mit Schichten in Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Screenshot mit einer Liste von Schichten auf einem mobilen Gerät und einem Zeitplan in Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Frontline-Manager können:

- Veröffentlichen Sie Schichten und Zeitpläne in Reflexis, und zeigen Sie sie in Schichten an.
- Bearbeiten Sie Schichten sowohl in Reflexis als auch in Schichten.
- Erstellen, verwalten und weisen Sie offene Schichten sowohl in Reflexis als auch Schichten zu.
- Sie können Zeitplananforderungen von Mitarbeitern sowohl in Reflexis als auch in Schichten anzeigen und genehmigen.

Mitarbeiter an vorder frontline können:

- Sehen Sie sich die Schichten und Zeitpläne ihres Teams in Schichten an.
- Fordern Sie freie Zeit, offene Schichten, Tauschen und Anbieten von Schichten an.

Weitere Informationen finden Sie unter https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Open-Source-Verbinder "Schichten"

Open-Source-Connectors für Schichten sind Community-gesteuerte Integrationen, die auf Schichten [und Graph-APIs aufgebaut sind](/graph/api/resources/shift). Die folgenden Open-Source-Connectors sind verfügbar:

- Kroneos-to-Teams WFC lokal
- JDA-to-Teams Shifts Connector (für Blue Yonder Version 2017 bis 2020.2)

Jeder Connector verfügt über detaillierte Bereitstellungs- und Konfigurationsleitfäden. Sie umfassen Azure Resource Manager-Bereitstellungsskripts (ARM), die Ihnen das Hosten aller erforderlichen Dienste in Microsoft Azure. Der Quellcode und die Bereitstellungsskripts stehen in einem Repository für GitHub [zum Download bereit](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). Sie können die Bereitstellung so anpassen oder erweitern, dass sie Ihren Anforderungen entspricht.

Weitere Informationen finden Sie unter [Produktionsfertige Schichten-Connectors](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
