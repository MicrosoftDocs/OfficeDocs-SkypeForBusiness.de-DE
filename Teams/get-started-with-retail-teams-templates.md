---
title: Verwenden von Teamvorlagen für den Einzelhandel
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie, wie Sie die Teamvorlagen für den Einzelhandel im Microsoft Teams Admin Center und mit Microsoft Graph verwalten und verwenden können, um schnell und einfach Teams für Ihre Einzelhandelsorganisation zu erstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c2bda6467bf819bdf9cf82713c24e8e9cd18d9d
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007795"
---
# <a name="use-retail-team-templates"></a>Verwenden von Teamvorlagen für den Einzelhandel

Mit Teamvorlagen in Microsoft Teams können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Teamstruktur aus Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für Einzelhändler können Teamvorlagen besonders nützlich sein, da sie Ihnen helfen, einheitliche Teams in der gesamten Organisation schnell bereitzustellen. Vorlagen helfen den Mitarbeitern auch, sich bei der effektiven Verwendung von Microsoft Teams zu orientieren.

Microsoft Teams bietet speziell für die Bedürfnisse des Einzelhandels konzipierte Vorlagen. Verwenden Sie diese vorgefertigten Vorlagen, um schnell Teams zu erstellen, mit denen Mitarbeiter kommunizieren und zusammenarbeiten können. In diesem Artikel stellen wir Ihnen jede dieser Vorlagen vor und empfehlen deren Verwendung.

Wie Sie Teamvorlagen verwalten und damit arbeiten, hängt davon ab, ob Sie Administrator oder Entwickler sind.

