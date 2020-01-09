---
title: Verwenden der Inhaltssuche in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: Informationen zur Inhaltssuche in Microsoft Teams und zum Suchen nach Kanal Unterhaltungen aus Exchange, Dateiuploads und Änderungen aus SharePoint und OneNote-Änderungen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fea6e671a84eec6f064a7ccc1f7f9b3f237a220d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991080"
---
<a name="use-content-search-in-microsoft-teams"></a>Verwenden der Inhaltssuche in Microsoft Teams
=====================================

> [!NOTE]
> Die Inhaltssuche von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [Inhaltssuche privater Kanäle](#content-search-of-private-channels).

Die Inhaltssuche bietet eine Möglichkeit zum Abfragen von Microsoft Teams-Informationen, die Exchange, SharePoint Online und OneDrive for Business umfassen.

Weitere Informationen finden Sie unter [Inhaltssuche in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

So können Sie beispielsweise mithilfe der **Inhaltssuche** auf der SharePoint-Website für die Produktionsspezifikationen für das Postfach und die Fertigungsspezifikationen nach Teams Standardkanal Unterhaltungen von Exchange, Dateiuploads und Änderungen aus SharePoint Online und OneNote-Änderungen suchen.

Sie können der **Inhaltssuche** auch Abfragekriterien hinzufügen, um die zurückgegebenen Ergebnisse einzuschränken. Im obigen Beispiel können Sie nach Inhalten suchen, bei denen die Schlüsselwörter "**New Factory Specs"** verwendet wurden.

> [!TIP]
> Nach dem Hinzufügen von Suchbedingungen können Sie einen Bericht oder die Daten zur Analyse auf Ihren Computer exportieren.

## <a name="content-search-of-private-channels"></a>Inhaltssuche privater Kanäle

Datensätze für Nachrichten, die in einem privaten Kanal gesendet wurden, werden an das Postfach aller privaten Kanalmitglieder und nicht an ein Gruppenpostfach übermittelt. Die Titel der Datensätze werden so formatiert, dass Sie angeben, von welchem privaten Kanal Sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützen nicht die Inhaltssuche eines einzelnen Kanals, damit das gesamte Team durchsucht werden muss. Wenn Sie eine Inhaltssuche in einem privaten Kanal durchführen möchten, suchen Sie im Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien einzubeziehen), und Postfächern privater Kanalmitglieder (zum Einbeziehen von Nachrichten).

Führen Sie die folgenden Schritte aus, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in die Inhaltssuche einbezogen werden sollen.

### <a name="include-private-channel-files-in-a-content-search"></a>Einbeziehen privater Kanaldateien in eine Inhaltssuche

Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint-Websitesammlungen abzurufen, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```
2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller URLs einer SharePoint-Websitesammlung abzurufen, die privaten Kanälen im Team zugeordnet sind, und die Gruppen-ID der übergeordneten Gruppe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Führen Sie für jede Team-oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten privaten Kanal Websites zu identifizieren.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Einbeziehen privater Kanal Nachrichten in eine Inhaltssuche

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert ist.

1. Führen Sie die folgenden Schritte aus, um eine Liste privater Kanäle im Team abzurufen.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Führen Sie die folgenden Schritte aus, um eine Liste privater Kanalmitglieder abzurufen.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil der Inhalts Suchabfrage ein.

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery-Fälle im Office 365 Security #a0 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 