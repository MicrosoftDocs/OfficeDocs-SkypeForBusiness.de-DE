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
description: Erfahren Sie, wie Sie die Inhaltssuche im Microsoft 365 Compliance Center verwenden, um nach Microsoft Teams-Inhalten zu suchen, die in Exchange Online, SharePoint Online, OneDrive for Business und OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6810355304371564a2a305c82290df7667f5efd41889e598021636cc9ccd11d4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278213"
---
# <a name="use-content-search-in-microsoft-teams"></a>Verwenden der Inhaltssuche in Microsoft Teams

> [!NOTE]
> Die Inhaltssuche von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [Inhaltssuche privater Kanäle.](#content-search-of-private-channels)

Die Inhaltssuche bietet eine Möglichkeit zum Microsoft Teams von Informationen über Exchange, SharePoint Online und OneDrive for Business.

Weitere Informationen finden Sie unter [Inhaltssuche in Microsoft 365.](/microsoft-365/compliance/content-search)

Wenn Sie  z. B. die Inhaltssuche für Ihr Postfach für Fertigungsspezifikationen und die Fertigungsspezifikationen SharePoint-Website verwenden, können Sie nach Teams-Standardkanalunterhaltungen aus Exchange, Dateiuploads und Änderungen von SharePoint Online suchen und OneNote ändern.

Sie können der Inhaltssuche auch Abfragekriterien hinzufügen, **um** die zurückgegebenen Ergebnisse zu eindingen. Im vorstehenden Beispiel können Sie nach Inhalten suchen, bei denen die Schlüsselwörter **"Neue Werksspezifikationen"** verwendet wurden.

> [!TIP]
> Nachdem Sie Suchbedingungen hinzugefügt haben, können Sie einen Bericht oder den eigentlichen Inhalt zur Analyse auf Ihren Computer exportieren.

## <a name="content-search-of-private-channels"></a>Inhaltssuche privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine Inhaltssuche in einem einzigen Kanal, daher muss das gesamte Team durchsucht werden. Um eine Inhaltssuche für einen privaten Kanal durchzuführen, durchsuchen Sie das gesamte Team, die dem privaten Kanal zugeordnete Websitesammlung (um Dateien zu enthalten) und Postfächer von Mitgliedern des privaten Kanals (um Nachrichten mit zu verwenden).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die sie in Ihre Inhaltssuche mit einbegriffen sollen.

### <a name="include-private-channel-files-in-a-content-search"></a>Schließen Sie Dateien privater Kanäle in eine Inhaltssuche ein.

Bevor Sie diese Schritte ausführen, installieren Sie die SharePoint Online-Verwaltungsshell, und stellen Sie [eine Verbindung mit SharePoint Online herzustellen.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint, die privaten Kanälen im Team zugeordnet sind, zu erhalten.

    ```PowerShell
    Get-SPOSite
    ```
2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller SharePoint-Websitesammlungs-URLs zu erhalten, die privaten Kanälen im Team und der ID der übergeordneten Teamgruppe zugeordnet sind.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Führen Sie für jede Team- oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten Websites privater Kanäle zu identifizieren.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Schließen Sie Nachrichten privater Kanäle in eine Inhaltssuche ein

Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie die neueste Version des Teams [PowerShell-Moduls installiert](teams-powershell-overview.md) haben.

1. Führen Sie die folgenden Schritte aus, um eine Liste der privaten Kanäle im Team zu erhalten.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Führen Sie die folgenden Schritte aus, um eine Liste der Mitglieder privater Kanäle zu erhalten.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil Ihrer Inhaltssuchabfrage ein.

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery-Fälle im Microsoft 365 Compliance Center](/Office365/SecurityCompliance/ediscovery-cases)