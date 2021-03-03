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
description: 'Erfahren Sie, wie Sie die Inhaltssuche im Microsoft 365 Compliance Center verwenden, um nach Microsoft #A0 zu suchen, die in Exchange Online, SharePoint Online, OneDrive for Business und OneNote gespeichert sind.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980439"
---
<a name="use-content-search-in-microsoft-teams"></a>Verwenden der Inhaltssuche in Microsoft Teams
=====================================

> [!NOTE]
> Die Inhaltssuche von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter ["Inhaltssuche privater Kanäle".](#content-search-of-private-channels)

Die Inhaltssuche bietet eine Möglichkeit zum Abfragen von Microsoft #A0 über Exchange, SharePoint Online und OneDrive for Business.

Weitere Informationen finden Sie unter ["Inhaltssuche" in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search)

Wenn Sie  z. B. die Inhaltssuche für Ihr Postfach für Fertigungsspezifikationen und die SharePoint-Website mit Fertigungsspezifikationen verwenden, können Sie nach standardmäßigen Kanalunterhaltungen in Teams von Exchange, Dateiuploads und Änderungen von SharePoint Online und OneNote-Änderungen suchen.

Sie können der Inhaltssuche auch Abfragekriterien hinzufügen, **um** die zurückgegebenen Ergebnisse zu einenten. Im vorstehenden Beispiel können Sie nach Inhalten suchen, in denen die Schlüsselwörter **"New Factory Specs"** verwendet wurden.

> [!TIP]
> Nachdem Sie Suchbedingungen hinzugefügt haben, können Sie einen Bericht oder den tatsächlichen Inhalt zur Analyse auf Ihren Computer exportieren.

## <a name="content-search-of-private-channels"></a>Inhaltssuche privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine Inhaltssuche in einem einzigen Kanal, daher muss das gesamte Team durchsucht werden. Wenn Sie eine Inhaltssuche in einem privaten Kanal durchführen möchten, suchen Sie im gesamten Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien mit zu umfassen), und nach Postfächern von Mitgliedern des privaten Kanals (um Nachrichten mit zu umfassen).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in Ihre Inhaltssuche mit einbegriffen werden sollen.

### <a name="include-private-channel-files-in-a-content-search"></a>Schließen Sie private Kanaldateien in eine Inhaltssuche ein

Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online herzustellen.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Führen Sie Folgendes aus, um eine Liste aller SharePoint-Websitesammlungen zu erhalten, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```
2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller SHAREPoint-Websitesammlungs-URLs, die privaten Kanälen im Team zugeordnet sind, und die ID der übergeordneten Teamgruppe zu erhalten.

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

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie die neueste Version des [Teams -PowerShell-Moduls installiert](teams-powershell-overview.md) haben.

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

- [eDiscovery-Fälle im Microsoft 365 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 