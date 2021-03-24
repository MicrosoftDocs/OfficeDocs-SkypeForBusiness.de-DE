---
title: Erste Schritte mit Microsoft Teams-Vorlagen im Einzelhandel
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe von Teams-Vorlagen Teamstrukturen erstellen, die auf die Anforderungen von Einzelhändlern zugeschnitten sind, indem Sie vordefinierte Einstellungen, Kanäle und vorinstallierte Apps bereitstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101201"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Erste Schritte mit Microsoft Teams-Vorlagen im Einzelhandel

Mit Teams-Vorlagen können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Teams-Vorlagen enthalten vordefinierte Definitionen von Teamstrukturen, die auf die Bedürfnisse von Einzelhändlern zugeschnitten sind. Mithilfe von Teams-Vorlagen können Sie schnell die für Einzelhändler geeigneten Teamtypen erstellen und in Ihrem Unternehmen bereitstellen. Sie können die Teams-Vorlagen auch erweitern, um Teams zu erstellen, die auf Ihre spezifischen organisatorischen Anforderungen zugeschnitten sind.

In diesem Artikel stellen wir die einzelnen Teams-Vorlagen vor und empfehlen deren Verwendung.

Dieser Artikel richtet sich an Sie, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Einzelhandelsorganisation verantwortlich sind. Sie haben den Teams-Dienst bereits in Ihrer Organisation bereitgestellt. Wenn Sie Teams noch nicht eingeführt haben, lesen Sie zunächst die Anleitung zum [Einführen von Microsoft Teams](./deploy-overview.md).

Weitere Informationen zu Teams-Vorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teams-Vorlagen](get-started-with-teams-templates.md).

## <a name="store-template"></a>Store-Vorlage

Die Store-Vorlage eignet sich ideal zum Erstellen eines Teams zur Darstellung eines einzelnen Einzelhandelsgeschäftsstandorts. Mithilfe der Store-Vorlage können Sie ein Team für jeden Einzelhandelsgeschäftsstandort in Ihrer Organisation erstellen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Kanäle <ul><li>Verschiebt die Übergabe\*</li><li>Lernen\*</li></ul>\*Automatisch favorisierte Kanäle<br><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Öffentlich gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kanäle können nicht erstellt/aktualisiert/gelöscht werden </li><li>Apps können nicht hinzugefügt/entfernt werden </li><li>Tabs können nicht erstellt/aktualisiert/entfernt werden</li><li>Konnektoren können nicht erstellt/aktualisiert/entfernt werden</li><ul>|
||||

Empfohlene Möglichkeiten zum Anpassen der Store-Vorlage für Ihre Organisation:

- Wenn Ihre Organisation Abteilungen in jedem Geschäft hat, fügen Sie für jede Abteilung einen Kanal hinzu. Das Hinzufügen eines Kanals erleichtert die Kommunikation und Zusammenarbeit innerhalb der Abteilung.

- Wenn Ihre Organisation über interne Websites verfügt (z. B. eine SharePoint-Site), sollten Sie diese als Registerkarten im entsprechenden Teamkanal anheften. Anweisungen finden Sie unter [Erste Schritte mit Teams-Vorlagen](get-started-with-teams-templates.md).

## <a name="manager-collaboration-template"></a>Vorlage für die Kollaboration von Managern

Die Vorlage für die Kollaboration von Managern ist eine weitere Vorlage für Teams, die auf die Bedürfnisse von Einzelhändlern zugeschnitten ist. Die Vorlage für die Kollaboration von Managern ist ideal, um ein Team für eine Reihe von Managern zu erstellen, die über Filialen/Regionen hinweg und mehr zusammenarbeiten können. Wenn Ihre Organisation beispielsweise über Regionen verfügt, können Sie ein Kollaborationsteam für Manager für die Region Kalifornien erstellen und alle Filialleiter in dieser Region sowie den Regionalmanager für diese Region einbeziehen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Kanäle <ul><li>Vorgänge\*</li><li>Lernen\*</li></ul>\*Automatisch favorisierte Kanäle<br><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kann Kanäle erstellen/aktualisieren/löschen </li><li>Kann Apps hinzufügen/entfernen </li><li>Kann Registerkarten erstellen/aktualisieren/entfernen</li><li>Kann Konnektoren erstellen/aktualisieren/entfernen</li><ul>|
||||

Empfohlene Möglichkeiten zum Anpassen der Vorlage der Managerkollaboration für Ihre Organisation:

- Wenn Ihre Organisation über interne Websites verfügt, z. B. eine SharePoint-Website, die für Manager relevant sind, sollten Sie diese als Registerkarten in einem relevanten Teamkanal anheften. Anweisungen finden Sie in der [Dokumentation zur Microsoft Teams-Vorlage](get-started-with-teams-templates.md).

## <a name="how-to-use-first-party-templates"></a>So verwenden Sie Vorlagen von Erstanbietern

Um diese Vorlagen zu verwenden, ändern Sie die Eigenschaft 'template@odata.bind' im Anforderungshauptteil von 'standard' in die obigen TemplateIDs.  Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Die Kanäle in der Vorlage werden automatisch auf der Registerkarte Allgemein erstellt.

### <a name="example-store-template-extension-script"></a>Beispiel: Store-Vorlagenerweiterungsskripts

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a>Thema in Beziehung setzen

[Beginnen Sie mit Teams-Vorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md)