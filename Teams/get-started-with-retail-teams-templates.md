---
title: Erste Schritte mit einer Teamvorlage im Einzelhandel
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
description: Erfahren Sie, wie Sie teamvorlagen verwenden, um Teamstrukturen für die Anforderungen des Einzelhändlers zu erstellen, indem Sie vordefinierte Einstellungen, Kanäle und vorinstallierte Apps bereitstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0193ab42a898cb8fca1e860120d663517fd0e16acd7ea2e687821b2bcd91a44
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276500"
---
# <a name="create-a-team-using-retail-team-templates"></a>Erstellen eines Teams mithilfe von Teamvorlagen für den Einzelhandel

Mit Microsoft-Teamvorlagen können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage für Einstellungen, Kanäle und vorinstallierte Apps bereitstellen.

Teamvorlagen verfügen über vordefinierte Definitionen von Teamstrukturen, die den Anforderungen des Einzelhändlers entsprechen. Mithilfe von Teamvorlagen können Sie schnell die Teamtypen erstellen, die für Einzelhändler gut funktionieren, und sie organisationsweit bereitstellen. Sie können die Teamvorlagen auch erweitern, um Teams zu erstellen, die Auf Ihre spezifischen Organisationsanforderungen zugeschnitten sind.

In diesem Artikel werden die einzelnen Teamvorlagen beschrieben und die Verwendung empfohlen.

Dieser Artikel richtet sich an Sie, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Einzelhandelsorganisation verantwortlich sind. Sie haben den Teams-Dienst bereits in Ihrer Organisation bereitgestellt. Wenn Sie Teams noch nicht eingeführt haben, lesen Sie zunächst die Anleitung zum [Einführen von Microsoft Teams](./deploy-overview.md).

Weitere allgemeine Informationen zu Teamvorlagen finden Sie unter Erste Schritte [mit Teamvorlagen.](get-started-with-teams-templates.md)

| Wer | Zu verwendende Methode: |
| ---- | --------- |
| Administratoren und IT-Spezialisten | [Verwenden Sie Teams Admin Center,](#use-the-team-templates-in-the-teams-admin-center) um Teams basierend auf den Einzelhandelsteamvorlagen zu erstellen.|
| Entwickler und Systemintegratoren | [Verwenden Sie die Microsoft Graph,](#use-the-team-templates-with-the-microsoft-graph) um Teams basierend auf den Einzelhandelsteamvorlagen zu erstellen. |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a>Verwenden der Teamvorlagen im Teams Admin Center

### <a name="organize-a-store"></a>Ein Store organisieren

Bringen Sie Ihre Einzelhandelsmitarbeiter in einer zentralen Erfahrung zusammen, um Aufgaben zu verwalten, Dokumente auszutauschen und Kundenprobleme zu lösen. Integrieren Sie zusätzliche Anwendungen, um Start- und Endprozesse von Schichten zu optimieren.

| Basisorlagentyp |baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------|-- |----------------------------------------------------- |
|Ein Store organisieren|`retailStore`|Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>Manager-Zusammenarbeit

Die Vorlage für die Zusammenarbeit von Vorgesetzten eignet sich ideal zum Erstellen eines Teams für eine Gruppe von Managern für die Zusammenarbeit in Stores/Regionen usw. Wenn Ihre Organisation beispielsweise Regionen hat, können Sie ein Team für die Zusammenarbeit vorgesetzter für die Region Kalifornien erstellen und alle Store-Manager in dieser Region zusammen mit dem Regionalmanager für diese Region umfassen.

| Basisorlagentyp| baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------|- |----------------------------------------------------- |
|Zusammenarbeit zwischen Einzelhandel und Manager|`retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Verwenden der Teamvorlagen mit dem Microsoft-Graph

### <a name="store-template"></a>Store-Vorlage

Die Store-Vorlage eignet sich ideal zum Erstellen eines Teams zur Darstellung eines einzelnen Einzelhandelsgeschäftsstandorts. Mithilfe der Store-Vorlage können Sie ein Team für jeden Einzelhandelsgeschäftsstandort in Ihrer Organisation erstellen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Kanäle <ul><li>Verschiebt die Übergabe\*</li><li>Lernen\*</li></ul>\*Automatisch favorisierte Kanäle<br><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Öffentlich gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kanäle können nicht erstellt/aktualisiert/gelöscht werden </li><li>Apps können nicht hinzugefügt/entfernt werden </li><li>Tabs können nicht erstellt/aktualisiert/entfernt werden</li><li>Konnektoren können nicht erstellt/aktualisiert/entfernt werden</li><ul>|
||||

Empfohlene Möglichkeiten zum Anpassen der Store-Vorlage für Ihre Organisation:

- Wenn Ihre Organisation Abteilungen in jedem Geschäft hat, fügen Sie für jede Abteilung einen Kanal hinzu. Das Hinzufügen eines Kanals erleichtert die Kommunikation und Zusammenarbeit innerhalb der Abteilung.

- Wenn Ihre Organisation über interne Websites verfügt (z. B. eine SharePoint-Site), sollten Sie diese als Registerkarten im entsprechenden Teamkanal anheften. Anweisungen dazu [finden Sie unter Erste Schritte mit Teamvorlagen.](get-started-with-teams-templates.md)

### <a name="manager-collaboration-template"></a>Vorlage für die Kollaboration von Managern

Die Vorlage für die Zusammenarbeit von Vorgesetzten ist eine weitere Teamvorlage, die auf die Anforderungen des Einzelhändlers ausgelegt ist. Die Vorlage für die Kollaboration von Managern ist ideal, um ein Team für eine Reihe von Managern zu erstellen, die über Filialen/Regionen hinweg und mehr zusammenarbeiten können. Wenn Ihre Organisation beispielsweise über Regionen verfügt, können Sie ein Kollaborationsteam für Manager für die Region Kalifornien erstellen und alle Filialleiter in dieser Region sowie den Regionalmanager für diese Region einbeziehen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Kanäle <ul><li>Vorgänge\*</li><li>Lernen\*</li></ul>\*Automatisch favorisierte Kanäle<br><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kann Kanäle erstellen/aktualisieren/löschen </li><li>Kann Apps hinzufügen/entfernen </li><li>Kann Registerkarten erstellen/aktualisieren/entfernen</li><li>Kann Konnektoren erstellen/aktualisieren/entfernen</li><ul>|
||||

Empfohlene Möglichkeiten zum Anpassen der Vorlage der Managerkollaboration für Ihre Organisation:

- Wenn Ihre Organisation über interne Websites verfügt, z. B. eine SharePoint-Website, die für Manager relevant sind, sollten Sie diese als Registerkarten in einem relevanten Teamkanal anheften. Anweisungen dazu finden Sie in der Dokumentation zu [Microsoft-Teamvorlagen.](get-started-with-teams-templates.md)

## <a name="how-to-use-first-party-templates"></a>So verwenden Sie Vorlagen von Erstanbietern

Um diese Vorlagen zu verwenden, ändern Sie die Eigenschaft 'template@odata.bind' im Anforderungshauptteil von 'standard' in die obigen TemplateIDs.  Weitere Informationen zum Bereitstellen von Teamvorlagen finden Sie im Microsoft Graph zum Erstellen [eines Teams.](/graph/api/team-post?view=graph-rest-beta)

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
