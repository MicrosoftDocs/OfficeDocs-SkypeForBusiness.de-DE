---
title: Verwenden der Inhaltssuche in Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Erfahren Sie mehr über die Verwendung der Inhaltssuche im Microsoft Purview-Complianceportal, um nach Microsoft Teams-Inhalten zu suchen, die in Exchange Online, SharePoint Online, OneDrive for Business und OneNote gespeichert sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b976c5e3c6467a6c71bb51eb1ff3ef720813584b
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808236"
---
# <a name="use-content-search-in-microsoft-teams"></a>Verwenden der Inhaltssuche in Microsoft Teams

> [!NOTE]
> Die Inhaltssuche von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [Inhaltssuche privater Kanäle](#content-search-of-private-channels).

Die Inhaltssuche bietet eine Möglichkeit zum Abfragen von Microsoft Teams-Informationen über Exchange, SharePoint Online und OneDrive for Business.

Weitere Informationen finden Sie [unter Inhaltssuche in Microsoft 365](/microsoft-365/compliance/content-search).

Beispielsweise können Sie mithilfe der **Inhaltssuche** für Ihr Manufacturing Specs-Postfach und die SharePoint-Website für Fertigungsspezifikationen nach Teams-Standardkanalunterhaltungen aus Exchange, Dateiuploads und Änderungen von SharePoint Online und OneNote-Änderungen suchen.

Sie können der **Inhaltssuche** auch Abfragekriterien hinzufügen, um die zurückgegebenen Ergebnisse einzugrenzen. Im obigen Beispiel können Sie nach Inhalten suchen, in denen die Schlüsselwörter "**Neue Werksspezifikationen"** verwendet wurden.

> [!TIP]
> Nach dem Hinzufügen von Suchbedingungen können Sie einen Bericht oder den tatsächlichen Inhalt zur Analyse auf Ihren Computer exportieren.

## <a name="content-search-of-private-channels"></a>Inhaltssuche privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt die Inhaltssuche eines einzelnen Kanals nicht, daher muss das gesamte Team durchsucht werden. Um eine Inhaltssuche eines privaten Kanals durchzuführen, durchsuchen Sie das gesamte Team, die dem privaten Kanal zugeordnete Websitesammlung (um Dateien einzuschließen) und Postfächer von Mitgliedern des privaten Kanals (um Nachrichten einzuschließen).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in Ihre Inhaltssuche einbezogen werden sollen.

### <a name="include-private-channel-files-in-a-content-search"></a>Einschließen von Dateien im privaten Kanal in eine Inhaltssuche

Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online her](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint-Websitesammlungen abzurufen, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```
2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller SharePoint-Websitesammlungs-URLs abzurufen, die privaten Kanälen im Team und der übergeordneten Teamgruppen-ID zugeordnet sind.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Führen Sie für jedes Team oder jede Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten privaten Kanalwebsites zu identifizieren.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Einschließen von Nachrichten im privaten Kanal in eine Inhaltssuche

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert haben.

1. Führen Sie die folgenden Schritte aus, um eine Liste der privaten Kanäle im Team abzurufen.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Führen Sie die folgenden Schritte aus, um eine Liste der Mitglieder des privaten Kanals abzurufen.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Schließen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil Ihrer Inhaltssuchabfrage ein.

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery-Fälle im Microsoft Purview-Complianceportal](/Office365/SecurityCompliance/ediscovery-cases)