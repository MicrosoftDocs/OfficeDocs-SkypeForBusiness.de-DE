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
- m365-frontline
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
ms.openlocfilehash: d8c6af4cc86051c9233e06d0bf6c67abe1a4ad39
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837335"
---
# <a name="use-retail-team-templates"></a>Verwenden von Teamvorlagen für den Einzelhandel

## <a name="overview"></a>Übersicht

Mit Teamvorlagen in Microsoft Teams können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Teamstruktur aus Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für Einzelhändler können Teamvorlagen besonders nützlich sein, da sie Ihnen helfen, einheitliche Teams in der gesamten Organisation schnell bereitzustellen. Vorlagen helfen den Mitarbeitern auch, sich bei der effektiven Verwendung von Microsoft Teams zu orientieren.

Microsoft Teams bietet speziell für die Bedürfnisse des Einzelhandels konzipierte Vorlagen. Verwenden Sie diese vorgefertigten Vorlagen, um schnell Teams zu erstellen, mit denen Mitarbeiter kommunizieren und zusammenarbeiten können. In diesem Artikel stellen wir Ihnen jede dieser Vorlagen vor und empfehlen deren Verwendung.

Wie Sie Teamvorlagen verwalten und damit arbeiten, hängt davon ab, ob Sie Administrator oder Entwickler sind.

