---
title: 'Lync Server 2013: integrieren in Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1c60768311f4fbf832f3dbe2ac4a0c2e8e55298
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="d8273-102">Integrieren von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8273-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8273-103">_**Letztes Änderungsstand des Themas:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="d8273-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="d8273-104">Exchange und lync Server haben eine lange Geschichte der Integration und Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="d8273-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="d8273-105">Diese Integration ist in der jeweiligen Clientanwendung am deutlichsten spürbar.</span><span class="sxs-lookup"><span data-stu-id="d8273-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="d8273-106">Beispielsweise können lync-Anwesenheitsinformationen in Microsoft Outlook gemeldet werden; Ebenso kann lync Outlook-Kalender verwenden, um diese Anwesenheitsinformationen automatisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d8273-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="d8273-107">(Beispielsweise kann lync ihren Status in "beschäftigt" ändern, wenn Ihr Kalender zeigt, dass Sie eine Besprechung geplant haben.) Obwohl Sie Exchange nicht ausführen müssen, um lync Server auszuführen (oder umgekehrt), gibt es kaum einen Zweifel daran, dass die Verwendung der beiden Produkte zusammen die Definition des Begriffs "besser zusammen" verkörpert.</span><span class="sxs-lookup"><span data-stu-id="d8273-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="d8273-108">Dies gilt insbesondere für die Veröffentlichung von Microsoft lync Server 2013 und Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8273-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="d8273-109">Neben Features wie Unified Messaging und Sofortnachrichten und Anwesenheitsinformationen, die sich in Microsoft Exchange Server 2010 und Microsoft lync Server 2010 befinden, enthalten die 2013-Versionen der Server Produkte eine Reihe neuer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d8273-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="d8273-110">Dazu zählen beispielsweise folgende:</span><span class="sxs-lookup"><span data-stu-id="d8273-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="d8273-111">**Lync-Archivierungs Integration**.</span><span class="sxs-lookup"><span data-stu-id="d8273-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="d8273-112">In lync Server 2013 Administratoren weiterhin die Möglichkeit haben, Chatnachrichten und Webkonferenz-Transkripte in SQL Server zu archivieren (genauso wie diese Transkripte in lync Server 2010 archiviert wurden).</span><span class="sxs-lookup"><span data-stu-id="d8273-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="d8273-113">Alternativ können Administratoren auch die Archivierung von Transkripten in Exchange 2013 auswählen, wobei diese Transkripte in den einzelnen Benutzerpostfächern auf dieselbe Weise gespeichert werden, in der Exchange die Kommunikation archiviert.</span><span class="sxs-lookup"><span data-stu-id="d8273-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="d8273-114">Das bedeutet ein einzelnes Repository für Ihre gesamte elektronische Kommunikation (sowohl in Exchange als auch in lync Server), wodurch es viel einfacher wird, diese Archivierte Kommunikation zu suchen und abzurufen, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d8273-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="d8273-115">**Einheitlicher Kontaktspeicher**.</span><span class="sxs-lookup"><span data-stu-id="d8273-115">**Unified Contact Store**.</span></span> <span data-ttu-id="d8273-116">In lync Server 2010 mussten Benutzer getrennte Kontaktlisten in Outlook und lync verwalten; um sicherzustellen, dass in beiden Produkten dieselben Kontakte verfügbar waren, mussten Sie doppelte Kontaktlisten verwalten, eine für Outlook und eine für lync.</span><span class="sxs-lookup"><span data-stu-id="d8273-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="d8273-117">Mit lync Server 2013 können Benutzer Kontakte jedoch in Exchange 2013 und im einheitlichen Kontaktspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d8273-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="d8273-118">Durch die Verwendung eines einzelnen Kontaktspeichers können Benutzer nur eine Gruppe von Kontakten verwalten, wobei dieselbe Gruppe von Kontakten in lync 2013, Outlook 2013 und Outlook Web Access 2013 zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="d8273-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="d8273-119">**Lync-Besprechungsplanung von OWA**.</span><span class="sxs-lookup"><span data-stu-id="d8273-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="d8273-120">Mit lync Server 2013-und Exchange 2013-Integration können Benutzer lync-Besprechungen von Outlook Web Access 2013 aus planen.</span><span class="sxs-lookup"><span data-stu-id="d8273-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="d8273-121">**Fotos mit hoher Auflösung**.</span><span class="sxs-lookup"><span data-stu-id="d8273-121">**High resolution photos**.</span></span> <span data-ttu-id="d8273-122">Lync 2010 konnten nur kleine Fotos Ihrer Kontakte anzeigen; Das liegt daran, dass diese Fotos in Active Directory gespeichert wurden und Active Directory eine 48 Pixelgrößen Beschränkung von 48 Pixeln auf gespeicherte Fotos auferlegt.</span><span class="sxs-lookup"><span data-stu-id="d8273-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="d8273-123">Mit lync Server 2013 können Fotos jedoch in Microsoft Exchange gespeichert werden; Dies ermöglicht hochauflösende Fotos mit einer Größe von 648 Pixeln von 648 Pixel.</span><span class="sxs-lookup"><span data-stu-id="d8273-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="d8273-124">Wie Sie vielleicht erwarten, wurde lync 2013 aktualisiert, um die Anzeige dieser hochauflösenden Fotos zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d8273-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="d8273-125">Beachten Sie, dass diese neuen Features sowohl lync Server 2013 als auch Exchange 2013 erfordern.</span><span class="sxs-lookup"><span data-stu-id="d8273-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="d8273-126">Darüber hinaus müssen Benutzer, die diese neuen Funktionen in vollem Umfang nutzen möchten, über Konten für lync Server 2013 und Exchange 2013 verfügen und die neuesten Versionen der Client Software verwenden (beispielsweise lync 2013).</span><span class="sxs-lookup"><span data-stu-id="d8273-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="d8273-127">Beispielsweise steht der einheitliche Kontaktspeicher nicht für Benutzer zur Verfügung, die in lync Server 2010 verwaltet wurden. Ebenso können hochauflösende Fotos nicht in lync 2010 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d8273-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="d8273-128">Diese Dokumentation enthält Informationen zur Integration von lync Server 2013 und Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d8273-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="d8273-129">einschließlich Schritt-für-Schritt-Informationen zur Aktivierung neuer Features wie die Archivierungs Integration und den einheitlichen Kontaktspeicher.</span><span class="sxs-lookup"><span data-stu-id="d8273-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="d8273-130">In dieser Dokumentation werden die anfänglichen Einstellungen und Konfigurationen dieser beiden Produkte erläutert.</span><span class="sxs-lookup"><span data-stu-id="d8273-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="d8273-131">Ausführliche Informationen zum Bereitstellen von lync Server 2013 finden Sie im lync Server 2013 [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)Tech Center unter.</span><span class="sxs-lookup"><span data-stu-id="d8273-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="d8273-132">Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie im Exchange 2013 [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)Tech Center unter.</span><span class="sxs-lookup"><span data-stu-id="d8273-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8273-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d8273-133">In This Section</span></span>

[<span data-ttu-id="d8273-134">Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8273-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="d8273-135">Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8273-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="d8273-136">Konfigurieren Microsoft lync Server 2013 für die Verwendung Microsoft Exchange Server 2013 Archivierung</span><span class="sxs-lookup"><span data-stu-id="d8273-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="d8273-137">Konfigurieren Microsoft SharePoint Server 2013 für die Suche nach archivierten Microsoft lync Server 2013 Daten</span><span class="sxs-lookup"><span data-stu-id="d8273-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="d8273-138">Konfigurieren Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</span><span class="sxs-lookup"><span data-stu-id="d8273-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="d8273-139">Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8273-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="d8273-140">Konfigurieren Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail</span><span class="sxs-lookup"><span data-stu-id="d8273-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="d8273-141">Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="d8273-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

