---
title: Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, was Sie tun müssen, wenn Sie eine eDiscovery durchführen, zum Beispiel, wenn Sie alle elektronisch gespeicherten Informationen für Gerichtsverfahren eingereicht müssen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564032"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="5e720-103">Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e720-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="5e720-104">Große Unternehmen sind häufig hohen strafrechtlichen Verfahren ausgesetzt, die die Übermittlung aller elektronisch gespeicherten Informationen (ESI) fordern.</span><span class="sxs-lookup"><span data-stu-id="5e720-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="5e720-p101">Alle Teams 1:1-oder Gruppen-Chats werden über die Postfächer der jeweiligen Benutzer in Journalen durchlaufen, und alle Kanal Nachrichten werden in das Gruppenpostfach, das das Team darstellt, in Journalen gespeichert. Hochgeladene Dateien werden unter der eDiscovery-Funktion für SharePoint Online und OneDrive for Business behandelt.</span><span class="sxs-lookup"><span data-stu-id="5e720-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="5e720-107">Wenn Sie eine eDiscovery-Untersuchung mit Microsoft Teams-Inhalten durchführen möchten, lesen Sie Schritt 1 in [diesem](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) Link.</span><span class="sxs-lookup"><span data-stu-id="5e720-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="5e720-108">Microsoft Teams-Daten werden als Chatnachrichten oder Unterhaltungen in der Excel-eDiscovery-Exportausgabe angezeigt, und Sie können das bereitstellen. PST in Outlook, um diese Nachrichten nach dem Export anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e720-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="5e720-p102">Beim montieren des. PST für das Team beachten Sie, dass alle Unterhaltungen im Teamchat-Ordner unter Konversationsprotokoll gespeichert werden. Der Titel der Nachricht wird an Team und Kanal ausgerichtet. Wenn Sie das Bild unten überprüfen, können Sie diese Nachricht von Bob sehen, der den Project 7-Kanal des Teams "Manufacturing Specs" gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="5e720-p102">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History. The title of the message aligns to Team and Channel. From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Screenshot eines Team-Chat-Ordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="5e720-113">Wenn Sie private Chats in einem Benutzerpostfach sehen möchten – diese befinden sich ebenfalls im Ordner „Teamchat“ unter „Aufgezeichnete Unterhaltungen“.</span><span class="sxs-lookup"><span data-stu-id="5e720-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="5e720-114">eDiscovery von Gast-zu-Gast-Chats</span><span class="sxs-lookup"><span data-stu-id="5e720-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="5e720-115">Ohne ein Postfach würden Gast-zu-Gast-Chats (1xN-Chats, in denen keine Home-Tenant-Benutzer vorhanden sind) nicht indiziert und daher nicht in eDiscovery enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="5e720-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="5e720-116">Um eDiscovery für Gast-zu-Gast-Chats zu vereinfachen, wird ein Cloud-basiertes Postfach (oder ein Phantom Postfach) zum Speichern der 1xN-Daten erstellt.</span><span class="sxs-lookup"><span data-stu-id="5e720-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="5e720-117">Nachdem die Chat-Daten des Teams im cloudbasierten Postfach gespeichert wurden, ist es für die eDiscovery-und Compliance-Inhaltssuche indiziert.</span><span class="sxs-lookup"><span data-stu-id="5e720-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="5e720-118">Die folgende Abbildung zeigt, wie eDiscovery für Gast-zu-Gast-Chats funktioniert, in denen kein Postfach vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5e720-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Gast-zu-Gast-Chats-mit-ohne-Postfach](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