|Wenn Sie: | Dann: |
| ---- | --------- |
| Ein Administrator oder IT-Profi |[Verwalten Sie Teamvorlagen im Teams Admin Center](#manage-team-templates-in-the-teams-admin-center). Zeigen Sie Teamvorlagen an und wenden Sie Vorlagenrichtlinien an, um zu steuern, welche Vorlagen Ihre Mitarbeiter in Teams zum Erstellen von Teams verwenden können. |
| Ein Entwickler | [Verwenden Sie Microsoft Graph](#use-team-templates-with-microsoft-graph), um Teams aus Teamvorlagen zu erstellen. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Teams Admin Center

Als Administrator können Sie Teamvorlagen im Microsoft Teams Admin Center verwalten. Hier können Sie Details zu jeder Vorlage anzeigen. Sie können Ihren Mitarbeitern auch [Vorlagenrichtlinien erstellen und zuweisen](templates-policies.md), um zu steuern, welche Vorlagen sie in Teams zum [Erstellen von Teams](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) sehen. 

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md).

Derzeit sind die folgenden vordefinierten Teamvorlagen für den Einzelhandel verfügbar. Um sie anzuzeigen, wechseln Sie in der linken Navigation im Microsoft Teams Admin Center zu **Teams** > **Teamvorlagen**.

### <a name="organize-a-store"></a>Organisieren Sie eine Filiale

Bringen Sie Ihre Einzelhandelsmitarbeiter in einer zentralen Erfahrung zusammen, an dem sie Aufgaben verwalten, Dokumente freigeben und Kundenprobleme lösen können. Integrieren Sie zusätzliche Apps für die Optimierung von Schichtabläufen.

| Vorlagentyp |TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------|-- |----------------------------------------------------- |
|Ein Store organisieren| `retailStore` |Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Bereitschaft der Filiale<ul><li>Prüfung&sup1;</li></ul></li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li><li>Schichten</li><li>Prüfung</li></ul>|

&sup1;App wurde dem Kanal als Registerkarte hinzugefügt

### <a name="manager-collaboration"></a>Zusammenarbeit leitender Angestellter

Die Vorlage für die Zusammenarbeit leitender Angestellter ist ideal, um ein Team für eine Gruppe von Managern zu erstellen, die über Filialen, Regionen usw. hinweg zusammenarbeiten.. Wenn Ihre Organisation beispielsweise in verschiedenen Ländern tätig ist, können Sie ein solches Team für die Region Kalifornien erstellen, und alle Filialleiter in dieser Region sowie den Regionalmanager für diese Region einbeziehen.

| Vorlagentyp| TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------|- |----------------------------------------------------- |
|Einzelhandel für leitende Angestellte|`retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge<ul><li>Aufgaben (Operative Aufgaben)&sup1;</li><li>Prüfung&sup1;</li></ul></li><li>Learning<ul><li>Aufgaben (Learning-Aufgaben)&sup1;</li></ul></li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li><li>Prüfung</li></ul>|
||||

&sup1;App wurde dem Kanal als Registerkarte hinzugefügt

## <a name="use-team-templates-with-microsoft-graph"></a>Verwenden Sie Teamvorlagen mit Microsoft Graph

Entwickler können Microsoft Graph verwenden, um Teams aus vorgefertigten Teamvorlagen zu erstellen. Weitere Informationen zur Verwendung von Teamvorlagen mit Microsoft Graph finden Sie unter [Erste Schritte mit Teamvorlagen mit Microsoft Graph](get-started-with-teams-templates.md), [Übersicht über die Microsoft Teams-API](/graph/teams-concept-overview?view=graph-rest-1.0), und [teamsTemplate-Ressourcentyp](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Hier finden Sie die vorgefertigten Teamvorlagen für den Einzelhandel.

### <a name="store"></a>Filiale

Die Store-Vorlage eignet sich ideal zum Erstellen eines Teams zur Darstellung eines einzelnen Einzelhandelsgeschäftsstandorts. Mithilfe der Store-Vorlage können Sie ein Team für jeden Einzelhandelsgeschäftsstandort in Ihrer Organisation erstellen.

| Vorlagentyp | TemplateId | Vorlagenkanäle |
| ------------------ | -------------- | ----------------------------------------------------- |
| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Kanäle <ul><li>Allgemein</li><li>Schichtübergabe&sup2;</li><li>Bereitschaft der Filiale</li><li>Learning&sup2;</li></ul>Teameigenschaften <ul><li>Teamsichtbarkeit auf Öffentlich gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kanäle können nicht erstellt, aktualisiert oder gelöscht werden </li><li>Apps können nicht hinzugefügt oder entfernt werden </li><li>Registerkarten können nicht erstellt, aktualisiert oder entfernt werden</li><li>Connectors können nicht erstellt, aktualisiert oder entfernt werden</li><ul>|
||||

&sup2;Automatisch als Favoriten festgelegte Kanäle

Empfohlene Möglichkeiten zum Anpassen der Store-Vorlage für Ihre Organisation:

- Wenn Ihre Organisation Abteilungen in jedem Geschäft hat, fügen Sie für jede Abteilung einen Kanal hinzu. Das Hinzufügen eines Kanals erleichtert die Kommunikation und Zusammenarbeit innerhalb der Abteilung.

- Wenn Ihre Organisation über interne Websites verfügt (z. B. eine SharePoint-Site), sollten Sie diese als Registerkarten im entsprechenden Teamkanal anheften.

### <a name="manager-collaboration"></a>Zusammenarbeit leitender Angestellter

Die Vorlage für die Zusammenarbeit leitender Angestellter ist ideal, um ein Team für eine Gruppe von Managern zu erstellen, die über Filialen, Regionen usw. hinweg zusammenarbeiten.. Wenn Ihre Organisation beispielsweise in verschiedenen Ländern tätig ist, können Sie ein solches Team für die Region Kalifornien erstellen, und alle Filialleiter in dieser Region sowie den Regionalmanager für diese Region einbeziehen.

| Vorlagentyp | TemplateId | Vorlagenkanäle |
| ------------------ | -------------- | ----------------------------------------------------- |
| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Kanäle <ul><li>Allgemein</li><li>Vorgänge&sup2;</li><li>Learning&sup2;</li></ul>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kanäle können erstellt, aktualisiert oder gelöscht werden </li><li>Apps können hinzugefügt oder entfernt werden </li><li>Registerkarten können erstellt, aktualisiert oder entfernt werden</li><li>Connectors können erstellt, aktualisiert oder entfernt werden</li><ul>|
||||

&sup2;Automatisch als Favoriten festgelegte Kanäle

Empfohlene Möglichkeiten zum Anpassen der Vorlage der Managerkollaboration für Ihre Organisation:

- Wenn Ihre Organisation über interne Websites verfügt, z. B. eine SharePoint-Website, die für Manager relevant sind, sollten Sie diese als Registerkarten in einem relevanten Teamkanal anheften.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>So verwenden Sie Teamvorlagen mit Microsoft Graph

Um diese Vorlagen zu verwenden, ändern Sie die Eigenschaft „template@odata.bind“ im Anforderungstext von „standard“' in die obigen Vorlagen-IDs.  Weitere Informationen zur Bereitstellung von Teamvorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Die Kanäle in der Vorlage werden automatisch auf der Registerkarte **Allgemein** erstellt.

### <a name="example-store-template-extension-script"></a>Beispiel: Skript zur Erweiterung der Vorlage für die Filiale

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

## <a name="related-articles"></a>Verwandte Artikel

- [Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen eines Teams aus einer Vorlage in der Microsoft Teams-App](https://support.microsoft.com/en-us/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [Erste Schritte mit Teamvorlagen mittels Microsoft Graph](get-started-with-teams-templates.md)