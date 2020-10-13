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
description: Hier erfahren Sie, wie Sie mithilfe von Teams-Vorlagen Teamstrukturen erstellen, die für Einzelhändler benötigt werden, indem Sie vordefinierte Einstellungen, Kanäle und vorinstallierte apps bereitstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424635"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Erste Schritte mit Microsoft Teams-Vorlagen im Einzelhandel

Mithilfe von Vorlagen für Teams können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.

In den Teams-Vorlagen gibt es vorgefertigte Definitionen von Teamstrukturen, die für die Anforderungen des Einzelhändlers entwickelt wurden. Mithilfe von Teams-Vorlagen können Sie schnell die Typen von Teams erstellen, die für Einzelhändler gut geeignet sind, und Sie in Ihrer Organisation bereitstellen. Sie können die Teams-Vorlagen auch erweitern, um Teams zu erstellen, die auf Ihre spezifischen organisatorischen Anforderungen zugeschnitten sind.

In diesem Artikel werden die einzelnen Teams-Vorlagen vorgestellt, und es wird empfohlen, diese zu verwenden.

Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in ihrer Einzelhandelsorganisation verantwortlich sind. Sie haben den Team-Service bereits in Ihrer Organisation bereitgestellt. Wenn Sie noch keine Teams ausgearbeitet haben, lesen Sie zunächst die [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md).

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates.md).

## <a name="store-template"></a>Store-Vorlage

Die Store-Vorlage eignet sich hervorragend zum Erstellen eines Teams zur Darstellung eines einzelnen Einzelhandels Standorts. Mithilfe der Store-Vorlage können Sie ein Team für jeden Einzelhändler Standort in Ihrer Organisation erstellen.

| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Kanäle <ul><li>Verschiebt die Übergabe\*</li><li>Lerntools\*</li></ul>\*Automatisch bevorzugte Kanäle<br><br>Team Eigenschaften <ul><li>Team Sichtbarkeit auf "öffentlich" eingestellt</li></ul> <br>Mitglieder Berechtigungen <ul><li>Kanäle können nicht erstellt/aktualisiert/gelöscht werden </li><li>Apps können nicht hinzugefügt/entfernt werden </li><li>Registerkarten können nicht erstellt/aktualisiert/entfernt werden</li><li>Connectors können nicht erstellt/aktualisiert/entfernt werden</li><ul>|
||||

Empfohlene Vorgehensweisen zum Anpassen der Store-Vorlage für Ihre Organisation:

- Wenn Ihre Organisation über Abteilungen innerhalb der einzelnen Stores verfügt, fügen Sie für jede Abteilung einen Kanal hinzu. Durch das Hinzufügen eines Kanals wird die Kommunikation und Zusammenarbeit innerhalb der Abteilung vereinfacht.

- Wenn Ihre Organisation über interne Websites verfügt (beispielsweise eine SharePoint-Website), sollten Sie Sie als Registerkarten im entsprechenden Teamkanal anheften. Anweisungen hierzu finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Manager-Zusammenarbeits Vorlage

Die Vorlage "Manager-Zusammenarbeit" ist eine weitere der Teamvorlagen, die für Einzelhändler benötigt werden. Die Vorlage "Manager-Zusammenarbeit" eignet sich hervorragend zum Erstellen eines Teams für eine Reihe von Managern, um über mehrere Geschäfte/Regionen hinweg zusammenzuarbeiten und mehr. Wenn Ihre Organisation beispielsweise Regionen hat, können Sie ein Manager-Zusammenarbeits Team für die Region Kalifornien erstellen und alle Filialmanager in dieser Region sowie den regionalen Manager für diese Region einbeziehen.

| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Kanäle <ul><li>Vorgänge\*</li><li>Lerntools\*</li></ul>\*Automatisch bevorzugte Kanäle<br><br>Team Eigenschaften <ul><li>Team Sichtbarkeit auf "Privat" gesetzt</li></ul> <br>Mitglieder Berechtigungen <ul><li>Kann Kanäle erstellen/aktualisieren/löschen </li><li>Kann apps hinzufügen/entfernen </li><li>Kann Registerkarten erstellen/aktualisieren/entfernen</li><li>Kann Connectors erstellen/aktualisieren/entfernen</li><ul>|
||||

Empfohlene Vorgehensweisen zum Anpassen der Vorlage für die Manager-Zusammenarbeit für Ihre Organisation:

- Wenn Ihre Organisation über interne Websites wie eine SharePoint-Website verfügt, die für Manager relevant sind, sollten Sie Sie in einem relevanten Teamkanal als Tabstopps anheften. Anweisungen hierzu finden Sie in der [Dokumentation zu Microsoft Teams-Vorlagen](get-started-with-teams-templates.md) .

## <a name="how-to-use-first-party-templates"></a>Verwenden von Vorlagen für Erstanbieter

Wenn Sie diese Vorlagen verwenden möchten, ändern Sie die Eigenschaft "Template@odata. Bind" im Anforderungstext von "Standard" in das obige TemplateIDs.  Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Die Kanäle in der Vorlage werden auf der RegisterkarteAllgemein automatisch erstellt.

### <a name="example-store-template-extension-script"></a>Beispiel: Vorlagen Erweiterungs Skript speichern

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
## <a name="relate-topic"></a>Thema verknüpfen

[Erste Schritte mit Microsoft Teams-Vorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
