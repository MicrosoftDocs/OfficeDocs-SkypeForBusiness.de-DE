---
title: Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, was Sie tun müssen, wenn Sie eine eDiscovery durchführen, zum Beispiel, wenn Sie alle elektronisch gespeicherten Informationen für Gerichtsverfahren eingereicht müssen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461804"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="c8bcb-103">Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8bcb-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="c8bcb-104">Große Unternehmen werden häufig für hohe beeinträchtigt gerichtlichen verfügbar gemacht, die Übermittlung von allen auf elektronischem Wege gespeicherten Informationen (ESI) gefordert wird.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="c8bcb-p101">Alle Teams 1:1 oder Gruppe Chats sind bis auf die Postfächer der jeweiligen Benutzer im Journal erfasst, und alle Channel-Nachrichten werden im Journal erfasst über die Gruppe Postfach, das Team darstellt. Dateien, die hochgeladen werden unter eDiscovery-Funktionalität für SharePoint Online und OneDrive für Unternehmen behandelt.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="c8bcb-107">Zum abhalten von Ermittlungen eDiscovery mit Microsoft-Teams, Inhalt, überprüfen Sie Schritt 1 in [dieser](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) Verknüpfung.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="c8bcb-108">Microsoft-Teams, Daten als Sofortnachrichten angezeigt oder Unterhaltungen in der eDiscovery Excel exportieren Ausgabe und können Sie Bereitstellen der. PST-Datei in Outlook können Sie diese Nachrichten anzeigen buchen exportieren.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="c8bcb-109">Beim Bereitstellen der. PST-Datei für das Team, Notiz, die alle Unterhaltungen Team Chat unter im Ordner Unterhaltungsverlauf gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="c8bcb-110">Der Titel der Nachricht Ausrichtung Teams und der Kanal.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="c8bcb-111">Von der Überprüfung der folgenden Abbilds, können Sie diese Meldung von Bob anzeigen, die den Project-7-Kanal des Teams Manufacturing Spezifikationsdialogfeld-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Screenshot von einem Team Chat Ordner im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="c8bcb-113">Wenn Sie private Chats in einem Benutzerpostfach sehen möchten – diese befinden sich ebenfalls im Ordner „Teamchat“ unter „Aufgezeichnete Unterhaltungen“.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="c8bcb-114">eDiscovery Gast-Gast-Chats</span><span class="sxs-lookup"><span data-stu-id="c8bcb-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="c8bcb-115">Ohne ein Postfach Gast-Gast-chats (1xN Chats, in denen keine private Mandanten Benutzer vorhanden sind) nicht indiziert und wird daher nicht in eDiscovery enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="c8bcb-116">Um eDiscovery für Gast-Gast-Chats zu erleichtern, wird eine cloudbasierte Postfach (oder phantom Postfach) zum Speichern der Daten 1xN erstellt.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="c8bcb-117">Nachdem die Teams chatdaten in der Cloud-basierte Postfach gespeichert ist, wird es für eDiscovery und Compliance Inhaltssuche indiziert.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="c8bcb-118">Die folgende Abbildung veranschaulicht die Funktionsweise von eDiscovery für Gast-Gast-Chats in dem es ist nicht auf ein Postfach.</span><span class="sxs-lookup"><span data-stu-id="c8bcb-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Guest-to-guest-Chats-with-No-Mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
