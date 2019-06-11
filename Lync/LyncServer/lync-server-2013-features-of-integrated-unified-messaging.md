---
title: 'Lync Server 2013: Features von integriertem Unified Messaging'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5dc6396bd78977d099e650f14ae1a0b4b46c54e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="854b8-102">Features von integriertem Unified Messaging und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854b8-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="854b8-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="854b8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="854b8-104">Lync Server 2013, Enterprise-VoIP verwendet die Exchange Unified Messaging (um)-Infrastruktur für die Bereitstellung von Anrufannahme, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und automatischen Telefonzentralen.</span><span class="sxs-lookup"><span data-stu-id="854b8-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="854b8-105">Anrufbeantwortung</span><span class="sxs-lookup"><span data-stu-id="854b8-105">Call Answering</span></span>

<span data-ttu-id="854b8-106">Bei der Anrufbeantwortung werden Sprachnachrichten für Benutzer entgegengenommen, die gerade nicht an ihrem Platz sind oder sich bereits in einem Gespräch befinden.</span><span class="sxs-lookup"><span data-stu-id="854b8-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="854b8-107">Hierzu gehören die Wiedergabe einer persönlichen Begrüßung, die Aufzeichnung einer Nachricht sowie die Übermittlung der Nachricht, um sie in die Warteschlange für eine Übermittlung an das auf dem Exchange-Postfachserver gespeicherte Postfach des Benutzers einzureihen.</span><span class="sxs-lookup"><span data-stu-id="854b8-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="854b8-p102">Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.</span><span class="sxs-lookup"><span data-stu-id="854b8-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="854b8-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="854b8-112">Outlook Voice Access</span></span>

<span data-ttu-id="854b8-113">Outlook Voice Access ermöglicht einem Enterprise-VoIP-Benutzer den Zugriff auf nicht nur Voicemail, sondern auch den Exchange-Posteingang, einschließlich e-Mail, Kalender und Kontakte über eine Telefonschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="854b8-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="854b8-114">Die Teilnehmerzugriffsnummer wird von einem Exchange um-Administrator zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="854b8-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="854b8-115">Automatische Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="854b8-115">Auto Attendant</span></span>

<span data-ttu-id="854b8-116">Bei der automatischen Telefonzentrale handelt es sich um ein Exchange um-Feature, das verwendet werden kann, um eine Telefonnummer zu konfigurieren, die externe Benutzer anrufen können, um Unternehmensvertreter zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="854b8-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="854b8-117">Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="854b8-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="854b8-118">Die Liste der verfügbaren Optionen wird vom Exchange um-Administrator auf dem Exchange um-Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="854b8-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="854b8-119">Fax-Dienste</span><span class="sxs-lookup"><span data-stu-id="854b8-119">Fax Services</span></span>

<span data-ttu-id="854b8-120">Exchange um umfasst Fax-Features, mit denen Benutzer eingehende Faxe in Ihren Exchange-Postfächern empfangen können.</span><span class="sxs-lookup"><span data-stu-id="854b8-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="854b8-121">Ausführliche Informationen finden Sie unter "Unified Messaging" in der Microsoft Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)-Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="854b8-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="854b8-122">Die vom Exchange um-Server bereitgestellten Faxdienst sind in lync Server-Bereitstellungen, die in Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Service Pack oder Exchange 2013 integriert sind, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="854b8-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

