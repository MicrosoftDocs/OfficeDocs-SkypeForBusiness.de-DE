---
title: 'Lync Server 2013: Client Interoperabilität in lync 2013'
description: 'Lync Server 2013: Client Interoperabilität in lync 2013.'
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
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549611"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="d664e-103">Client Interoperabilität in lync 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d664e-104">_**Letztes Änderungsstand des Themas:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="d664e-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="d664e-105">In diesem Thema wird erläutert, wie Microsoft lync Server 2013 Clients in früheren Versionen von lync Server und Office Communications Server nebeneinander bestehen und mit Clients interagieren können.</span><span class="sxs-lookup"><span data-stu-id="d664e-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="d664e-106">Server-und Client Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="d664e-106">Server and Client Compatibility</span></span>

<span data-ttu-id="d664e-107">In der folgenden Tabelle ist aufgeführt, welche Kombinationen von Client- und Serverversionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d664e-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="d664e-108">Diese Tabelle gibt an, ob die Anmeldung unterstützt wird, wenn der Client versucht, eine Verbindung mit dem angezeigten Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d664e-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="d664e-109">Lync Server 2013 unterstützt die vorherige Client Version.</span><span class="sxs-lookup"><span data-stu-id="d664e-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="d664e-110">Im Gegensatz zu früheren Versionen unterstützt lync Server 2010 auch die neuen lync 2013-Clients.</span><span class="sxs-lookup"><span data-stu-id="d664e-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="d664e-111">Auf diese Weise können Organisationen, die ein Upgrade von lync Server 2010 durchführen, neue Clients unabhängig von lync Server Upgrades Ausrollen.</span><span class="sxs-lookup"><span data-stu-id="d664e-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d664e-112">Client</span><span class="sxs-lookup"><span data-stu-id="d664e-112">Client</span></span></th>
<th><span data-ttu-id="d664e-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="d664e-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="d664e-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d664e-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d664e-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d664e-117">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="d664e-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="d664e-119">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d664e-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d664e-121">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-122">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-123">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="d664e-125">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-126">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-127">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d664e-129">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-130">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-131">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d664e-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d664e-133">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-134">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-135">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-136">Lync 2010 Gruppen Chat</span><span class="sxs-lookup"><span data-stu-id="d664e-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="d664e-137">Unterstützt1</span><span class="sxs-lookup"><span data-stu-id="d664e-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="d664e-138">Unterstützt2</span><span class="sxs-lookup"><span data-stu-id="d664e-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="d664e-139">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d664e-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="d664e-141">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-142">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-143">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="d664e-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="d664e-145">Nicht Supported3</span><span class="sxs-lookup"><span data-stu-id="d664e-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="d664e-146">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-147">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d664e-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d664e-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="d664e-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="d664e-150">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-151">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-152">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="d664e-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d664e-153">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-154">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-155">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="d664e-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="d664e-157">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-158">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-159">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d664e-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="d664e-161">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-162">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-163">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-164">Lync Windows Store-App</span><span class="sxs-lookup"><span data-stu-id="d664e-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="d664e-165">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-166">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-167">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d664e-168">Details zu 1Für finden Sie unter [Migration from lync Server 2010, Group Chat oder Office Communications Server 2007 R2 Group Chat to lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d664e-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="d664e-169">2in Microsoft lync Server 2010 war die gruppenchatfunktion mit dem Gruppenchat Server, einer vertrauenswürdigen Drittanbieteranwendung für lync Server 2010, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d664e-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="d664e-170">Lync 2013 Clients sind nicht mit lync Server 2010, Gruppen Chat, kompatibel.</span><span class="sxs-lookup"><span data-stu-id="d664e-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="d664e-171">3Lync-Webanwendung 2013 bietet nun eine umfassende Besprechungs Erfahrung, einschließlich Computer-Audio und-Video, und gilt als Ersatz für lync 2010 Attendee.</span><span class="sxs-lookup"><span data-stu-id="d664e-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="d664e-172">Lync 2010 Attendee stellt nur dann eine Verbindung mit lync Server 2013 her, wenn Sie einen nicht unterstützten Browser (Internet Explorer 6 oder Internet Explorer 7) und Windows XP verwenden.</span><span class="sxs-lookup"><span data-stu-id="d664e-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="d664e-173">4Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="d664e-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="d664e-174">Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.</span><span class="sxs-lookup"><span data-stu-id="d664e-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="d664e-175">5 Informationen zu Einschränkungen finden Sie unter "Unterstützung von Konferenzfeatures für lync 2013 Clients in lync Server 2010 Besprechungen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="d664e-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="d664e-176">Interoperabilität zwischen Clients</span><span class="sxs-lookup"><span data-stu-id="d664e-176">Interoperability among Clients</span></span>

<span data-ttu-id="d664e-177">Mit der lync Server 2013-Version können verschiedene Clientversionen nahtlos in Peer-zu-Peer-und Konferenzszenarien interagieren.</span><span class="sxs-lookup"><span data-stu-id="d664e-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="d664e-178">In diesem Abschnitt wird die Verfügbarkeit von Features erläutert, wenn Benutzer mit anderen Benutzern interagieren, die unterschiedliche Versionen von Clients und Servern verwenden.</span><span class="sxs-lookup"><span data-stu-id="d664e-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="d664e-179">Unterstützung von Peer-zu-Peer-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d664e-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="d664e-180">Peer-to-Peer-Funktionen werden für Benutzer unterstützt, die in verschiedenen Versionen des Servers verwaltet werden und unterschiedliche Clientversionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d664e-180">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="d664e-181">Die Endbenutzeroberfläche und die verfügbaren Features stehen im Einklang mit den Funktionen des Clients des Benutzers und der Version des Servers, bei dem der Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="d664e-181">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="d664e-182">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="d664e-182">In other words:</span></span>

  - <span data-ttu-id="d664e-183">Wenn ein Benutzer bei lync Server 2013 mit einem älteren Client angemeldet ist, hat der Benutzer die gleiche Erfahrung wie er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d664e-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="d664e-184">Keines der in lync Server 2013 eingeführten neuen Features ist verfügbar, bis der Client des Benutzers aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d664e-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="d664e-185">Beispiele hierfür sind Video Galerie-Ansicht, HD-Video, aktualisierte PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videodaten beim Besprechungseintrag.</span><span class="sxs-lookup"><span data-stu-id="d664e-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="d664e-186">Die neuen Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="d664e-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="d664e-187">Wenn ein Benutzer bei lync Server 2010 mit einem lync 2013-Client angemeldet ist, sind alle neuen Features, die nicht von lync Server 2010 unterstützt werden, erst verfügbar, wenn der Benutzer zu lync Server 2013 verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="d664e-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="d664e-188">In der folgenden Tabelle wird die Verfügbarkeit von Features in Peer-to-Peer-Sitzungen verglichen, in denen der Client entweder lync Server 2013 oder lync Server 2010 angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="d664e-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d664e-189">Lync Web App und lync 2010 Attendee sind Besprechungs bezogene Clients, die nicht in dieser Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d664e-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="d664e-190">Client</span><span class="sxs-lookup"><span data-stu-id="d664e-190">Client</span></span></th>
<th><span data-ttu-id="d664e-191">Instant Messaging</span><span class="sxs-lookup"><span data-stu-id="d664e-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="d664e-192">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="d664e-192">Presence</span></span></th>
<th><span data-ttu-id="d664e-193">VoIP</span><span class="sxs-lookup"><span data-stu-id="d664e-193">Voice</span></span></th>
<th><span data-ttu-id="d664e-194">Video</span><span class="sxs-lookup"><span data-stu-id="d664e-194">Video</span></span></th>
<th><span data-ttu-id="d664e-195">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="d664e-195">Application Sharing</span></span></th>
<th><span data-ttu-id="d664e-196">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="d664e-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d664e-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d664e-198">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-199">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-200">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-201">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-202">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-203">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d664e-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d664e-205">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-206">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-207">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-208">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-209">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-210">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d664e-212">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-213">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-214">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-215">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-216">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-217">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d664e-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="d664e-219">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-220">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-221">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="d664e-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="d664e-223">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-224">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d664e-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="d664e-226">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-227">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-228">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d664e-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d664e-230">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-231">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-232">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-233">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-234">Yes1</span><span class="sxs-lookup"><span data-stu-id="d664e-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="d664e-235">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-236">Öffentliche Chatnachrichten (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="d664e-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="d664e-237">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-238">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-239">Öffentliche Chatnachrichten (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="d664e-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="d664e-240">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-241">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-242">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-243">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d664e-244">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d664e-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="d664e-245">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d664e-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d664e-246">Messenger bis zum Datum der Beendigung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="d664e-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="d664e-247">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d664e-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d664e-248">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="d664e-248">has been announced.</span></span> <span data-ttu-id="d664e-249">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="d664e-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="d664e-250">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden.</span><span class="sxs-lookup"><span data-stu-id="d664e-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d664e-251">Messenger.</span><span class="sxs-lookup"><span data-stu-id="d664e-251">Messenger.</span></span> <span data-ttu-id="d664e-252">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="d664e-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="d664e-253">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="d664e-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d664e-254">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d664e-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d664e-255">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</span><span class="sxs-lookup"><span data-stu-id="d664e-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d664e-256">1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d664e-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d664e-257">Die Desktop Freigabe zwischen Office Communicator 2007 R2 und Skype for Business 2015 kann nicht vom neueren Client initiiert werden, wenn die Skype for Business 2015 Client-Benutzeroberfläche erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="d664e-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="d664e-258">Unterstützung von Konferenzfeatures für lync 2013 Clients in lync Server 2010 Besprechungen</span><span class="sxs-lookup"><span data-stu-id="d664e-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="d664e-259">Wenn Benutzer lync Server 2010 Besprechungen mit einem lync 2013-Clientteil nehmen, haben Sie Zugriff auf lync 2013-Clientfeatures mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="d664e-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="d664e-260">In den Verwaltungsoptionen für **Teilnehmer** , auf die durch den Hinweis auf das Symbol Personen im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechungs-Chat** Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="d664e-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="d664e-261">Die Katalogansicht funktioniert nicht in Videokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="d664e-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="d664e-262">Der Benutzer sieht anstelle aller Lautsprecher nur den aktiven Lautsprecher.</span><span class="sxs-lookup"><span data-stu-id="d664e-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="d664e-263">In der Liste der Optionen zum **Auswählen eines Layouts** ist die **Katalogansicht** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d664e-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="d664e-264">Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d664e-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="d664e-265">Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Verwaltungsoptionen **Video Spotlight** und **PIN-an-Katalog** -Teilnehmerverwaltung Sperren nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d664e-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="d664e-266">Unterstützung von Konferenzfeatures in lync Server 2013 Besprechungen</span><span class="sxs-lookup"><span data-stu-id="d664e-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="d664e-267">Lync Server 2013 stellt neue Konferenzfeatures bereit, die Benutzern zur Verfügung stehen, nachdem Ihre Konten in lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="d664e-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="d664e-268">Beispiele hierfür sind Video Galerie-Ansicht, HD-Video, PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videodaten beim Besprechungseintrag.</span><span class="sxs-lookup"><span data-stu-id="d664e-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="d664e-269">Die neuen Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="d664e-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d664e-270">In lync Server 2013 Besprechungen werden bestimmte Konferenzfeatures für Benutzer unterstützt, die in unterschiedlichen Versionen des Servers verwaltet werden und unterschiedliche Clients und Clientversionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d664e-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="d664e-271">Wenn Clients an einer lync Server 2013 Besprechung teilnehmen, haben Benutzer Zugriff auf die in dieser Tabelle gezeigten Features und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d664e-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="d664e-272">Client</span><span class="sxs-lookup"><span data-stu-id="d664e-272">Client</span></span></th>
<th><span data-ttu-id="d664e-273">Peer-zu-Peer-Chat</span><span class="sxs-lookup"><span data-stu-id="d664e-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="d664e-274">VoIP</span><span class="sxs-lookup"><span data-stu-id="d664e-274">Voice</span></span></th>
<th><span data-ttu-id="d664e-275">Video</span><span class="sxs-lookup"><span data-stu-id="d664e-275">Video</span></span></th>
<th><span data-ttu-id="d664e-276">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="d664e-276">Application Sharing</span></span></th>
<th><span data-ttu-id="d664e-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d664e-277">PowerPoint</span></span></th>
<th><span data-ttu-id="d664e-278">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="d664e-278">File Transfer</span></span></th>
<th><span data-ttu-id="d664e-279">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="d664e-279">Whiteboard</span></span></th>
<th><span data-ttu-id="d664e-280">Abrufen</span><span class="sxs-lookup"><span data-stu-id="d664e-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d664e-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d664e-282">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-283">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-284">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-285">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-286">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-287">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-288">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-289">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="d664e-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="d664e-291">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-292">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-293">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-294">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-295">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-296">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-297">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-298">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="d664e-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="d664e-300">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-301">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-302">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-303">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-304">Ja2</span><span class="sxs-lookup"><span data-stu-id="d664e-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="d664e-305">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-306">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-307">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d664e-309">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-310">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-311">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-312">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-313">Yes3</span><span class="sxs-lookup"><span data-stu-id="d664e-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="d664e-314">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-315">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="d664e-316">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="d664e-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="d664e-318">Ja</span><span class="sxs-lookup"><span data-stu-id="d664e-318">Yes</span></span></p></td>
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


<span data-ttu-id="d664e-319">1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d664e-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="d664e-320">2 lync Server 2013 verwendet einen aktualisierten Mechanismus für das Hochladen von PowerPoint-Dateien.</span><span class="sxs-lookup"><span data-stu-id="d664e-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="d664e-321">Lync Web App Benutzer, die einer Besprechung beitreten, die ursprünglich auf lync Server 2010 geplant war, können PowerPoint-Präsentationen anzeigen und navigieren, jedoch keine PowerPoint-Dateien hochladen.</span><span class="sxs-lookup"><span data-stu-id="d664e-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="d664e-322">3 Wenn die Besprechung in lync Server 2013 geplant wurde und PowerPoint-Folien von einem lync 2013-Client hochgeladen wurden, verfügen lync 2010 Benutzer über einen schreibgeschützten Zugriff auf die Folien.</span><span class="sxs-lookup"><span data-stu-id="d664e-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="d664e-323">Wenn umgekehrt die PowerPoint-Folien von einem lync 2010-Benutzer hochgeladen wurden, können lync Server 2013 Benutzer anzeigen und Folien und, falls Office-webapps-Server konfiguriert ist, auf neue Funktionen wie höhere Auflösung, Animationen, Folienübergänge und eingebettete Videos zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d664e-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="d664e-324">Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="d664e-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="d664e-325">4Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="d664e-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="d664e-326">Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.</span><span class="sxs-lookup"><span data-stu-id="d664e-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="d664e-327">Planen der Add-in-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d664e-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="d664e-328">Die Server Unterstützung für die unterschiedlichen Planungs-Add-Ins ist konsistent mit der Server-und Client Versionskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="d664e-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="d664e-329">Im Allgemeinen werden die folgenden Planungs-Add-Ins in lync Server 2013 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d664e-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="d664e-330">In früheren Versionen von Add-Ins werden jedoch keine neuen lync 2013-Add-in-Features bereitgestellt, wie beispielsweise die Option zum stumm schalten aller Teilnehmer-Audio-und-Videos beim Besprechungseintrag.</span><span class="sxs-lookup"><span data-stu-id="d664e-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="d664e-331">**Online-Besprechungs-Add-in für lync 2013**     Stellt die gleichen Features wie das Online Besprechungs-Add-in für lync 2010 bereit, wobei die Teilnehmer-stumm Schaltungs Steuerelemente hinzugefügt werden, mit deren Hilfe Besprechungsorganisatoren Konferenzen planen können, bei denen Audio und Video für Teilnehmer standardmäßig stumm geschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="d664e-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="d664e-332">Administratoren können die Besprechungseinladungen der Organisation auch anpassen, indem Sie ein benutzerdefiniertes Logo, eine Support-URL, eine URL für einen rechtlichen Haftungsausschluss oder benutzerdefinierter Fußzeilentext hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d664e-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="d664e-333">**Online-Besprechungs-Add-in für lync 2010**     Bietet Zeitplanung für lync-Besprechungen und entfernt die Möglichkeit, Office Live Meeting Konferenzen zu planen.</span><span class="sxs-lookup"><span data-stu-id="d664e-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="d664e-334">**Office Communicator 2007 R2-Konferenz-Add-in**     Bietet Zeitplanung für Office Live Meeting Konferenzen und Office Communicator 2007 R2 Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="d664e-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="d664e-335">Live Meeting Konferenzen können nicht für lync Server 2013 geplant werden.</span><span class="sxs-lookup"><span data-stu-id="d664e-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="d664e-336">Planen des Clients</span><span class="sxs-lookup"><span data-stu-id="d664e-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="d664e-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="d664e-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="d664e-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d664e-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d664e-340">Online-Besprechungs-Add-in für lync 2013 (kann mit Office 2013, Outlook 2010 und Outlook 2007 verwendet werden)</span><span class="sxs-lookup"><span data-stu-id="d664e-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="d664e-341">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-342">Unterstützt (neue Add-in-Features nicht verfügbar)</span><span class="sxs-lookup"><span data-stu-id="d664e-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="d664e-343">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-344">Lync 2013-Webplaner</span><span class="sxs-lookup"><span data-stu-id="d664e-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="d664e-345">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-346">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-347">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d664e-348">Online-Besprechungs-Add-in für lync 2010</span><span class="sxs-lookup"><span data-stu-id="d664e-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d664e-349">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-350">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-351">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d664e-352">Office Communicator 2007 R2-Konferenz-Add-in</span><span class="sxs-lookup"><span data-stu-id="d664e-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="d664e-353">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-354">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="d664e-355">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d664e-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="d664e-356">Unterstützung für den Beitritt zu Besprechungen</span><span class="sxs-lookup"><span data-stu-id="d664e-356">Support for Joining Meetings</span></span>

<span data-ttu-id="d664e-357">Alle von lync Server 2013 unterstützten Clients dürfen lync 2013 Besprechungen beitreten.</span><span class="sxs-lookup"><span data-stu-id="d664e-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="d664e-358">Da lync Web App eine Webkomponente des Servers ist, wird in Fällen, in denen lync Web App für den Beitritt zu einer lync Server 2013 Besprechung verwendet wird, die neuere Version von lync Web App immer verwendet.</span><span class="sxs-lookup"><span data-stu-id="d664e-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="d664e-359">Lync 2013 Clients können Besprechungen, die auf lync 2010 gehostet werden, und Office Communications Server 2007 R2 mit heruntergestuften Funktionen verbinden.</span><span class="sxs-lookup"><span data-stu-id="d664e-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="d664e-360">In-Meeting-Features sind durch die Version des Servers, auf dem die Besprechung gehostet wird, limitiert.</span><span class="sxs-lookup"><span data-stu-id="d664e-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d664e-361">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d664e-361">See Also</span></span>


[<span data-ttu-id="d664e-362">Lync Windows Store-App-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="d664e-363">Neue Konferenzfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="d664e-364">Neuerungen für Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d664e-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