|Wenn Sie: | Dann: |
| ---- | --------- |
| Ein Administrator oder IT-Profi |[Verwalten Sie Teamvorlagen im Teams Admin Center](#manage-team-templates-in-the-teams-admin-center). Zeigen Sie Teamvorlagen an und wenden Sie Vorlagenrichtlinien an, um zu steuern, welche Vorlagen Ihre Mitarbeiter in Teams zum Erstellen von Teams verwenden können. |
| Ein Entwickler | [Verwenden Sie Microsoft Graph](#use-team-templates-with-microsoft-graph), um Teams aus Teamvorlagen zu erstellen. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Teams Admin Center

Als Administrator können Sie Teamvorlagen im Microsoft Teams Admin Center verwalten. Hier können Sie Details zu jeder Vorlage anzeigen. Sie können Ihren Mitarbeitern auch [Vorlagenrichtlinien erstellen und zuweisen](templates-policies.md), um zu steuern, welche Vorlagen sie in Teams zum [Erstellen von Teams](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) sehen.

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md).

Derzeit sind die folgenden vordefinierten Teamvorlagen für den Einzelhandel verfügbar. Um sie anzuzeigen, wechseln Sie in der linken Navigation im Microsoft Teams Admin Center zu **Teams** > **Teamvorlagen**.

> [!NOTE]
> Ein Sternchen (*) gibt an, dass es sich bei der Vorlage um eine *mit Microsoft 365 verbundene Vorlage* handelt. Wenn Benutzer ein Team mithilfe der Vorlage erstellen, wird die verbundene SharePoint-Vorlage auf die Website und das Team angewendet. SharePoint-Komponenten wie Seiten, Listen und Power Platform-Integrationen werden automatisch als Registerkarten zum Kanal "Allgemein" im Team hinzugefügt und angeheftet. Benutzer können diese Seiten und Listen direkt in Teams bearbeiten.
>
> Weitere Informationen zu SharePoint-Vorlagen finden Sie [unter Anwenden und Anpassen von SharePoint-Websitevorlagen](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Verwalten eines Stores*

Bringen Sie Ihre Einzelhandelsmitarbeiter in einer zentralen Erfahrung zusammen, an dem sie Aufgaben verwalten, Dokumente freigeben und Kundenprobleme lösen können. Integrieren Sie zusätzliche Anwendungen, um Schichtanfangs- und -endprozesse zu optimieren.

> [!div class="mx-tdBreakAll"]
>| Vorlagentyp |TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
>| ------------------|-- |----------------------------------------------------- |
>| Verwalten eines Stores| `retailStore` |Kanäle: <ul><li>Allgemein<li>Übergabe umschalten</li><li>Store-Bereitschaft</li><li>Learning</li></ul> Apps: <ul><li>Genehmigungen</li><li>Prüfung</li><li>Listen<ul><li>Bestandsliste</li></ul></li><li>SharePoint-Seiten<ul><li>Unser Store</li></ul></li><li>Schichten</li><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>Einzelhandel für Manager*

Erstellen Sie ein Team für eine Gruppe von Managern für die Zusammenarbeit zwischen Geschäften oder Regionen. Wenn Ihre Organisation beispielsweise Regionen hat, können Sie ein Team für die Region Kalifornien erstellen und alle Store-Manager in dieser Region zusammen mit dem Regionalmanager für diese Region einbeziehen.

> [!div class="mx-tdBreakAll"]
>| Vorlagentyp| TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
>| ------------------|- |----------------------------------------------------- |
>| Einzelhandel für Manager| `retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Genehmigungen</li><li>Prüfung</li><li>SharePoint-Seiten<ul><li>Unser Store</li></ul></li><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Verwenden Sie Teamvorlagen mit Microsoft Graph

Weitere Informationen zur Verwendung von Teamvorlagen mit Microsoft Graph finden Sie unter [Erste Schritte mit Teamvorlagen mit Microsoft Graph](get-started-with-teams-templates.md), [Übersicht über die Microsoft Teams-API](/graph/teams-concept-overview?view=graph-rest-1.0), und [teamsTemplate-Ressourcentyp](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Hier finden Sie die vorgefertigten Teamvorlagen für den Einzelhandel.

> [!NOTE]
> Ein Sternchen (*) gibt an, dass es sich bei der Vorlage um eine *mit Microsoft 365 verbundene Vorlage* handelt. Wenn Benutzer ein Team mithilfe der Vorlage erstellen, wird die verbundene SharePoint-Vorlage auf die Website und das Team angewendet. SharePoint-Komponenten wie Seiten, Listen und Power Platform-Integrationen werden automatisch als Registerkarten zum Kanal "Allgemein" im Team hinzugefügt und angeheftet. Benutzer können diese Seiten und Listen direkt in Teams bearbeiten.
>
> Weitere Informationen zu SharePoint-Vorlagen finden Sie [unter Anwenden und Anpassen von SharePoint-Websitevorlagen](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Verwalten eines Stores*

Verwenden Sie diese Vorlage, um ein Team für jeden Einzelhandelsspeicherort in Ihrer Organisation zu erstellen.

> [!div class="mx-tdBreakAll"]
>| Vorlagentyp | TemplateId | Vorlagenkanäle |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Einzelhandel -  <br>Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Kanäle <ul><li>Allgemein</li><li>Übergabe umschalten</li><li>Store-Bereitschaft</li><li>Learning</li></ul>Teameigenschaften <ul><li>Teamsichtbarkeit auf Öffentlich gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kanäle können nicht erstellt, aktualisiert oder gelöscht werden </li><li>Apps können nicht hinzugefügt oder entfernt werden </li><li>Registerkarten können nicht erstellt, aktualisiert oder entfernt werden</li><li>Connectors können nicht erstellt, aktualisiert oder entfernt werden</li><ul>|

Empfohlene Möglichkeiten zum Anpassen der Store-Vorlage für Ihre Organisation:

- Wenn Ihre Organisation Abteilungen in jedem Geschäft hat, fügen Sie für jede Abteilung einen Kanal hinzu. Das Hinzufügen eines Kanals erleichtert die Kommunikation und Zusammenarbeit innerhalb der Abteilung.

- Wenn Ihre Organisation über interne Websites verfügt (z. B. eine SharePoint-Site), sollten Sie diese als Registerkarten im entsprechenden Teamkanal anheften.

### <a name="retail-for-managers"></a>Einzelhandel für Manager*

Verwenden Sie diese Vorlage, um ein Team für eine Gruppe von Managern für die Zusammenarbeit zwischen Geschäften oder Regionen zu erstellen. Wenn Ihre Organisation beispielsweise Regionen hat, können Sie ein Team für die Region Kalifornien erstellen und alle Store-Manager in dieser Region zusammen mit dem Regionalmanager für diese Region einbeziehen.

> [!div class="mx-tdBreakAll"]
>| Vorlagentyp | TemplateId | Vorlagenkanäle |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Einzelhandel -  <br>Zusammenarbeit leitender Angestellter | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| Kanäle <ul><li>Allgemein</li><li>Vorgänge</li><li>Lernen</li></ul>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> <br>Mitgliedsberechtigungen <ul><li>Kanäle können erstellt, aktualisiert oder gelöscht werden </li><li>Apps können hinzugefügt oder entfernt werden </li><li>Registerkarten können erstellt, aktualisiert oder entfernt werden</li><li>Connectors können erstellt, aktualisiert oder entfernt werden</li><ul>|

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

> [!NOTE]
> Wenn Sie Microsoft Graph verwenden, um ein Team aus einer vorhandenen Microsoft 365-Gruppe oder einem vorhandenen Team mithilfe einer mit Microsoft 365 verbundenen Vorlage zu erstellen, wird die verbundene SharePoint-Vorlage nicht automatisch auf die Website oder das Team angewendet. Sie müssen die SharePoint-Websitevorlage manuell anwenden, nachdem das Team erstellt wurde. Wechseln Sie in Teams zum Team, wählen Sie in der oberen rechten Ecke weitere **Optionen** aus, > **In SharePoint öffnen**. Wählen Sie dann **"Einstellungen** > **" aus, um eine Websitevorlage anzuwenden** , und wählen Sie die entsprechende Websitevorlage aus.

## <a name="related-articles"></a>Verwandte Artikel

- [Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen eines Teams aus einer Vorlage](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Erste Schritte mit Teamvorlagen mittels Microsoft Graph](get-started-with-teams-templates.md)