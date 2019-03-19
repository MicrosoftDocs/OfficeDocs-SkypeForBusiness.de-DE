---
title: Erste Schritte mit Teams Vorlagen im Einzelhandel
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Teams Vorlagen zum Erstellen von Strukturen, die für Händler Anforderungen entwickelt verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664708"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Erste Schritte mit Teams Vorlagen im Einzelhandel 

Teams Vorlagen können Sie schnell und einfach Teams durch die Bereitstellung von Einstellungen, Kanäle und vorinstallierte apps einer vordefinierten Vorlage erstellen.

Teams Vorlagen haben Definitionen von Strukturen, die entworfen, um Händler Anforderungen vorab erstellte. Teams Vorlagen können Sie schnell die Arten von Teams erstellen, eignen sich gut für Einzelhandelsunternehmen und stellen diese in Ihrer Organisation. Sie können auch die Teams Vorlagen zum Erstellen von Teams, die auf Ihre Organisation Bedürfnisse zugeschnitten werden erweitern.

In diesem Artikel erhalten Sie eine Einführung einzelnen Teams Vorlagen und wie es wird empfohlen, deren Verwendung.

Dieser Artikel ist für Sie, wenn Sie für das Planen, bereitstellen und Verwalten von mehreren Teams innerhalb Ihrer Organisation Retail verantwortlich sind.

Weitere Informationen zu Team finden Vorlagen finden Sie im Allgemeinen bitte in [Erste Schritte mit Teams Vorlagen](get-started-with-teams-templates.md).

## <a name="store-template"></a>Store-Vorlage

Die Vorlage Store eignet sich ideal für das Erstellen eines Teams, um ein einzelnes Store Einzelhandel darstellen. Mit der Vorlage Store können Sie ein Team für jeden Retail Store Standort in Ihrer Organisation erstellen.

| Basisvorlage-Typ | baseTemplateId | Eigenschaften, die im Lieferumfang von diese Basisvorlage |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail- <br>abspeichern | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Kanäle <ul><li>Verschiebt die Übergabe\*</li><li>Learning\*</li></ul>\*Automatische favorisierte Kanäle<br><br>Team-Eigenschaften <ul><li>Team Sichtbarkeit auf Public festgelegt</li></ul> <br>Member-Berechtigungen <ul><li>Kann nicht erstellen/aktualisieren/löschen Kanäle </li><li>Apps können nicht hinzufügen/entfernen werden </li><li>Kann nicht Registerkarten erstellen/aktualisieren/entfernen</li><li>Kann nicht erstellen/aktualisieren/Entfernen von connectors</li><ul>|
||||

Empfohlene Vorgehensweisen zum Anpassen der Vorlage Speicher für Ihre Organisation:

- Wenn Ihre Organisation Abteilungen innerhalb jeder Informationsspeicher verfügt, fügen Sie einen Kanal für jede Abteilung. Dadurch wird die Kommunikation und Zusammenarbeit innerhalb der Abteilung erleichtern.

- Wenn Ihre Organisation keine interne Websites (beispielsweise eine SharePoint-Website) verfügt, sollten Sie festhalten werden als Registerkarten in den entsprechenden Team DDE-Kanal. Anweisungen finden Sie unter [Erste Schritte mit Teams Vorlagen](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Manager für die Zusammenarbeit-Vorlage

Die Vorlage-Manager für die Zusammenarbeit ist ein weiterer, die eine der Teams Vorlagen entworfen, um Händler benötigt. Die Vorlage-Manager für die Zusammenarbeit eignet sich ideal für das Erstellen eines Teams für eine Reihe von Zusammenarbeit im gesamten Speicher/Regionen usw. -Manager. Wenn Ihre Organisation Regionen verfügt, können Sie beispielsweise erstellen ein Team-Manager für die Zusammenarbeit für die Region Kalifornien (CA) und die Store Manager in diesem Bereich als auch die regionalen Manager für dieser Region enthalten.

| Basisvorlage-Typ | baseTemplateId | Eigenschaften, die im Lieferumfang von diese Basisvorlage |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail- <br>abspeichern | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Kanäle <ul><li>Vorgänge\*</li><li>Learning\*</li></ul>\*Automatische favorisierte Kanäle<br><br>Team-Eigenschaften <ul><li>Team Visibility auf Private festgelegt</li></ul> <br>Member-Berechtigungen <ul><li>Erstellen/Aktualisieren/löschen Kanäle können </li><li>Apps können hinzufügen/entfernen werden </li><li>Erstellen/Aktualisieren/Entfernen Registerkarten können</li><li>Erstellen/Aktualisieren/Entfernen Connectors können</li><ul>|
||||

Empfohlene Vorgehensweisen zum Anpassen der Vorlage-Manager für die Zusammenarbeit für Ihre Organisation:

- Wenn Ihr Unternehmen alle internen Websites (beispielsweise eine SharePoint-Website), die für Manager relevant sind verfügt, sollten Sie festhalten werden als Registerkarten in einem entsprechenden Team-Kanal (in der Dokumentation [hier](get-started-with-teams-templates.md) ).