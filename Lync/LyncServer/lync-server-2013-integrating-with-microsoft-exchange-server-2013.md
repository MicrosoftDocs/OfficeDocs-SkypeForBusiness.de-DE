---
title: 'Lync Server 2013: integrieren in Microsoft Exchange Server 2013'
description: 'Lync Server 2013: Integration in Microsoft Exchange Server 2013.'
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
ms.openlocfilehash: 54ab4a81e5455bc0a44677b1509876f39ff4d985
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543981"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="5286d-103">Integrieren von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="5286d-103">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5286d-104">_**Letztes Änderungsstand des Themas:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="5286d-104">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="5286d-105">Exchange und lync Server haben eine lange Geschichte der Integration und Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="5286d-105">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="5286d-106">Diese Integration ist in der jeweiligen Clientanwendung am deutlichsten spürbar.</span><span class="sxs-lookup"><span data-stu-id="5286d-106">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="5286d-107">Beispielsweise können lync-Anwesenheitsinformationen in Microsoft Outlook gemeldet werden; Ebenso kann lync Outlook-Kalender verwenden, um diese Anwesenheitsinformationen automatisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5286d-107">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="5286d-108">(Beispielsweise kann lync ihren Status in "beschäftigt" ändern, wenn Ihr Kalender zeigt, dass Sie eine Besprechung geplant haben.) Obwohl Sie Exchange nicht ausführen müssen, um lync Server auszuführen (oder umgekehrt), gibt es kaum einen Zweifel daran, dass die Verwendung der beiden Produkte zusammen die Definition des Begriffs "besser zusammen" verkörpert.</span><span class="sxs-lookup"><span data-stu-id="5286d-108">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="5286d-109">Dies gilt insbesondere für die Veröffentlichung von Microsoft lync Server 2013 und Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5286d-109">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="5286d-110">Neben Features wie Unified Messaging und Sofortnachrichten und Anwesenheitsinformationen, die sich in Microsoft Exchange Server 2010 und Microsoft lync Server 2010 befinden, enthalten die 2013-Versionen der Server Produkte eine Reihe neuer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5286d-110">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="5286d-111">Dazu zählen beispielsweise folgende:</span><span class="sxs-lookup"><span data-stu-id="5286d-111">These capabilities include such things as:</span></span>

  - <span data-ttu-id="5286d-112">**Lync-Archivierungs Integration**.</span><span class="sxs-lookup"><span data-stu-id="5286d-112">**Lync Archiving Integration**.</span></span> <span data-ttu-id="5286d-113">In lync Server 2013 Administratoren weiterhin die Möglichkeit haben, Chatnachrichten und Webkonferenz-Transkripte in SQL Server zu archivieren (genauso wie diese Transkripte in lync Server 2010 archiviert wurden).</span><span class="sxs-lookup"><span data-stu-id="5286d-113">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="5286d-114">Alternativ können Administratoren auch die Archivierung von Transkripten in Exchange 2013 auswählen, wobei diese Transkripte in den einzelnen Benutzerpostfächern auf dieselbe Weise gespeichert werden, in der Exchange die Kommunikation archiviert.</span><span class="sxs-lookup"><span data-stu-id="5286d-114">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="5286d-115">Das bedeutet ein einzelnes Repository für Ihre gesamte elektronische Kommunikation (sowohl in Exchange als auch in lync Server), wodurch es viel einfacher wird, diese Archivierte Kommunikation zu suchen und abzurufen, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5286d-115">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="5286d-116">**Einheitlicher Kontaktspeicher**.</span><span class="sxs-lookup"><span data-stu-id="5286d-116">**Unified Contact Store**.</span></span> <span data-ttu-id="5286d-117">In lync Server 2010 mussten Benutzer getrennte Kontaktlisten in Outlook und lync verwalten; um sicherzustellen, dass in beiden Produkten dieselben Kontakte verfügbar waren, mussten Sie doppelte Kontaktlisten verwalten, eine für Outlook und eine für lync.</span><span class="sxs-lookup"><span data-stu-id="5286d-117">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="5286d-118">Mit lync Server 2013 können Benutzer Kontakte jedoch in Exchange 2013 und im einheitlichen Kontaktspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5286d-118">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="5286d-119">Durch die Verwendung eines einzelnen Kontaktspeichers können Benutzer nur eine Gruppe von Kontakten verwalten, wobei dieselbe Gruppe von Kontakten in lync 2013, Outlook 2013 und Outlook Web Access 2013 zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="5286d-119">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="5286d-120">**Lync-Besprechungsplanung von OWA**.</span><span class="sxs-lookup"><span data-stu-id="5286d-120">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="5286d-121">Mit lync Server 2013-und Exchange 2013-Integration können Benutzer lync-Besprechungen von Outlook Web Access 2013 aus planen.</span><span class="sxs-lookup"><span data-stu-id="5286d-121">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="5286d-122">**Fotos mit hoher Auflösung**.</span><span class="sxs-lookup"><span data-stu-id="5286d-122">**High resolution photos**.</span></span> <span data-ttu-id="5286d-123">Lync 2010 konnten nur kleine Fotos Ihrer Kontakte anzeigen; Das liegt daran, dass diese Fotos in Active Directory gespeichert wurden und Active Directory eine 48 Pixelgrößen Beschränkung von 48 Pixeln auf gespeicherte Fotos auferlegt.</span><span class="sxs-lookup"><span data-stu-id="5286d-123">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="5286d-124">Mit lync Server 2013 können Fotos jedoch in Microsoft Exchange gespeichert werden; Dies ermöglicht hochauflösende Fotos mit einer Größe von 648 Pixeln von 648 Pixel.</span><span class="sxs-lookup"><span data-stu-id="5286d-124">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="5286d-125">Wie Sie vielleicht erwarten, wurde lync 2013 aktualisiert, um die Anzeige dieser hochauflösenden Fotos zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5286d-125">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="5286d-126">Beachten Sie, dass diese neuen Features sowohl lync Server 2013 als auch Exchange 2013 erfordern.</span><span class="sxs-lookup"><span data-stu-id="5286d-126">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="5286d-127">Darüber hinaus müssen Benutzer, die diese neuen Funktionen in vollem Umfang nutzen möchten, über Konten für lync Server 2013 und Exchange 2013 verfügen und die neuesten Versionen der Client Software verwenden (beispielsweise lync 2013).</span><span class="sxs-lookup"><span data-stu-id="5286d-127">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="5286d-128">Beispielsweise steht der einheitliche Kontaktspeicher nicht für Benutzer zur Verfügung, die in lync Server 2010 verwaltet wurden. Ebenso können hochauflösende Fotos nicht in lync 2010 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5286d-128">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="5286d-129">Diese Dokumentation enthält Informationen zur Integration von lync Server 2013 und Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="5286d-129">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="5286d-130">einschließlich Schritt-für-Schritt-Informationen zur Aktivierung neuer Features wie die Archivierungs Integration und den einheitlichen Kontaktspeicher.</span><span class="sxs-lookup"><span data-stu-id="5286d-130">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="5286d-131">In dieser Dokumentation werden die anfänglichen Einstellungen und Konfigurationen dieser beiden Produkte erläutert.</span><span class="sxs-lookup"><span data-stu-id="5286d-131">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="5286d-132">Ausführliche Informationen zum Bereitstellen von lync Server 2013 finden Sie im lync Server 2013 Tech Center unter [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) .</span><span class="sxs-lookup"><span data-stu-id="5286d-132">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="5286d-133">Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie im Exchange 2013 Tech Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .</span><span class="sxs-lookup"><span data-stu-id="5286d-133">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5286d-134">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5286d-134">In This Section</span></span>

[<span data-ttu-id="5286d-135">Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="5286d-135">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="5286d-136">Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="5286d-136">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="5286d-137">Konfigurieren Microsoft lync Server 2013 für die Verwendung Microsoft Exchange Server 2013 Archivierung</span><span class="sxs-lookup"><span data-stu-id="5286d-137">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="5286d-138">Konfigurieren Microsoft SharePoint Server 2013 für die Suche nach archivierten Microsoft lync Server 2013 Daten</span><span class="sxs-lookup"><span data-stu-id="5286d-138">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="5286d-139">Konfigurieren Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</span><span class="sxs-lookup"><span data-stu-id="5286d-139">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="5286d-140">Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5286d-140">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="5286d-141">Konfigurieren Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail</span><span class="sxs-lookup"><span data-stu-id="5286d-141">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="5286d-142">Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="5286d-142">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

