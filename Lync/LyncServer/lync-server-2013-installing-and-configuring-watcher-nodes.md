---
title: 'Lync Server 2013: Installieren und Konfigurieren von Watcher-Knoten'
description: 'Lync Server 2013: Installieren und Konfigurieren von Watcher-Knoten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574001"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="ec08b-103">Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec08b-103">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec08b-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ec08b-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ec08b-105">*Watcher-Knoten* sind Computer, die regelmäßig lync Server synthetischen Transaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-105">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="ec08b-106">*Synthetische Transaktionen* sind Windows PowerShell-Cmdlets, mit denen sichergestellt wird, dass wichtige Endbenutzerszenarien wie die Möglichkeit zum Anmelden am System oder die Möglichkeit zum Austauschen von Sofortnachrichten wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ec08b-106">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="ec08b-107">Für lync Server 2013 kann System Center Operations Manager die synthetischen Transaktionen ausführen, die in der folgenden Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ec08b-107">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="ec08b-108">In der Tabelle sind drei verschiedene synthetische Transaktionstypen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ec08b-108">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="ec08b-109">**Standard**.</span><span class="sxs-lookup"><span data-stu-id="ec08b-109">**Default**.</span></span> <span data-ttu-id="ec08b-110">Hierbei handelt es sich um die synthetischen Transaktionen, die standardmäßig ein Watcher-Knoten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ec08b-110">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="ec08b-111">Wenn Sie einen neuen Watcher-Knoten erstellen, haben Sie die Möglichkeit, anzugeben, welche synthetischen Transaktionen dieser Knoten ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="ec08b-111">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="ec08b-112">(Dies ist der Zweck des Parameters "Tests", der vom Cmdlet " **New-CsWatcherNodeConfiguration** " verwendet wird.) Wenn Sie den Parameter Tests nicht verwenden, wenn der Watcher-Knoten erstellt wird, werden alle synthetischen Standardtransaktionen automatisch ausgeführt, und es werden keine synthetischen, nicht standardmäßigen Transaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec08b-112">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="ec08b-113">Das bedeutet beispielsweise, dass der Watcher-Knoten so konfiguriert wird, dass der Test-CsAddressBookService Test ausgeführt wird, aber nicht für die Ausführung des Test-CsExumConnectivity Tests konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ec08b-113">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="ec08b-114">**Nicht Standard**.</span><span class="sxs-lookup"><span data-stu-id="ec08b-114">**Non-default**.</span></span> <span data-ttu-id="ec08b-115">Wie es der Name schon sagt, handelt es sich bei synthetischen Transaktionen dieses Typs um Tests, die vom Watcher-Knoten nicht standardmäßig durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-115">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="ec08b-116">Der Knoten kann jedoch zum Ausführen von nicht standardmäßigen synthetischen Transaktionen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-116">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="ec08b-117">Dies können Sie beim Erstellen des Watcher-Knotens (mithilfe des **New-CsWatcherNodeConfiguration**-Cmdlets) oder jederzeit später vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-117">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="ec08b-118">Für viele der nicht standardmäßigen synthetischen Transaktionen sind zusätzliche Einrichtungsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec08b-118">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="ec08b-119">Ausführliche Informationen finden Sie unter [spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="ec08b-119">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="ec08b-120">**Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="ec08b-120">**Extended**.</span></span> <span data-ttu-id="ec08b-121">Erweiterte Tests sind ein spezieller Typ von nicht standardmäßigen synthetischen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-121">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="ec08b-122">Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-122">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="ec08b-123">Dies kann nützlich sein, wenn bestimmte Verhaltensweisen – wie zum Beispiel mehrere PSTN-VoIP-Routen für einen Pool – überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-123">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="ec08b-124">Zur Konfiguration werden einem Watcher-Knoten einfach mehrere Instanzen eines erweiterten Tests hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec08b-124">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="ec08b-125">Ausführliche Informationen zum Prozess des Hinzufügens weiterer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Managing Watcher Nodes in lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="ec08b-125">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="ec08b-126">Sie können die lync Server-Verwaltungsshell verwenden, um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-126">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="ec08b-127">Zu den für Watcher-Knoten verfügbaren synthetischen Transaktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="ec08b-127">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec08b-128">Cmdlet-Name (Test-Name)</span><span class="sxs-lookup"><span data-stu-id="ec08b-128">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="ec08b-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec08b-129">Description</span></span></th>
<th><span data-ttu-id="ec08b-130">Typ von synthetischer Transaktion</span><span class="sxs-lookup"><span data-stu-id="ec08b-130">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-131">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="ec08b-131">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-132">Überprüft, ob Benutzer in der Lage sind, Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-132">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-133">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-133">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-134">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="ec08b-134">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-135">Überprüft, ob Benutzer in der Lage sind, HTTP Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-135">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-136">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-136">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-137">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="ec08b-137">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-138">Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Sofortnachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-138">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-139">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-139">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-140">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="ec08b-140">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-141">Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).</span><span class="sxs-lookup"><span data-stu-id="ec08b-141">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="ec08b-142">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-142">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-143">Test-CsPresence (Anwesenheit)</span><span class="sxs-lookup"><span data-stu-id="ec08b-143">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-144">Überprüft, ob Benutzer in der Lage sind, die Anwesenheit anderer Benutzer zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-144">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-145">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-145">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-146">Test-CsRegistration (Registrierung)</span><span class="sxs-lookup"><span data-stu-id="ec08b-146">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-147">Überprüft, ob Benutzer in der Lage sind, sich bei Lync anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-147">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-148">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-148">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-149">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="ec08b-149">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-150">Wird nicht mit der lokalen Version von lync Server 2013 verwendet</span><span class="sxs-lookup"><span data-stu-id="ec08b-150">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="ec08b-151">Erweitert</span><span class="sxs-lookup"><span data-stu-id="ec08b-151">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-152">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="ec08b-152">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-153">Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-153">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="ec08b-154">Nicht Standard, Erweitert</span><span class="sxs-lookup"><span data-stu-id="ec08b-154">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-155">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="ec08b-155">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-156">Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-156">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-157">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-157">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="ec08b-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-159">Überprüft, ob die Audio-/Video-Edgeserver in der Lage sind, Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-159">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-160">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-160">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-161">Test-CsDataConference (dataconference)</span><span class="sxs-lookup"><span data-stu-id="ec08b-161">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-162">Überprüft, ob Benutzer an einer Datenzusammenarbeitskonferenz (eine Online-Besprechung, zu der Aktivitäten wie Whiteboards und Abstimmungen gehören) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="ec08b-162">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-163">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-163">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-164">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="ec08b-164">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-165">Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (um) herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="ec08b-165">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="ec08b-166">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-166">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-167">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="ec08b-167">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-168">Überprüft, ob Benutzer in der Lage sind, in Konferenzen Sofortnachrichten zu senden und an Sofortnachrichtengesprächen mit drei oder mehr Personen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-168">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-169">Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-169">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-170">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="ec08b-170">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-171">Überprüft, ob Benutzer in der Lage sind, geplante Besprechungen zu erstellen und an geplanten Besprechungen über einen Weblink teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-171">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-172">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-172">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-173">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="ec08b-173">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-174">Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Sofortnachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-174">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-175">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-175">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="ec08b-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-177">Bestätigt, dass Benutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.</span><span class="sxs-lookup"><span data-stu-id="ec08b-177">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-178">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-178">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="ec08b-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-180">Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="ec08b-180">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="ec08b-181">Der einheitliche Kontaktspeicher bietet Benutzern eine Möglichkeit, eine einzelne Gruppe von Kontakten zu verwalten, auf die mithilfe von lync 2013, Outlook und/oder Outlook Web Access zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec08b-181">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-182">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-182">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-183">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="ec08b-183">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="ec08b-184">Überprüft, ob eine Sofortnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec08b-184">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="ec08b-185">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="ec08b-185">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ec08b-186">Sie müssen keine Watcher-Knoten installieren, um System Center Operations Manager verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="ec08b-186">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="ec08b-187">Wenn Sie diese Knoten nicht installieren, können Sie weiterhin Echtzeitwarnungen von lync Server 2013 Komponenten erhalten, wenn ein Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="ec08b-187">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="ec08b-188">(Die Komponente und das Benutzer Management Pack verwenden keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien mithilfe des Active Monitoring Management Packs überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec08b-188">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec08b-189">Administratoren können synthetische Transaktionen auch manuell ausführen, ohne dass dazu der Operations Manager installiert oder verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ec08b-189">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="ec08b-190">Ausführliche Informationen zu den verschiedenen Test-Cs-Cmdlets finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">lync Server 2013 Cmdlets-Index</A>.</span><span class="sxs-lookup"><span data-stu-id="ec08b-190">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="ec08b-191">Je nach der Größe Ihrer Bereitstellung können synthetische Transaktionen einen großen Teil Ihrer Arbeitsspeicher- und Prozessorressourcen in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-191">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="ec08b-192">Aus diesem Grund wird empfohlen, als Watcher-Knoten einen dedizierten Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-192">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="ec08b-193">Beispielsweise sollten Sie keine Front-End-Server konfigurieren, die als Watcher-Knoten fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="ec08b-193">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="ec08b-194">Watcher-Knoten sollten die folgenden Hardwarespezifikationen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ec08b-194">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec08b-195">Ein Legacy Microsoft lync Server 2010 Watcher-Knoten kann nicht mit einem lync Server 2013 Watcher-Knoten auf demselben Computer zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="ec08b-195">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="ec08b-196">Dies liegt daran, dass die Hauptsystem Dateien für lync Server 2010 und lync Server 2013 nicht auf demselben Computer installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ec08b-196">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="ec08b-197">Lync Server 2013 Watcher-Knoten können jedoch gleichzeitig sowohl lync Server 2013 als auch lync Server 2010 überwachen.</span><span class="sxs-lookup"><span data-stu-id="ec08b-197">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="ec08b-198">Die synthetischen Transaktionen vom Typ "Standard" werden in beiden Produktversionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec08b-198">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="ec08b-199">Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="ec08b-199">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="ec08b-200">Konnektivität zu Pools für Benutzer innerhalb des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="ec08b-200">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="ec08b-201">Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten</span><span class="sxs-lookup"><span data-stu-id="ec08b-201">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="ec08b-202">Konnektivität zu Branch Office Appliances</span><span class="sxs-lookup"><span data-stu-id="ec08b-202">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="ec08b-203">Konnektivität mit lync Server 2010 innerhalb des Unternehmens und über Umkreisnetzwerke.</span><span class="sxs-lookup"><span data-stu-id="ec08b-203">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="ec08b-204">Zur leichteren Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb oder außerhalb des Unternehmens zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ec08b-204">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="ec08b-205">Ausführliche Informationen finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="ec08b-205">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="ec08b-206">Wenn Sie einen Computer als Watcher-Knoten konfigurieren möchten, müssen Sie die folgenden Schritte ausführen, nachdem Sie System Center Operations Manager installiert und die lync Server 2013 Management Packs importiert haben.</span><span class="sxs-lookup"><span data-stu-id="ec08b-206">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="ec08b-207">Bevor Sie die lync Server 2013 Kerndateien und die System Center-Agentdateien installieren, sollten Sie auch sicherstellen, dass der Watcher-Knoten Computer alle Voraussetzungen für die Installation von lync Server 2013 erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ec08b-207">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="ec08b-208">Außerdem sollten auf dem Watcher-Computer auch die folgenden Komponenten installiert sein:</span><span class="sxs-lookup"><span data-stu-id="ec08b-208">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec08b-209">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="ec08b-209">Hardware component</span></span></th>
<th><span data-ttu-id="ec08b-210">Mindestanforderung</span><span class="sxs-lookup"><span data-stu-id="ec08b-210">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-211">CPU</span><span class="sxs-lookup"><span data-stu-id="ec08b-211">CPU</span></span></p></td>
<td><p><span data-ttu-id="ec08b-212">Eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="ec08b-212">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ec08b-213">64-Bit-Prozessor, Quad-Core, 2,33 GHz oder höher</span><span class="sxs-lookup"><span data-stu-id="ec08b-213">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="ec08b-214">64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher</span><span class="sxs-lookup"><span data-stu-id="ec08b-214">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec08b-215">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="ec08b-215">Memory</span></span></p></td>
<td><p><span data-ttu-id="ec08b-216">8 GB</span><span class="sxs-lookup"><span data-stu-id="ec08b-216">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec08b-217">Netzwerkbetriebs System</span><span class="sxs-lookup"><span data-stu-id="ec08b-217">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ec08b-218">1 Netzwerkadapter 1 Gbit/s</span><span class="sxs-lookup"><span data-stu-id="ec08b-218">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="ec08b-219">Windows Server 2008 R2, Windows Server 2012 oder</span><span class="sxs-lookup"><span data-stu-id="ec08b-219">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="ec08b-220">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec08b-220">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="ec08b-221">Die Vollversion von .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ec08b-221">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="ec08b-222">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="ec08b-222">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="ec08b-223">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ec08b-223">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ec08b-224">Sobald alle Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten wie folgt installieren:</span><span class="sxs-lookup"><span data-stu-id="ec08b-224">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="ec08b-225">Installieren der lync Server 2013 Kerndateien auf dem Watcher-Knoten Computer.</span><span class="sxs-lookup"><span data-stu-id="ec08b-225">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="ec08b-226">Installieren von System Center Operations Manager-Agent auf dem Monitor Knoten Computer.</span><span class="sxs-lookup"><span data-stu-id="ec08b-226">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="ec08b-227">Ausführen der Datei WATCHERNODE.MSI</span><span class="sxs-lookup"><span data-stu-id="ec08b-227">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="ec08b-228">Konfigurieren von Testbenutzern für den Watcher-Knoten mithilfe des **CsWatcherNodeConfiguration**-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ec08b-228">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

