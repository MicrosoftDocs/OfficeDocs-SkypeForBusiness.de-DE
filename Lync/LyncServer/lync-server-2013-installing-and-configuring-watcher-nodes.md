---
title: 'Lync Server 2013: Installieren und Konfigurieren von Watcher-Knoten'
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
ms.openlocfilehash: 0cd57e3b78e3e16ac9d640536771cf2b5b90773a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="c065a-102">Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c065a-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c065a-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c065a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c065a-104">*Watcher-Knoten* sind Computer, die regelmäßig lync Server synthetischen Transaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c065a-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="c065a-105">*Synthetische Transaktionen* sind Windows PowerShell-Cmdlets, mit denen sichergestellt wird, dass wichtige Endbenutzerszenarien wie die Möglichkeit zum Anmelden am System oder die Möglichkeit zum Austauschen von Sofortnachrichten wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c065a-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="c065a-106">Für lync Server 2013 kann System Center Operations Manager die synthetischen Transaktionen ausführen, die in der folgenden Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="c065a-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="c065a-107">In der Tabelle sind drei verschiedene synthetische Transaktionstypen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c065a-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="c065a-108">**Standard**.</span><span class="sxs-lookup"><span data-stu-id="c065a-108">**Default**.</span></span> <span data-ttu-id="c065a-109">Hierbei handelt es sich um die synthetischen Transaktionen, die standardmäßig ein Watcher-Knoten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c065a-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="c065a-110">Wenn Sie einen neuen Watcher-Knoten erstellen, haben Sie die Möglichkeit, anzugeben, welche synthetischen Transaktionen dieser Knoten ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="c065a-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="c065a-111">(Dies ist der Zweck des Parameters "Tests", der vom Cmdlet " **New-CsWatcherNodeConfiguration** " verwendet wird.) Wenn Sie den Parameter Tests nicht verwenden, wenn der Watcher-Knoten erstellt wird, werden alle synthetischen Standardtransaktionen automatisch ausgeführt, und es werden keine synthetischen, nicht standardmäßigen Transaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c065a-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="c065a-112">Das bedeutet beispielsweise, dass der Watcher-Knoten so konfiguriert wird, dass der Test-CsAddressBookService-Test ausgeführt wird, aber nicht für die Ausführung des Test-csexumconnectivity "-Tests konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c065a-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="c065a-113">**Nicht Standard**.</span><span class="sxs-lookup"><span data-stu-id="c065a-113">**Non-default**.</span></span> <span data-ttu-id="c065a-114">Wie es der Name schon sagt, handelt es sich bei synthetischen Transaktionen dieses Typs um Tests, die vom Watcher-Knoten nicht standardmäßig durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c065a-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="c065a-115">Der Knoten kann jedoch zum Ausführen von nicht standardmäßigen synthetischen Transaktionen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c065a-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="c065a-116">Dies können Sie beim Erstellen des Watcher-Knotens (mithilfe des **New-CsWatcherNodeConfiguration**-Cmdlets) oder jederzeit später vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c065a-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="c065a-117">Für viele der nicht standardmäßigen synthetischen Transaktionen sind zusätzliche Einrichtungsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c065a-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="c065a-118">Ausführliche Informationen finden Sie unter [spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="c065a-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="c065a-119">**Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="c065a-119">**Extended**.</span></span> <span data-ttu-id="c065a-120">Erweiterte Tests sind ein spezieller Typ von nicht standardmäßigen synthetischen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="c065a-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="c065a-121">Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c065a-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="c065a-122">Dies kann nützlich sein, wenn bestimmte Verhaltensweisen – wie zum Beispiel mehrere PSTN-VoIP-Routen für einen Pool – überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c065a-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="c065a-123">Zur Konfiguration werden einem Watcher-Knoten einfach mehrere Instanzen eines erweiterten Tests hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c065a-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="c065a-124">Ausführliche Informationen zum Prozess des Hinzufügens weiterer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Managing Watcher Nodes in lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="c065a-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="c065a-125">Sie können die lync Server-Verwaltungsshell verwenden, um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c065a-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="c065a-126">Zu den für Watcher-Knoten verfügbaren synthetischen Transaktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="c065a-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c065a-127">Cmdlet-Name (Test-Name)</span><span class="sxs-lookup"><span data-stu-id="c065a-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="c065a-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c065a-128">Description</span></span></th>
<th><span data-ttu-id="c065a-129">Typ von synthetischer Transaktion</span><span class="sxs-lookup"><span data-stu-id="c065a-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c065a-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="c065a-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="c065a-131">Überprüft, ob Benutzer in der Lage sind, Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.</span><span class="sxs-lookup"><span data-stu-id="c065a-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="c065a-132">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="c065a-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="c065a-134">Überprüft, ob Benutzer in der Lage sind, HTTP Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.</span><span class="sxs-lookup"><span data-stu-id="c065a-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="c065a-135">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="c065a-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="c065a-137">Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Sofortnachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="c065a-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="c065a-138">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="c065a-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="c065a-140">Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).</span><span class="sxs-lookup"><span data-stu-id="c065a-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="c065a-141">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-142">Test-CsPresence (Anwesenheit)</span><span class="sxs-lookup"><span data-stu-id="c065a-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="c065a-143">Überprüft, ob Benutzer in der Lage sind, die Anwesenheit anderer Benutzer zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="c065a-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="c065a-144">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-145">Test-CsRegistration (Registrierung)</span><span class="sxs-lookup"><span data-stu-id="c065a-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="c065a-146">Überprüft, ob Benutzer in der Lage sind, sich bei Lync anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c065a-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="c065a-147">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="c065a-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="c065a-149">Wird nicht mit der lokalen Version von lync Server 2013 verwendet</span><span class="sxs-lookup"><span data-stu-id="c065a-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="c065a-150">Erweitert</span><span class="sxs-lookup"><span data-stu-id="c065a-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-151">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="c065a-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="c065a-152">Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.</span><span class="sxs-lookup"><span data-stu-id="c065a-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="c065a-153">Nicht Standard, Erweitert</span><span class="sxs-lookup"><span data-stu-id="c065a-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="c065a-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="c065a-155">Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c065a-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="c065a-156">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-157">Test-csavedgeconnectivity "(AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="c065a-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="c065a-158">Überprüft, ob die Audio-/Video-Edgeserver in der Lage sind, Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c065a-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="c065a-159">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-160">Test-csdataconference "(dataconference)</span><span class="sxs-lookup"><span data-stu-id="c065a-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="c065a-161">Überprüft, ob Benutzer an einer Datenzusammenarbeitskonferenz (eine Online-Besprechung, zu der Aktivitäten wie Whiteboards und Abstimmungen gehören) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="c065a-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="c065a-162">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-163">Test-csexumconnectivity "(ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="c065a-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="c065a-164">Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (um) herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="c065a-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="c065a-165">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-166">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="c065a-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="c065a-167">Überprüft, ob Benutzer in der Lage sind, in Konferenzen Sofortnachrichten zu senden und an Sofortnachrichtengesprächen mit drei oder mehr Personen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c065a-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="c065a-168">Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-169">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="c065a-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="c065a-170">Überprüft, ob Benutzer in der Lage sind, geplante Besprechungen zu erstellen und an geplanten Besprechungen über einen Weblink teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c065a-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="c065a-171">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="c065a-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="c065a-173">Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Sofortnachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="c065a-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="c065a-174">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-175">Test-cspersistentchatmessage "(PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="c065a-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="c065a-176">Bestätigt, dass Benutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.</span><span class="sxs-lookup"><span data-stu-id="c065a-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="c065a-177">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="c065a-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="c065a-179">Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="c065a-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="c065a-180">Der einheitliche Kontaktspeicher bietet Benutzern eine Möglichkeit, eine einzelne Gruppe von Kontakten zu verwalten, auf die mithilfe von lync 2013, Outlook und/oder Outlook Web Access zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c065a-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="c065a-181">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-182">Test-csxmppim "(XmppIM)</span><span class="sxs-lookup"><span data-stu-id="c065a-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="c065a-183">Überprüft, ob eine Sofortnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c065a-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="c065a-184">Nicht Standard</span><span class="sxs-lookup"><span data-stu-id="c065a-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c065a-185">Sie müssen keine Watcher-Knoten installieren, um System Center Operations Manager verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="c065a-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="c065a-186">Wenn Sie diese Knoten nicht installieren, können Sie weiterhin Echtzeitwarnungen von lync Server 2013 Komponenten erhalten, wenn ein Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="c065a-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="c065a-187">(Die Komponente und das Benutzer Management Pack verwenden keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien mithilfe des Active Monitoring Management Packs überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="c065a-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c065a-188">Administratoren können synthetische Transaktionen auch manuell ausführen, ohne dass dazu der Operations Manager installiert oder verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c065a-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="c065a-189">Ausführliche Informationen zu den verschiedenen Cmdlets für Test-CS finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">lync Server 2013 Cmdlets-Index</A>.</span><span class="sxs-lookup"><span data-stu-id="c065a-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="c065a-190">Je nach der Größe Ihrer Bereitstellung können synthetische Transaktionen einen großen Teil Ihrer Arbeitsspeicher- und Prozessorressourcen in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="c065a-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="c065a-191">Aus diesem Grund wird empfohlen, als Watcher-Knoten einen dedizierten Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c065a-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="c065a-192">Beispielsweise sollten Sie keine Front-End-Server konfigurieren, die als Watcher-Knoten fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="c065a-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="c065a-193">Watcher-Knoten sollten die folgenden Hardwarespezifikationen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="c065a-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c065a-194">Ein Legacy Microsoft lync Server 2010 Watcher-Knoten kann nicht mit einem lync Server 2013 Watcher-Knoten auf demselben Computer zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="c065a-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="c065a-195">Dies liegt daran, dass die Hauptsystem Dateien für lync Server 2010 und lync Server 2013 nicht auf demselben Computer installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c065a-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="c065a-196">Lync Server 2013 Watcher-Knoten können jedoch gleichzeitig sowohl lync Server 2013 als auch lync Server 2010 überwachen.</span><span class="sxs-lookup"><span data-stu-id="c065a-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="c065a-197">Die synthetischen Transaktionen vom Typ "Standard" werden in beiden Produktversionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c065a-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="c065a-198">Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="c065a-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="c065a-199">Konnektivität zu Pools für Benutzer innerhalb des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="c065a-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="c065a-200">Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten</span><span class="sxs-lookup"><span data-stu-id="c065a-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="c065a-201">Konnektivität zu Branch Office Appliances</span><span class="sxs-lookup"><span data-stu-id="c065a-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="c065a-202">Konnektivität mit lync Server 2010 innerhalb des Unternehmens und über Umkreisnetzwerke.</span><span class="sxs-lookup"><span data-stu-id="c065a-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="c065a-203">Zur leichteren Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb oder außerhalb des Unternehmens zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c065a-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="c065a-204">Ausführliche Informationen finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="c065a-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="c065a-205">Wenn Sie einen Computer als Watcher-Knoten konfigurieren möchten, müssen Sie die folgenden Schritte ausführen, nachdem Sie System Center Operations Manager installiert und die lync Server 2013 Management Packs importiert haben.</span><span class="sxs-lookup"><span data-stu-id="c065a-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="c065a-206">Bevor Sie die lync Server 2013 Kerndateien und die System Center-Agentdateien installieren, sollten Sie auch sicherstellen, dass der Watcher-Knoten Computer alle Voraussetzungen für die Installation von lync Server 2013 erfüllt.</span><span class="sxs-lookup"><span data-stu-id="c065a-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="c065a-207">Außerdem sollten auf dem Watcher-Computer auch die folgenden Komponenten installiert sein:</span><span class="sxs-lookup"><span data-stu-id="c065a-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c065a-208">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="c065a-208">Hardware component</span></span></th>
<th><span data-ttu-id="c065a-209">Mindestanforderung</span><span class="sxs-lookup"><span data-stu-id="c065a-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c065a-210">CPU</span><span class="sxs-lookup"><span data-stu-id="c065a-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="c065a-211">Eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="c065a-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c065a-212">64-Bit-Prozessor, Quad-Core, 2,33 GHz oder höher</span><span class="sxs-lookup"><span data-stu-id="c065a-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="c065a-213">64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher</span><span class="sxs-lookup"><span data-stu-id="c065a-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c065a-214">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="c065a-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="c065a-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="c065a-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c065a-216">Netzwerkbetriebs System</span><span class="sxs-lookup"><span data-stu-id="c065a-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c065a-217">1 Netzwerkadapter 1 Gbit/s</span><span class="sxs-lookup"><span data-stu-id="c065a-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="c065a-218">Windows Server 2008 R2, Windows Server 2012 oder</span><span class="sxs-lookup"><span data-stu-id="c065a-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="c065a-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c065a-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="c065a-220">Die Vollversion von .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="c065a-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="c065a-221">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="c065a-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="c065a-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c065a-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="c065a-223">Sobald alle Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten wie folgt installieren:</span><span class="sxs-lookup"><span data-stu-id="c065a-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="c065a-224">Installieren der lync Server 2013 Kerndateien auf dem Watcher-Knoten Computer.</span><span class="sxs-lookup"><span data-stu-id="c065a-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="c065a-225">Installieren von System Center Operations Manager-Agent auf dem Monitor Knoten Computer.</span><span class="sxs-lookup"><span data-stu-id="c065a-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="c065a-226">Ausführen der Datei WATCHERNODE.MSI</span><span class="sxs-lookup"><span data-stu-id="c065a-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="c065a-227">Konfigurieren von Testbenutzern für den Watcher-Knoten mithilfe des **CsWatcherNodeConfiguration**-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c065a-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

