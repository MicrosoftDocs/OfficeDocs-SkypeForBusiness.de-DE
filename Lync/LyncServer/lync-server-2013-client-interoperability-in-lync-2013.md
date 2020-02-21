---
title: 'Lync Server 2013: Client Interoperabilität in lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 437051279393b9dedc7c4def0c75cd119cded914
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="78f8a-102">Client Interoperabilität in lync 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78f8a-103">_**Letztes Änderungsstand des Themas:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="78f8a-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="78f8a-104">In diesem Thema wird erläutert, wie Microsoft lync Server 2013 Clients in früheren Versionen von lync Server und Office Communications Server nebeneinander bestehen und mit Clients interagieren können.</span><span class="sxs-lookup"><span data-stu-id="78f8a-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="78f8a-105">Server-und Client Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="78f8a-105">Server and Client Compatibility</span></span>

<span data-ttu-id="78f8a-106">In der folgenden Tabelle ist aufgeführt, welche Kombinationen von Client- und Serverversionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="78f8a-107">Diese Tabelle gibt an, ob die Anmeldung unterstützt wird, wenn der Client versucht, eine Verbindung mit dem angezeigten Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="78f8a-108">Lync Server 2013 unterstützt die vorherige Client Version.</span><span class="sxs-lookup"><span data-stu-id="78f8a-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="78f8a-109">Im Gegensatz zu früheren Versionen unterstützt lync Server 2010 auch die neuen lync 2013-Clients.</span><span class="sxs-lookup"><span data-stu-id="78f8a-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="78f8a-110">Auf diese Weise können Organisationen, die ein Upgrade von lync Server 2010 durchführen, neue Clients unabhängig von lync Server Upgrades Ausrollen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78f8a-111">Client</span><span class="sxs-lookup"><span data-stu-id="78f8a-111">Client</span></span></th>
<th><span data-ttu-id="78f8a-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="78f8a-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="78f8a-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="78f8a-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="78f8a-116">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="78f8a-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="78f8a-118">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="78f8a-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="78f8a-120">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-121">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-122">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="78f8a-124">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-125">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-126">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="78f8a-128">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-129">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-130">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="78f8a-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="78f8a-132">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-133">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-134">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-135">Lync 2010 Gruppen Chat</span><span class="sxs-lookup"><span data-stu-id="78f8a-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="78f8a-136">Unterstützt1</span><span class="sxs-lookup"><span data-stu-id="78f8a-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="78f8a-137">Unterstützt2</span><span class="sxs-lookup"><span data-stu-id="78f8a-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="78f8a-138">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="78f8a-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="78f8a-140">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-141">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-142">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="78f8a-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="78f8a-144">Nicht Supported3</span><span class="sxs-lookup"><span data-stu-id="78f8a-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="78f8a-145">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-146">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="78f8a-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="78f8a-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="78f8a-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="78f8a-149">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-150">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="78f8a-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="78f8a-152">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-153">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-154">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="78f8a-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="78f8a-156">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-157">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-158">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="78f8a-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="78f8a-160">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-161">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-162">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-163">Lync Windows Store-App</span><span class="sxs-lookup"><span data-stu-id="78f8a-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="78f8a-164">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-165">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-166">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="78f8a-167">Details zu 1Für finden Sie unter [Migration from lync Server 2010, Group Chat oder Office Communications Server 2007 R2 Group Chat to lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="78f8a-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="78f8a-168">2in Microsoft lync Server 2010 war die gruppenchatfunktion mit dem Gruppenchat Server, einer vertrauenswürdigen Drittanbieteranwendung für lync Server 2010, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78f8a-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="78f8a-169">Lync 2013 Clients sind nicht mit lync Server 2010, Gruppen Chat, kompatibel.</span><span class="sxs-lookup"><span data-stu-id="78f8a-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="78f8a-170">3Lync-Webanwendung 2013 bietet nun eine umfassende Besprechungs Erfahrung, einschließlich Computer-Audio und-Video, und gilt als Ersatz für lync 2010 Attendee.</span><span class="sxs-lookup"><span data-stu-id="78f8a-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="78f8a-171">Lync 2010 Attendee stellt nur dann eine Verbindung mit lync Server 2013 her, wenn Sie einen nicht unterstützten Browser (Internet Explorer 6 oder Internet Explorer 7) und Windows XP verwenden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="78f8a-172">4Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="78f8a-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="78f8a-173">Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.</span><span class="sxs-lookup"><span data-stu-id="78f8a-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="78f8a-174">5 Informationen zu Einschränkungen finden Sie unter "Unterstützung von Konferenzfeatures für lync 2013 Clients in lync Server 2010 Besprechungen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="78f8a-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="78f8a-175">Interoperabilität zwischen Clients</span><span class="sxs-lookup"><span data-stu-id="78f8a-175">Interoperability among Clients</span></span>

<span data-ttu-id="78f8a-176">Mit der lync Server 2013-Version können verschiedene Clientversionen nahtlos in Peer-zu-Peer-und Konferenzszenarien interagieren.</span><span class="sxs-lookup"><span data-stu-id="78f8a-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="78f8a-177">In diesem Abschnitt wird die Verfügbarkeit von Features erläutert, wenn Benutzer mit anderen Benutzern interagieren, die unterschiedliche Versionen von Clients und Servern verwenden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="78f8a-178">Unterstützung von Peer-zu-Peer-Funktionen</span><span class="sxs-lookup"><span data-stu-id="78f8a-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="78f8a-179">Peer-to-Peer-Funktionen werden für Benutzer unterstützt, die in verschiedenen Versionen des Servers verwaltet werden und unterschiedliche Clientversionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="78f8a-180">Die Endbenutzeroberfläche und die verfügbaren Features stehen im Einklang mit den Funktionen des Clients des Benutzers und der Version des Servers, bei dem der Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="78f8a-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="78f8a-181">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="78f8a-181">In other words:</span></span>

  - <span data-ttu-id="78f8a-182">Wenn ein Benutzer bei lync Server 2013 mit einem älteren Client angemeldet ist, hat der Benutzer die gleiche Erfahrung wie er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78f8a-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="78f8a-183">Keines der in lync Server 2013 eingeführten neuen Features ist verfügbar, bis der Client des Benutzers aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="78f8a-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="78f8a-184">Beispiele hierfür sind Video Galerie-Ansicht, HD-Video, aktualisierte PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videodaten beim Besprechungseintrag.</span><span class="sxs-lookup"><span data-stu-id="78f8a-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="78f8a-185">Die neuen Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="78f8a-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="78f8a-186">Wenn ein Benutzer bei lync Server 2010 mit einem lync 2013-Client angemeldet ist, sind alle neuen Features, die nicht von lync Server 2010 unterstützt werden, erst verfügbar, wenn der Benutzer zu lync Server 2013 verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="78f8a-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="78f8a-187">In der folgenden Tabelle wird die Verfügbarkeit von Features in Peer-to-Peer-Sitzungen verglichen, in denen der Client entweder lync Server 2013 oder lync Server 2010 angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="78f8a-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78f8a-188">Lync Web App und lync 2010 Attendee sind Besprechungs bezogene Clients, die nicht in dieser Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="78f8a-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78f8a-189">Client</span><span class="sxs-lookup"><span data-stu-id="78f8a-189">Client</span></span></th>
<th><span data-ttu-id="78f8a-190">Instant Messaging</span><span class="sxs-lookup"><span data-stu-id="78f8a-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="78f8a-191">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="78f8a-191">Presence</span></span></th>
<th><span data-ttu-id="78f8a-192">VoIP</span><span class="sxs-lookup"><span data-stu-id="78f8a-192">Voice</span></span></th>
<th><span data-ttu-id="78f8a-193">Video</span><span class="sxs-lookup"><span data-stu-id="78f8a-193">Video</span></span></th>
<th><span data-ttu-id="78f8a-194">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="78f8a-194">Application Sharing</span></span></th>
<th><span data-ttu-id="78f8a-195">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="78f8a-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="78f8a-197">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-198">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-199">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-200">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-201">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-202">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="78f8a-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="78f8a-204">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-205">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-206">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-207">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-208">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-209">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="78f8a-211">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-212">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-213">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-214">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-215">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-216">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="78f8a-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="78f8a-218">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-219">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-220">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="78f8a-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="78f8a-222">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-223">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="78f8a-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="78f8a-225">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-226">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-227">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="78f8a-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="78f8a-229">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-230">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-231">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-232">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="78f8a-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="78f8a-234">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-235">Öffentliche Chatnachrichten (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="78f8a-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="78f8a-236">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-237">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-238">Öffentliche Chatnachrichten (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="78f8a-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="78f8a-239">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-240">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-241">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-242">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="78f8a-243">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78f8a-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="78f8a-244">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="78f8a-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="78f8a-245">Messenger bis zum Datum der Beendigung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="78f8a-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="78f8a-246">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="78f8a-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="78f8a-247">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="78f8a-247">has been announced.</span></span> <span data-ttu-id="78f8a-248">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="78f8a-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="78f8a-249">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="78f8a-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="78f8a-250">Messenger.</span></span> <span data-ttu-id="78f8a-251">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="78f8a-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="78f8a-252">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="78f8a-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="78f8a-253">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78f8a-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="78f8a-254">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</span><span class="sxs-lookup"><span data-stu-id="78f8a-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="78f8a-255">1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="78f8a-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78f8a-256">Die Desktop Freigabe zwischen Office Communicator 2007 R2 und Skype for Business 2015 kann nicht vom neueren Client initiiert werden, wenn die Skype for Business 2015 Client-Benutzeroberfläche erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="78f8a-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="78f8a-257">Unterstützung von Konferenzfeatures für lync 2013 Clients in lync Server 2010 Besprechungen</span><span class="sxs-lookup"><span data-stu-id="78f8a-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="78f8a-258">Wenn Benutzer lync Server 2010 Besprechungen mit einem lync 2013-Clientteil nehmen, haben Sie Zugriff auf lync 2013-Clientfeatures mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="78f8a-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="78f8a-259">In den Verwaltungsoptionen für **Teilnehmer** , auf die durch den Hinweis auf das Symbol Personen im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechungs-Chat** Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="78f8a-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="78f8a-260">Die Katalogansicht funktioniert nicht in Videokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="78f8a-261">Der Benutzer sieht anstelle aller Lautsprecher nur den aktiven Lautsprecher.</span><span class="sxs-lookup"><span data-stu-id="78f8a-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="78f8a-262">In der Liste der Optionen zum **Auswählen eines Layouts** ist die **Katalogansicht** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78f8a-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="78f8a-263">Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78f8a-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="78f8a-264">Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Verwaltungsoptionen **Video Spotlight** und **PIN-an-Katalog** -Teilnehmerverwaltung Sperren nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78f8a-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="78f8a-265">Unterstützung von Konferenzfeatures in lync Server 2013 Besprechungen</span><span class="sxs-lookup"><span data-stu-id="78f8a-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="78f8a-266">Lync Server 2013 stellt neue Konferenzfeatures bereit, die Benutzern zur Verfügung stehen, nachdem Ihre Konten in lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="78f8a-267">Beispiele hierfür sind Video Galerie-Ansicht, HD-Video, PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videodaten beim Besprechungseintrag.</span><span class="sxs-lookup"><span data-stu-id="78f8a-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="78f8a-268">Die neuen Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="78f8a-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="78f8a-269">In lync Server 2013 Besprechungen werden bestimmte Konferenzfeatures für Benutzer unterstützt, die in unterschiedlichen Versionen des Servers verwaltet werden und unterschiedliche Clients und Clientversionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="78f8a-270">Wenn Clients an einer lync Server 2013 Besprechung teilnehmen, haben Benutzer Zugriff auf die in dieser Tabelle gezeigten Features und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78f8a-271">Client</span><span class="sxs-lookup"><span data-stu-id="78f8a-271">Client</span></span></th>
<th><span data-ttu-id="78f8a-272">Peer-zu-Peer-Chat</span><span class="sxs-lookup"><span data-stu-id="78f8a-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="78f8a-273">VoIP</span><span class="sxs-lookup"><span data-stu-id="78f8a-273">Voice</span></span></th>
<th><span data-ttu-id="78f8a-274">Video</span><span class="sxs-lookup"><span data-stu-id="78f8a-274">Video</span></span></th>
<th><span data-ttu-id="78f8a-275">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="78f8a-275">Application Sharing</span></span></th>
<th><span data-ttu-id="78f8a-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="78f8a-276">PowerPoint</span></span></th>
<th><span data-ttu-id="78f8a-277">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="78f8a-277">File Transfer</span></span></th>
<th><span data-ttu-id="78f8a-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="78f8a-278">Whiteboard</span></span></th>
<th><span data-ttu-id="78f8a-279">Abrufen</span><span class="sxs-lookup"><span data-stu-id="78f8a-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="78f8a-281">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-282">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-283">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-284">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-285">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-286">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-287">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-288">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="78f8a-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="78f8a-290">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-291">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-292">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-293">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-294">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-295">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-296">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-297">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="78f8a-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="78f8a-299">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-300">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-301">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-302">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-303">Ja2</span><span class="sxs-lookup"><span data-stu-id="78f8a-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="78f8a-304">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-305">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-306">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="78f8a-308">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-309">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-310">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-311">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="78f8a-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="78f8a-313">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-314">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="78f8a-315">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="78f8a-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="78f8a-317">Ja</span><span class="sxs-lookup"><span data-stu-id="78f8a-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="78f8a-318">1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="78f8a-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="78f8a-319">2 lync Server 2013 verwendet einen aktualisierten Mechanismus für das Hochladen von PowerPoint-Dateien.</span><span class="sxs-lookup"><span data-stu-id="78f8a-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="78f8a-320">Lync Web App Benutzer, die einer Besprechung beitreten, die ursprünglich auf lync Server 2010 geplant war, können PowerPoint-Präsentationen anzeigen und navigieren, jedoch keine PowerPoint-Dateien hochladen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="78f8a-321">3 Wenn die Besprechung in lync Server 2013 geplant wurde und PowerPoint-Folien von einem lync 2013-Client hochgeladen wurden, verfügen lync 2010 Benutzer über einen schreibgeschützten Zugriff auf die Folien.</span><span class="sxs-lookup"><span data-stu-id="78f8a-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="78f8a-322">Wenn umgekehrt die PowerPoint-Folien von einem lync 2010-Benutzer hochgeladen wurden, können lync Server 2013 Benutzer anzeigen und Folien und, falls Office-webapps-Server konfiguriert ist, auf neue Funktionen wie höhere Auflösung, Animationen, Folienübergänge und Eingebettetes Video.</span><span class="sxs-lookup"><span data-stu-id="78f8a-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="78f8a-323">Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="78f8a-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="78f8a-324">4Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="78f8a-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="78f8a-325">Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.</span><span class="sxs-lookup"><span data-stu-id="78f8a-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="78f8a-326">Planen der Add-in-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="78f8a-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="78f8a-327">Die Server Unterstützung für die unterschiedlichen Planungs-Add-Ins ist konsistent mit der Server-und Client Versionskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="78f8a-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="78f8a-328">Im Allgemeinen werden die folgenden Planungs-Add-Ins in lync Server 2013 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="78f8a-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="78f8a-329">In früheren Versionen von Add-Ins werden jedoch keine neuen lync 2013-Add-in-Features bereitgestellt, wie beispielsweise die Option zum stumm schalten aller Teilnehmer-Audio-und-Videos beim Besprechungseintrag.</span><span class="sxs-lookup"><span data-stu-id="78f8a-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="78f8a-330">**Das Online-Besprechungs-Add-in für lync 2013**   bietet dieselben Features wie das Online-Besprechungs-Add-in für lync 2010, wobei die Teilnehmer-stumm Schaltungs Steuerelemente hinzugefügt werden, mit deren Hilfe Besprechungsorganisatoren Konferenzen planen können, für die die Teilnehmer-Audio und-Videostandard mäßig stumm geschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="78f8a-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="78f8a-331">Administratoren können die Besprechungseinladungen der Organisation auch anpassen, indem Sie ein benutzerdefiniertes Logo, eine Support-URL, eine URL für einen rechtlichen Haftungsausschluss oder benutzerdefinierter Fußzeilentext hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="78f8a-332">**Das Online-Besprechungs-Add-in für lync 2010**   bietet Zeitpläne für lync-Besprechungen und entfernt die Möglichkeit, Office Live Meeting Konferenzen zu planen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="78f8a-333">**Office Communicator 2007 R2 Konferenz-Add-in**   bietet Zeitplanung für Office Live Meeting Konferenzen und Office Communicator 2007 R2 Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="78f8a-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="78f8a-334">Live Meeting Konferenzen können nicht für lync Server 2013 geplant werden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78f8a-335">Planen des Clients</span><span class="sxs-lookup"><span data-stu-id="78f8a-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="78f8a-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="78f8a-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="78f8a-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="78f8a-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-339">Online-Besprechungs-Add-in für lync 2013 (kann mit Office 2013, Outlook 2010 und Outlook 2007 verwendet werden)</span><span class="sxs-lookup"><span data-stu-id="78f8a-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="78f8a-340">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-341">Unterstützt (neue Add-in-Features nicht verfügbar)</span><span class="sxs-lookup"><span data-stu-id="78f8a-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="78f8a-342">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-343">Lync 2013-Webplaner</span><span class="sxs-lookup"><span data-stu-id="78f8a-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="78f8a-344">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-345">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-346">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78f8a-347">Online-Besprechungs-Add-in für lync 2010</span><span class="sxs-lookup"><span data-stu-id="78f8a-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="78f8a-348">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-349">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-350">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78f8a-351">Office Communicator 2007 R2-Konferenz-Add-in</span><span class="sxs-lookup"><span data-stu-id="78f8a-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="78f8a-352">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-353">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="78f8a-354">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="78f8a-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="78f8a-355">Unterstützung für den Beitritt zu Besprechungen</span><span class="sxs-lookup"><span data-stu-id="78f8a-355">Support for Joining Meetings</span></span>

<span data-ttu-id="78f8a-356">Alle von lync Server 2013 unterstützten Clients dürfen lync 2013 Besprechungen beitreten.</span><span class="sxs-lookup"><span data-stu-id="78f8a-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="78f8a-357">Da lync Web App eine Webkomponente des Servers ist, wird in Fällen, in denen lync Web App für den Beitritt zu einer lync Server 2013 Besprechung verwendet wird, die neuere Version von lync Web App immer verwendet.</span><span class="sxs-lookup"><span data-stu-id="78f8a-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="78f8a-358">Lync 2013 Clients können Besprechungen, die auf lync 2010 gehostet werden, und Office Communications Server 2007 R2 mit heruntergestuften Funktionen verbinden.</span><span class="sxs-lookup"><span data-stu-id="78f8a-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="78f8a-359">In-Meeting-Features sind durch die Version des Servers, auf dem die Besprechung gehostet wird, limitiert.</span><span class="sxs-lookup"><span data-stu-id="78f8a-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78f8a-360">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78f8a-360">See Also</span></span>


[<span data-ttu-id="78f8a-361">Lync Windows Store-App-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="78f8a-362">Neue Konferenzfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="78f8a-363">Neuerungen für Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78f8a-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

