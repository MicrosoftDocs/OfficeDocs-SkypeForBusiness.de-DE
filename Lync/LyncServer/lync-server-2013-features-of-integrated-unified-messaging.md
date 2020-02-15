---
title: 'Lync Server 2013: Features von Integrated Unified Messaging'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c70df997e0ed42f77451287cccbae23ae93d14e6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="e10be-102">Features integrierter Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e10be-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e10be-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e10be-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e10be-104">Lync Server 2013 verwendet Enterprise-VoIP die Exchange Unified Messaging (um)-Infrastruktur zur Bereitstellung von Mailboxansage, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und automatischen Telefonzentralen Diensten.</span><span class="sxs-lookup"><span data-stu-id="e10be-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="e10be-105">Anrufbeantwortung</span><span class="sxs-lookup"><span data-stu-id="e10be-105">Call Answering</span></span>

<span data-ttu-id="e10be-106">Mailboxansage ist der Empfang von Sprachnachrichten im Namen von Benutzern, deren Anrufe nicht beantwortet werden oder ausgelastet sind.</span><span class="sxs-lookup"><span data-stu-id="e10be-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="e10be-107">Es umfasst die Wiedergabe einer persönlichen Begrüßung, das Aufzeichnen einer Nachricht und das Senden der Nachricht an die Warteschlange für die Zustellung an das Postfach des Benutzers, das auf dem Exchange-Postfachserver gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e10be-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="e10be-p102">Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.</span><span class="sxs-lookup"><span data-stu-id="e10be-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="e10be-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="e10be-112">Outlook Voice Access</span></span>

<span data-ttu-id="e10be-113">Outlook Voice Access ermöglicht Enterprise-VoIP-Benutzern über eine Telefonie-Benutzeroberfläche nicht nur den Zugriff auf Voicemail, sondern auch auf den Posteingang von Exchange, einschließlich E-Mail, Sprachnachrichten, Kalender und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="e10be-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="e10be-114">Die Teilnehmerzugriffsnummer wird von einem Exchange um Administrator zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e10be-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="e10be-115">Automatische Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="e10be-115">Auto Attendant</span></span>

<span data-ttu-id="e10be-116">Die automatische Telefonzentrale ist ein Exchange UMes Feature, mit dem eine Telefonnummer konfiguriert werden kann, die von externen Benutzern zum Erreichen von Unternehmensvertretern gewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e10be-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="e10be-117">Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e10be-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="e10be-118">Die Liste der verfügbaren Optionen wird vom Exchange um Administrator auf dem Exchange um Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e10be-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="e10be-119">Faxdienste</span><span class="sxs-lookup"><span data-stu-id="e10be-119">Fax Services</span></span>

<span data-ttu-id="e10be-120">Exchange um enthält Fax-Features, mit denen Benutzer eingehende Faxe in Ihren Exchange-Postfächern empfangen können.</span><span class="sxs-lookup"><span data-stu-id="e10be-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="e10be-121">Ausführliche Informationen finden Sie unter "Unified Messaging" in der Exchange Server- [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="e10be-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e10be-122">Die vom Exchange um-Server bereitgestellten Faxdienst sind in lync Server-Bereitstellungen nicht verfügbar, die mit Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Service Pack oder Exchange 2013 integriert sind.</span><span class="sxs-lookup"><span data-stu-id="e10be-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

