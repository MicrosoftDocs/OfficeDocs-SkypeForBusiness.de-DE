---
title: Verwenden der Inhaltssuche in Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Erfahren Sie mehr über die Verwendung der Inhaltssuche im Microsoft 365 Compliance Center, um nach Microsoft Teams-Inhalten zu suchen, die in Exchange Online, SharePoint Online, OneDrive for Business und OneNote gespeichert sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3758f96dc4755303ce8ccf3cae4443deb2a5cd99
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094285"
---
<a name="use-content-search-in-microsoft-teams"></a>Verwenden der Inhaltssuche in Microsoft Teams
=====================================

> [!NOTE]
> Die Inhaltssuche von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [Inhaltssuche privater Kanäle.](#content-search-of-private-channels)

Die Inhaltssuche bietet eine Möglichkeit zum Abfragen von Microsoft Teams-Informationen über Exchange, SharePoint Online und OneDrive for Business.

Weitere Informationen finden Sie unter [Inhaltssuche in Microsoft 365.](/microsoft-365/compliance/content-search)

Wenn Sie  beispielsweise die Inhaltssuche für Ihr Postfach für Fertigungsspezifikationen und die SharePoint-Website "Fertigungsspezifikationen" verwenden, können Sie nach Standardkanalunterhaltungen von Teams aus Exchange, Dateiuploads und -änderungen aus SharePoint Online und OneNote-Änderungen suchen.

Sie können der Inhaltssuche auch Abfragekriterien hinzufügen, **um** die zurückgegebenen Ergebnisse zu einengt. Im vorstehenden Beispiel können Sie nach Inhalten suchen, in denen die Schlüsselwörter **"Neue Werksspezifikationen"** verwendet wurden.

> [!TIP]
> Nachdem Sie Suchbedingungen hinzugefügt haben, können Sie einen Bericht oder den tatsächlichen Inhalt zur Analyse auf Ihren Computer exportieren.

## <a name="content-search-of-private-channels"></a>Inhaltssuche privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine Inhaltssuche in einem einzigen Kanal, daher muss das gesamte Team durchsucht werden. Um eine Inhaltssuche eines privaten Kanals durchzuführen, durchsuchen Sie das gesamte Team, die websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien zu enthalten), und Postfächer von Mitgliedern des privaten Kanals (um Nachrichten zu enthalten).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in Ihre Inhaltssuche mit ein-/ausgg.

### <a name="include-private-channel-files-in-a-content-search"></a>Schließen Sie Dateien des privaten Kanals in eine Inhaltssuche ein

Installieren Sie vor dem Ausführen dieser Schritte die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online ein.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Führen Sie folgendes aus, um eine Liste aller SharePoint-Websitesammlungen zu erhalten, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```
2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller URLs der SharePoint-Websitesammlung zu erhalten, die privaten Kanälen im Team und der übergeordneten Teamgruppen-ID zugeordnet sind.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Führen Sie für jedes Team oder jede Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten Websites des privaten Kanals zu identifizieren.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Schließen Sie Nachrichten des privaten Kanals in eine Inhaltssuche ein.

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Die neueste Version des [Teams PowerShell-Moduls installiert](teams-powershell-overview.md) ist.

1. Führen Sie die folgenden Schritte aus, um eine Liste der privaten Kanäle im Team zu erhalten.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Führen Sie folgendes aus, um eine Liste der Mitglieder des privaten Kanals zu erhalten.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil Ihrer Inhaltssuchabfrage ein.

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery-Fälle im Microsoft 365 Compliance Center](/Office365/SecurityCompliance/ediscovery-cases)