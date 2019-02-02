---
title: Erste Schritte mit Retail Teams Vorlagen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 02/01/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Teams Vorlagen zum Erstellen von Strukturen, die entworfen, um Anforderungen Händler verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e74a7d44709f93fd0ef74917e5fc21103d2a8bbd
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715437"
---
# <a name="get-started-with-retail-teams-templates"></a>Erste Schritte mit Retail Teams Vorlagen 

Teams Vorlagen können Sie schnell und einfach Teams durch die Bereitstellung von Einstellungen, Kanäle und vorinstallierte apps einer vordefinierten Vorlage erstellen.

Retail Teams Vorlagen haben Definitionen von Strukturen, die entworfen, um Händler Anforderungen vorab erstellte. Retail Teams Vorlagen können Sie schnell die Arten von Teams erstellen, eignen sich gut für Einzelhandelsunternehmen und stellen diese in Ihrer Organisation. Sie können auch die Retail Teams Vorlagen zum Erstellen von Teams, die auf Ihre Organisation Bedürfnisse zugeschnitten werden erweitern.

In diesem Artikel erhalten Sie eine Einführung einzelnen Vorlagen Retail Teams und wie es wird empfohlen, diese.

Dieser Artikel ist für Sie, wenn Sie für das Planen, bereitstellen und Verwalten von mehreren Teams innerhalb Ihrer Organisation Retail verantwortlich sind.

Weitere Informationen zu Team finden Vorlagen finden Sie im Allgemeinen bitte in [Erste Schritte mit Teams Vorlagen](get-started-with-teams-templates.md).

## <a name="store-template"></a>Store-Vorlage

Die Store-Vorlage ist eine der Vorlagen für den Einzelhandel Teams. Die Vorlage Store eignet sich ideal für das Erstellen eines Teams, um ein einzelnes Store Einzelhandel darstellen. Mit der Vorlage Store können Sie ein Team für jeden Retail Store Standort in Ihrer Organisation erstellen.

| Basisvorlage-Typ | baseTemplateId | Eigenschaften, die im Lieferumfang von diese Basisvorlage |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail- <br>Anmelden | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore`| Kanäle <ul><li>Verschiebt die Übergabe\*</li><li>Learning\*</li></ul>\*Automatische favorisierte Kanäle<br><br>Team-Eigenschaften <ul><li>Team Sichtbarkeit auf Public festgelegt</li></ul> <br>Member-Berechtigungen <ul><li>Kann nicht erstellen/aktualisieren/löschen Kanäle </li><li>Apps können nicht hinzufügen/entfernen werden </li><li>Kann nicht Registerkarten erstellen/aktualisieren/entfernen</li><li>Kann nicht erstellen/aktualisieren/Entfernen von connectors</li><ul>|
||||

Empfohlene Vorgehensweisen zum Anpassen der Vorlage Speicher für Ihre Organisation:

- Wenn Ihre Organisation Abteilungen innerhalb jeder Informationsspeicher verfügt, fügen Sie einen Kanal für jede Abteilung. Dadurch wird die Kommunikation und Zusammenarbeit innerhalb der Abteilung erleichtern.

- Wenn Ihre Organisation keine interne Websites (beispielsweise eine SharePoint-Website) verfügt, sollten Sie festhalten werden als Registerkarten in den entsprechenden Team DDE-Kanal. In der Dokumentation finden Sie [hier](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Manager für die Zusammenarbeit-Vorlage

Die Vorlage-Manager für die Zusammenarbeit ist ein weiteres der Vorlagen Retail Teams. Die Vorlage-Manager für die Zusammenarbeit eignet sich ideal für das Erstellen eines Teams für eine Reihe von Managern über Speicher/Regionen/Etc zusammenarbeiten. Wenn Ihre Organisation Regionen verfügt, können Sie beispielsweise erstellen ein Team-Manager für die Zusammenarbeit für die Region Kalifornien (CA) und die Store Manager in diesem Bereich als auch die regionalen Manager für dieser Region enthalten.

| Basisvorlage-Typ | baseTemplateId | Eigenschaften, die im Lieferumfang von diese Basisvorlage |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail- <br>Anmelden | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration`| Kanäle <ul><li>Betrieb\*</li><li>Learning\*</li></ul>\*Automatische favorisierte Kanäle<br><br>Team-Eigenschaften <ul><li>Team Visibility auf Private festgelegt</li></ul> <br>Member-Berechtigungen <ul><li>Erstellen/Aktualisieren/löschen Kanäle können </li><li>Apps können hinzufügen/entfernen werden </li><li>Erstellen/Aktualisieren/Entfernen Registerkarten können</li><li>Erstellen/Aktualisieren/Entfernen Connectors können</li><ul>|
||||

Empfohlene Vorgehensweisen zum Anpassen der Vorlage-Manager für die Zusammenarbeit für Ihre Organisation:

- Wenn Ihr Unternehmen alle internen Websites (beispielsweise eine SharePoint-Website), die für Manager relevant sind verfügt, sollten Sie festhalten werden als Registerkarten in einem entsprechenden Team-Kanal (in der Dokumentation [hier](get-started-with-teams-templates.md) ).