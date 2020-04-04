---
title: Durchführen einer eDiscovery-Untersuchung von Inhalten
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie vorgehen müssen, wenn Sie eine eDiscovery durchführen müssen, beispielsweise wenn Sie alle elektronisch gespeicherten Informationen für gerichtliche Verfahren übermitteln müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136685"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen sind häufig hohen strafrechtlichen Verfahren ausgesetzt, die die Übermittlung aller elektronisch gespeicherten Informationen (ESI) fordern.

Alle Teams 1:1-oder Gruppen-Chats werden über die Postfächer der jeweiligen Benutzer in Journalen durchlaufen, und alle standardmäßigen Kanal Nachrichten werden in das Gruppenpostfach, das das Team darstellt, in Journalen gespeichert. Dateien, die in Standardkanälen hochgeladen werden, werden von der eDiscovery-Funktion für SharePoint Online und OneDrive for Business abgedeckt. eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle](#ediscovery-of-private-channels).

> [!NOTE]
> Derzeit unterstützen wir keine eDiscovery-Chatnachrichten in Szenarien, in denen Gastbenutzer die einzigen Teilnehmer an einem 1:1-oder 1: N-Chat sind. Diese Arten von Chats werden auch als *Gast-zu-Gast* -Chats bezeichnet, da Sie keine Home-Tenant-Nutzer sind.

1. Wenn Sie eine eDiscovery-Untersuchung mit Microsoft Teams-Inhalten durchführen möchten, lesen Sie Schritt 1 in [diesem](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) Link.

2. Microsoft Teams-Daten werden als Chatnachrichten oder Unterhaltungen in der Excel-eDiscovery-Exportausgabe angezeigt, und Sie können die PST-Datei in Outlook öffnen, um diese Nachrichten nach dem Export anzuzeigen.

    Beachten Sie beim Anzeigen der PST-Datei für das Team, dass alle Unterhaltungen im Team-Chat-Ordner unter "Konversations Verlauf" aufbewahrt werden. Der Titel der Nachricht wird an Team und Kanal ausgerichtet. Wenn Sie das Bild unten überprüfen, können Sie diese Nachricht von Bob sehen, der den Project 7-Standardkanal des Teams "Manufacturing Specs" gesendet hat.

    ![Screenshot eines Team-Chat-Ordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. Um private Chats im Postfach eines Benutzers anzuzeigen, befinden Sie sich auch im Ordner "Team-Chat" unter "Konversationsprotokoll".

## <a name="ediscovery-of-private-channels"></a>eDiscovery privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine eDiscovery eines einzelnen Kanals, sodass das gesamte Team durchsucht werden muss. Wenn Sie eine eDiscovery-Suche nach Inhalten in einem privaten Kanal durchführen möchten, suchen Sie im Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien einzubeziehen), und Postfächern privater Kanalmitglieder (zum Einbeziehen von Nachrichten).

Führen Sie die folgenden Schritte aus, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die Sie in Ihre eDiscovery-Suche einbeziehen möchten.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Einbeziehen privater Kanaldateien in eine eDiscovery-Suche

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

3. Führen Sie für jede Team-oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten privaten Kanal Websites zu identifizieren, wobei $GroupID die Gruppen-ID des Teams ist.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Einbeziehen privater Kanal Nachrichten in eine eDiscovery-Suche

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert ist.

1. Führen Sie die folgenden Schritte aus, um eine Liste privater Kanäle im Team abzurufen.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Führen Sie die folgenden Schritte aus, um eine Liste privater Kanalmitglieder abzurufen.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil ihrer eDiscovery-Suchabfrage ein.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
