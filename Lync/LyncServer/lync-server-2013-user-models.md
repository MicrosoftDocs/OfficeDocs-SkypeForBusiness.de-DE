---
title: 'Lync Server 2013: Benutzermodelle'
description: 'Lync Server 2013: Benutzermodelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15be3f4c002de6cfb9ade4f13d80aedb59d76a82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569761"
---
# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="c97cf-103">Benutzermodelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c97cf-103">User models in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c97cf-104">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c97cf-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c97cf-105">Die hier beschriebenen Benutzermodelle bilden die Grundlage für die Kapazitäts Planungs Messungen und-Empfehlungen, die unter [Kapazitätsplanung für lync Server 2013 mithilfe der Benutzermodelle](lync-server-2013-capacity-planning-using-the-user-models.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-105">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="c97cf-106">Lync Server 2013-Benutzermodelle</span><span class="sxs-lookup"><span data-stu-id="c97cf-106">Lync Server 2013 User Models</span></span>

<span data-ttu-id="c97cf-107">In der folgenden Tabelle wird das Benutzermodell für die Registrierung, Kontakte, Chatnachrichten und Anwesenheitsinformationen für lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c97cf-107">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="c97cf-108">Benutzermodell für Umgebung und Registrierung</span><span class="sxs-lookup"><span data-stu-id="c97cf-108">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-109">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-109">Category</span></span></th>
<th><span data-ttu-id="c97cf-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-111">Bereitstellungsgröße und Verteilung</span><span class="sxs-lookup"><span data-stu-id="c97cf-111">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-112">Es wird eine große Bereitstellung mit drei zentralen Standorten und einem Front-End-Pool pro Standort modelliert.</span><span class="sxs-lookup"><span data-stu-id="c97cf-112">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-113">Prozentsatz an Active Directory-Benutzern</span><span class="sxs-lookup"><span data-stu-id="c97cf-113">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="c97cf-114">Es wird davon ausgegangen, dass 70% aller Active Directory-Benutzer in der Organisation für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c97cf-114">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="c97cf-115">80% dieser aktivierten Benutzer sind bei lync Server jeden Tag angemeldet (80% Gleichzeitigkeit).</span><span class="sxs-lookup"><span data-stu-id="c97cf-115">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="c97cf-116">Die gleichzeitigen Benutzer sind die Grundlage für die weiteren Zahlenangaben in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-116">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-117">Active Directory-Änderungen</span><span class="sxs-lookup"><span data-stu-id="c97cf-117">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="c97cf-118">Es wird davon ausgegangen, dass 0,5% der Gesamtbenutzer in Active Directory jede Woche für lync erstellt und aktiviert werden und dass 0,5% der Gesamtbenutzer pro Woche von Active Directory und von lync deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c97cf-118">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="c97cf-119">Für 5 % der Benutzer wird jede Woche mindestens ein Active Directory-Attribut geändert.</span><span class="sxs-lookup"><span data-stu-id="c97cf-119">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-120">Active Directory-Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="c97cf-120">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p103">Es wird davon ausgegangen, dass die Anzahl der Active Directory-Verteilergruppen in der Organisation dreimal die Anzahl aller Benutzer in Active Directory ist. Die Verteilergruppen haben folgende Größe:</span><span class="sxs-lookup"><span data-stu-id="c97cf-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="c97cf-123">64 % umfassen 2-30 Benutzer</span><span class="sxs-lookup"><span data-stu-id="c97cf-123">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="c97cf-124">13 % umfassen 31-50 Benutzer</span><span class="sxs-lookup"><span data-stu-id="c97cf-124">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="c97cf-125">10 % umfassen 51-100 Benutzer</span><span class="sxs-lookup"><span data-stu-id="c97cf-125">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="c97cf-126">13 % umfassen 101-500 Benutzer</span><span class="sxs-lookup"><span data-stu-id="c97cf-126">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-127">VoIP-Benutzer (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="c97cf-127">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="c97cf-128">60% der lync Server Benutzer sind für Unified Communications (UC) aktiviert (das heißt, die Telefonnummern befinden sich im Besitz von lync Server).</span><span class="sxs-lookup"><span data-stu-id="c97cf-128">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-129">Verteilung registrierter Clients</span><span class="sxs-lookup"><span data-stu-id="c97cf-129">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-130">65% der Clients führen lync 2013 Software aus, einschließlich lync und lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c97cf-130">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="c97cf-131">30% der Clients mit Client Software aus einer früheren Version von lync.</span><span class="sxs-lookup"><span data-stu-id="c97cf-131">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="c97cf-132">5% der Clients verwenden lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c97cf-132">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="c97cf-133">Wenn die Mobilität aktiviert ist, wird davon ausgegangen, dass 40% der Benutzer die Mobilität gleichzeitig mit den anderen zuvor zitierten registrierten Clientoptionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-133">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="c97cf-134">In diesem Fall beträgt das mpop-Verhältnis (Multiple Points of Presence) des Clients 1:1.9.</span><span class="sxs-lookup"><span data-stu-id="c97cf-134">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="c97cf-135">Wenn Mobility deaktiviert ist, beträgt das mpop-Verhältnis 1:1.5.</span><span class="sxs-lookup"><span data-stu-id="c97cf-135">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-136">Verteilung von Remotebenutzern</span><span class="sxs-lookup"><span data-stu-id="c97cf-136">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-137">70 % der Benutzer verbinden sich intern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-137">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="c97cf-138">30 % der Benutzer stellen über einen Edgeserver und einen Director eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="c97cf-138">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-139">Verteilung von Kontakten</span><span class="sxs-lookup"><span data-stu-id="c97cf-139">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p105">Die maximale Anzahl von Kontakten eines Benutzers beträgt 1.000. Weniger als 1 % der Benutzer verfügen über 1.000 Kontakte. Weniger als 25 % der Benutzer verfügen über 100 Kontakte oder mehr.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="c97cf-p106">Benutzer, die mit einem öffentlichen Netz verbunden sind, verfügen über durchschnittlich 80 Kontakte. Für diese Benutzer gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c97cf-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c97cf-p107">50 % der Kontakte befinden sich innerhalb der Organisation. 10 % dieser Benutzer sind Remotebenutzer, die sich von außerhalb der Firewall verbinden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-147">40 % der Kontakte sind Benutzer einer öffentlichen Cloud (z. B. Benutzer von AOL, Yahoo! oder Google Talk).</span><span class="sxs-lookup"><span data-stu-id="c97cf-147">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="c97cf-148">10 % der Kontakte sind Benutzer von Verbundpartnern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-148">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c97cf-149">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c97cf-149">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c97cf-150">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c97cf-150">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c97cf-151">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="c97cf-151">Messenger until the service shut down date.</span></span> <span data-ttu-id="c97cf-152">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c97cf-152">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c97cf-153">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-153">has been announced.</span></span> <span data-ttu-id="c97cf-154">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c97cf-154">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c97cf-155">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c97cf-155">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c97cf-156">Messenger.</span><span class="sxs-lookup"><span data-stu-id="c97cf-156">Messenger.</span></span> <span data-ttu-id="c97cf-157">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-157">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="c97cf-158">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-158">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c97cf-159">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c97cf-159">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c97cf-160">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="c97cf-160">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="c97cf-p111">Benutzer ohne Verbindung mit einem öffentlichen Netz verfügen über durchschnittlich 50 Kontakte. Für diese Benutzer gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c97cf-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c97cf-p112">80 % der Kontakte befinden sich innerhalb der Organisation. 10 % dieser Benutzer sind Remotebenutzer, die sich von außerhalb der Firewall verbinden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-165">20 % der Kontakte sind Benutzer von Verbundpartnern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-165">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="c97cf-p113">Jeder Benutzer weist 1 Verteilergruppe in seiner Kontaktliste auf. Für Leistungstest wird davon ausgegangen, dass Verteilergruppen immer erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="c97cf-168">25 % der Kontakte eines Benutzers verwenden XMPP.</span><span class="sxs-lookup"><span data-stu-id="c97cf-168">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-169">Sitzungszeit</span><span class="sxs-lookup"><span data-stu-id="c97cf-169">Session time</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p114">Eine durchschnittliche Benutzeranmeldesitzung dauert 12 Stunden. Sämtliche Benutzer melden sich innerhalb von 120 Minuten nach dem Sitzungsstart an.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="c97cf-172">Benutzermodell für Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="c97cf-172">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-173">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-173">Category</span></span></th>
<th><span data-ttu-id="c97cf-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-175">Peer-zu-Peer-Chatsitzungen</span><span class="sxs-lookup"><span data-stu-id="c97cf-175">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="c97cf-176">Jeder Benutzer verfügt über durchschnittlich sechs Peer-zu-Peer-Chatsitzungen pro Tag.</span><span class="sxs-lookup"><span data-stu-id="c97cf-176">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="c97cf-177">10 Chatnachrichten pro Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c97cf-177">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="c97cf-178">Jede Nachricht wird durch zwei SIP-Info-Nachrichten und 2 SIP 200 OK-Nachrichten (für die Status anzeigen wie " &lt; Name &gt; is Typing") abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-178">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-179">Abfrage von Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="c97cf-179">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p115">Insgesamt wird von durchschnittlich 60 Abfragen von Anwesenheitsinformationen pro Benutzer und Stunde ausgegangen. Für jeden Benutzer wird von folgenden Durchschnittswerten ausgegangen:</span><span class="sxs-lookup"><span data-stu-id="c97cf-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="c97cf-p116">Eine Abfrage pro Tag für die Anwesenheitsinformationen von Benutzern auf der Registerkarte Organisation (nicht jedoch von Benutzern in der Kontaktliste) des Benutzers. Die durchschnittliche Anzahl von Benutzern auf der Registerkarte Organisation eines Benutzers, bei denen es sich nicht um Kontakte handelt, beträgt 15 Benutzer. Zwei Anzeigevorgänge für Visitenkarten pro Tag.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-185">Eine Abfrage von Anwesenheitsinformationen, sobald der Benutzer einen anderen Benutzer anklickt, um eine Unterhaltung zu beginnen (diese Aktion erfolgt schätzungsweise einmal pro Stunde).</span><span class="sxs-lookup"><span data-stu-id="c97cf-185">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-p117">Sechs Suchvorgänge für Benutzer pro Stunde. Jedes Mal, wenn eine Suche ausgeführt wird, wird eine Stapelabfrage an alle Benutzer in der Suchergebnisliste gesendet. Es wird von einer durchschnittlichen Größe von 20 Suchergebnissen ausgegangen. Falls die Suchergebnisse weiterhin auf dem Bildschirm angezeigt werden, wird die Stapelabfrage alle 5 Minuten aktualisiert. Es wird von zwei derartigen Aktualisierungen pro Stunde ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-190">Wenn der Benutzer eine E-Mail in Outlook öffnet bzw. eine Vorschau anzeigt, werden die Anwesenheitsinformationen für die Benutzer in den Feldern An: und CC: der E-Mail abgefragt (dieser Vorgang erfolgt schätzungsweise bei fünf E-Mails pro Stunde und für vier Benutzer pro E-Mail).</span><span class="sxs-lookup"><span data-stu-id="c97cf-190">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-191">Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="c97cf-191">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p118">Wenn ein Benutzer einen anderen Benutzer als Kontakt hinzufügt, <em>abonniert</em> der erste Benutzer fünf Kategorien von Informationen zum zweiten Benutzer. Aktualisierungen dieser Informationskategorien werden automatisch an den ersten Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="c97cf-194">Für jeden Client wird eine einzige Stapelabonnementanforderung gesendet, um den Anwesenheitsstatus von durchschnittlich 40 Kontakten abzurufen, mit zusätzlich 40 Dialogen zum Abrufen von Anwesenheitsinformationen für Partnerkontakte.</span><span class="sxs-lookup"><span data-stu-id="c97cf-194">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="c97cf-195">Die Anwesenheitsinformationen für Mitglieder einer erweiterten Verteilergruppe werden über beständige Anwesenheitsabonnements ermittelt, nicht über Abrufe, und werden als 1 Erweiterung pro Benutzer für jeweils 2 Stunden modelliert.</span><span class="sxs-lookup"><span data-stu-id="c97cf-195">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="c97cf-p119"><em>Kurze Abonnements</em> werden verwendet, wenn sich ein Benutzer anmeldet, wenn ein Stapelabonnement für alle Kontakte des Benutzers vorhanden ist und wenn sich der Benutzer bald abmeldet. Es wird von 6 kurzen Abonnements pro Benutzer und Stunde ausgegangen, wobei jedes Abonnement 10 Minuten dauert.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-198">Veröffentlichung der Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="c97cf-198">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="c97cf-199">Der Anwesenheitsstatus wird durchschnittlich viermal pro Benutzer und Stunde veröffentlicht, mit einer maximalen Anzahl von 6 Veröffentlichungen pro Benutzer und Stunde.</span><span class="sxs-lookup"><span data-stu-id="c97cf-199">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-200">Größe des Anwesenheitsdokuments</span><span class="sxs-lookup"><span data-stu-id="c97cf-200">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="c97cf-201">Bei einem vollständigen Anwesenheitsdokument wird von einer durchschnittlichen Größe von 4 KB ausgegangen, mit einer maximalen Größe von 25 KB.</span><span class="sxs-lookup"><span data-stu-id="c97cf-201">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c97cf-202">In der folgenden Tabelle wird das Benutzermodell für die Adressbuchverwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c97cf-202">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="c97cf-203">Benutzermodell für die Adressbuchverwendung</span><span class="sxs-lookup"><span data-stu-id="c97cf-203">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-204">Adressbuchsuchmodus</span><span class="sxs-lookup"><span data-stu-id="c97cf-204">Address Book search mode</span></span></th>
<th><span data-ttu-id="c97cf-205">Verwendung</span><span class="sxs-lookup"><span data-stu-id="c97cf-205">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-206">Nur Adressbuchwebabfrage (alle Abfragen werden vom Adressbuch-Webabfragedienst ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="c97cf-206">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="c97cf-207">Vier Präfixabfragen pro Benutzer und Tag.</span><span class="sxs-lookup"><span data-stu-id="c97cf-207">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="c97cf-p120">60 exakte Suchabfragen pro Benutzer und Tag. 40 % dieser Abfragen werden als Batchabfragen ausgeführt, mit durchschnittlich 20 Kontakten pro Abfrage. Die übrigen 60 % der Abfragen werden für einen einzelnen Kontakt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="c97cf-p121">25 Fotoabfragen pro Benutzer und Tag. 24 Abfragen für ein einzelnes Foto, die verbleibende Abfrage wird als Batchabfrage mit durchschnittlich 20 Kontakten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="c97cf-213">Eine Suchabfrage für die gesamte Organisation pro Benutzer und Tag.</span><span class="sxs-lookup"><span data-stu-id="c97cf-213">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-p122">Im gemischten Modus werden sowohl die Adressbuchdatei als auch Webabfragen verwendet. Dies ist der Standardmodus.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="c97cf-216">Nur zwei Abfragetypen werden über das Netzwerk ausgeführt, die Suchabfragen für Fotos und für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="c97cf-216">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="c97cf-p123">25 Fotoabfragen pro Benutzer und Tag. 24 Abfragen für ein einzelnes Foto, die verbleibende Abfrage wird als Batchabfrage mit durchschnittlich 20 Kontakten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="c97cf-219">Eine Suchabfrage für die gesamte Organisation pro Benutzer und Tag.</span><span class="sxs-lookup"><span data-stu-id="c97cf-219">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c97cf-220">In der folgenden Tabelle ist das Konferenzmodell beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c97cf-220">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="c97cf-221">Konferenzmodell</span><span class="sxs-lookup"><span data-stu-id="c97cf-221">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-222">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-222">Category</span></span></th>
<th><span data-ttu-id="c97cf-223">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-224">Geplante Besprechungen im Vergleich zu &quot; sofort &quot; Besprechungen</span><span class="sxs-lookup"><span data-stu-id="c97cf-224">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="c97cf-225">60 % geplant, 40 % ungeplant.</span><span class="sxs-lookup"><span data-stu-id="c97cf-225">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="c97cf-226">Bei den geplanten Besprechungen wird von 80 % zugewiesenen Konferenzen ausgegangen, wobei es sich um Instanzen von wiederkehrenden Konferenzen handelt. 10 % sind einmalige offene Besprechungen, 8% sind einmalige anonyme Besprechungen, und 2 % sind einmalige geschlossene Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-226">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-227">Verteilung von Konferenzclients</span><span class="sxs-lookup"><span data-stu-id="c97cf-227">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-228">Für geplante Besprechungen:</span><span class="sxs-lookup"><span data-stu-id="c97cf-228">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="c97cf-229">65% der Konferenzbenutzer verwenden lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c97cf-229">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-230">5% der Konferenzbenutzer verwenden Microsoft lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c97cf-230">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-231">30% der Konferenzbenutzer verwenden frühere Clients, einschließlich Microsoft lync 2010, Office Communicator 2007 R2, Office Communicator 2007 und Microsoft Office Communicator Web Access (Version 2007).</span><span class="sxs-lookup"><span data-stu-id="c97cf-231">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="c97cf-232">Für ungeplante Besprechungen:</span><span class="sxs-lookup"><span data-stu-id="c97cf-232">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="c97cf-233">70% der Konferenzbenutzer verwenden lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c97cf-233">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-234">30% der Konferenzbenutzer verwenden frühere Clients, einschließlich Microsoft lync 2010, Office Communicator 2007 R2, Office Communicator 2007 und Microsoft Office Communicator Web Access (Version 2007).</span><span class="sxs-lookup"><span data-stu-id="c97cf-234">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-235">Gleichzeitigkeit von Besprechungen</span><span class="sxs-lookup"><span data-stu-id="c97cf-235">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p124">5 % der Benutzer befinden sich während der Arbeitszeiten in Konferenzen. Bei einem Pool mit 80.000 Benutzern können sich daher bis zu 4.000 Benutzer gleichzeitig in Konferenzen befinden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-238">Verteilung der Audiofunktion in Besprechungen</span><span class="sxs-lookup"><span data-stu-id="c97cf-238">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-239">40 % Kombination aus VoIP-Audio- und Einwahlkonferenzen, mit einem Verhältnis von 3:1 von VoIP-Benutzern zu Einwahlbenutzern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-239">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="c97cf-240">35 % nur VoIP-Audio.</span><span class="sxs-lookup"><span data-stu-id="c97cf-240">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="c97cf-241">15 % nur Audio bei Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-241">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="c97cf-242">10 % ohne Audio (reine Chatkonferenzen mit durchschnittlich fünf gesendeten Nachrichten pro Benutzer).</span><span class="sxs-lookup"><span data-stu-id="c97cf-242">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-243">Medienmix für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="c97cf-243">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="c97cf-244">Bei 75 % der Konferenzen handelt es sich um Webkonferenzen mit Audio sowie einigen anderen Methoden für die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="c97cf-244">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="c97cf-245">Für diesen Konferenzen werden die folgenden weiteren Methoden für die Zusammenarbeit genutzt:</span><span class="sxs-lookup"><span data-stu-id="c97cf-245">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c97cf-246">Die Summe dieser Zahlen beträgt mehr als 100 %, da in einer Konferenz mehrere Methoden zur Zusammenarbeit verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c97cf-246">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="c97cf-p125">50 % nutzen zusätzlich die Anwendungsfreigabe. Es wird davon ausgegangen, dass ein Benutzer Daten mit maximal 1,1 MB pro Sekunde sendet.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-249">50 % nutzen zusätzlich Chatdienste (mit durchschnittlich zwei Chatnachrichten pro Benutzer).</span><span class="sxs-lookup"><span data-stu-id="c97cf-249">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="c97cf-p126">20 % nutzen zusätzlich die Datenzusammenarbeit, einschließlich PowerPoint oder Whiteboard. Dabei werden pro Konferenz durchschnittlich zwei PowerPoint-Dateien mit einer durchschnittlichen Größe von 10 MB (ohne eingebettetes Video) oder 30 MB (mit eingebettetem Video) präsentiert. Durchschnittlich 20 Anmerkungen pro Whiteboard.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-p127">20 % nutzen zusätzlich die Videofunktion. 70 % dieser Benutzer nehmen an Konferenzen teil, für die Mehrfachansicht-Video aktiviert ist, wobei jeder Benutzer 2 bis 3 Videostreams empfängt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="c97cf-254">15 % fügen freigegebene Notizen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c97cf-254">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-255">Verteilung der Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c97cf-255">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-256">50 % interne, authentifizierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c97cf-256">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="c97cf-257">25 % authentifizierte Benutzer mit Remotezugriff.</span><span class="sxs-lookup"><span data-stu-id="c97cf-257">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="c97cf-258">15 % anonyme Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c97cf-258">15% anonymous users.</span></span></p>
<p><span data-ttu-id="c97cf-259">10 % Partnerbenutzer.</span><span class="sxs-lookup"><span data-stu-id="c97cf-259">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-260">Verteilung für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="c97cf-260">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="c97cf-261">Für die Benutzer wird simuliert, dass sie der Besprechung innerhalb der ersten 5 Minuten beitreten.</span><span class="sxs-lookup"><span data-stu-id="c97cf-261">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c97cf-262">In regulären Front-End-Pools hat lync Server 2013 eine maximal unterstützte Besprechungsgröße von 250 Benutzern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-262">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="c97cf-263">Jeder Pool kann zu einem bestimmten Zeitpunkt eine Besprechung mit 250 Benutzern hosten.</span><span class="sxs-lookup"><span data-stu-id="c97cf-263">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="c97cf-264">Während eine Besprechung dieser Größe stattfindet, kann der Pool zusätzlich weitere kleinere Konferenzen hosten.</span><span class="sxs-lookup"><span data-stu-id="c97cf-264">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="c97cf-265">Darüber hinaus können Sie Besprechungen mit bis zu 1000 Benutzern unterstützen, indem Sie einen Pool speziell zum Hosten dieser Besprechungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="c97cf-265">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="c97cf-266">Ausführliche Informationen finden Sie unter [Support für umfangreiche Besprechungen in lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="c97cf-266">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="c97cf-267">Konferenzen wurden wie folgt simuliert:</span><span class="sxs-lookup"><span data-stu-id="c97cf-267">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="c97cf-268">85 % der Konferenzen wiesen vier Teilnehmer auf.</span><span class="sxs-lookup"><span data-stu-id="c97cf-268">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="c97cf-269">10 % der Konferenzen wiesen sechs Teilnehmer auf.</span><span class="sxs-lookup"><span data-stu-id="c97cf-269">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="c97cf-270">5 % der Konferenzen wiesen elf Teilnehmer auf.</span><span class="sxs-lookup"><span data-stu-id="c97cf-270">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="c97cf-271">Eine große Konferenz mit 250 Benutzern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-271">One large conference of 250 users.</span></span>

<span data-ttu-id="c97cf-272">Die folgende Tabelle enthält ausführliche Informationen zum Benutzermodell für Konferenzen mit Einwahlbenutzern.</span><span class="sxs-lookup"><span data-stu-id="c97cf-272">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="c97cf-273">Benutzermodell für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="c97cf-273">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-274">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-274">Category</span></span></th>
<th><span data-ttu-id="c97cf-275">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-276">Authentifiziert/anonym</span><span class="sxs-lookup"><span data-stu-id="c97cf-276">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p129">70 % der Anrufer treten anonym bei und werden zur Aufzeichnung ihres Namens aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-279">Anrufdauer und Wartemusik</span><span class="sxs-lookup"><span data-stu-id="c97cf-279">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="c97cf-280">Durchschnittliche Anrufdauer ohne Wartemusik: 50 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c97cf-280">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="c97cf-281">Für 50 % der Einwahlbenutzer wird Wartemusik wiedergegeben (durchschnittlich 5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="c97cf-281">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-282">DTMF (Dual-Tone Multifrequency, Mehrfrequenzverfahren)</span><span class="sxs-lookup"><span data-stu-id="c97cf-282">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p130">15 % der Konferenzen, auf die ausschließlich per Einwahl zugegriffen wird, werden per Telefon geleitet. 10 % der gemischten Konferenzen, an denen Einwahlbenutzer teilnehmen, werden ebenfalls per Telefon geleitet.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="c97cf-285">20 % der Konferenzleiter (per Telefon) nutzen 2 DTMF-Befehle pro Konferenz.</span><span class="sxs-lookup"><span data-stu-id="c97cf-285">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-286">Sprache von Ansagen</span><span class="sxs-lookup"><span data-stu-id="c97cf-286">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="c97cf-287">Bei Simulationen wird Englisch als Ansagensprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="c97cf-287">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c97cf-288">Die folgende Tabelle enthält ausführliche Informationen zum Benutzermodell für die Konferenzlobby.</span><span class="sxs-lookup"><span data-stu-id="c97cf-288">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="c97cf-289">Benutzermodell für die Konferenzlobby</span><span class="sxs-lookup"><span data-stu-id="c97cf-289">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-290">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-290">Category</span></span></th>
<th><span data-ttu-id="c97cf-291">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-291">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-292">Anzahl von Benutzern in der Lobby</span><span class="sxs-lookup"><span data-stu-id="c97cf-292">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="c97cf-293">5 % der Einwahlbenutzer betreten zunächst die Lobby, 25 % der anderen Benutzer werden zunächst in die Lobby weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c97cf-293">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-294">Zulassen von Benutzern aus der Lobby</span><span class="sxs-lookup"><span data-stu-id="c97cf-294">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="c97cf-295">Bei Simulationen wurden alle Benutzer vom Referenten zugelassen, bevor ein Clienttimeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-295">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c97cf-296">In der folgenden Tabelle ist das Benutzermodell für andere Peer-zu-Peer-Sitzungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c97cf-296">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="c97cf-297">Benutzermodell für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="c97cf-297">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-298">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-298">Category</span></span></th>
<th><span data-ttu-id="c97cf-299">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-299">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-300">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="c97cf-300">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c97cf-301">Jeder Benutzer nimmt an fünf Peer-zu-Peer-Anwendungsfreigabesitzungen pro Monat teil (durchschnittlich 0,25 Sitzungen pro Tag).</span><span class="sxs-lookup"><span data-stu-id="c97cf-301">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-302">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="c97cf-302">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c97cf-p131">Jeder Benutzer nimmt (im Rahmen einer Chatsitzung) an einer Peer-zu-Peer-Dateiübertragungssitzung pro Monat teil (durchschnittlich 0,05 Sitzungen pro Tag). Die durchschnittliche Größe der in einer Sitzung übertragenen Dateien beträgt 1 MB.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c97cf-305">In der folgenden Tabelle wird das Benutzermodell für Richtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c97cf-305">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="c97cf-306">Benutzermodell für Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c97cf-306">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97cf-307">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c97cf-307">Category</span></span></th>
<th><span data-ttu-id="c97cf-308">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97cf-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97cf-309">Konferenz-, Anwesenheits- und Archivierungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c97cf-309">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="c97cf-310">Es wird von einer globalen Richtlinie, zehn Konferenzrichtlinien, vier Archivierungsrichtlinien und zehn Anwesenheitsrichtlinien ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-310">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97cf-311">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c97cf-311">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="c97cf-312">Es wird von einer globalen Richtlinie und zwei Richtlinien pro Standort ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-312">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="c97cf-313">100 % der Standorte verfügen über eine Standortrichtlinie, und 30 % der Benutzer ist eine benutzerbasierte Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-313">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="c97cf-314">Pro Standort wird von einem Wählplan und zwei Routen ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="c97cf-314">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="c97cf-315">Spitzenzeiten</span><span class="sxs-lookup"><span data-stu-id="c97cf-315">Busy Hour</span></span>

<span data-ttu-id="c97cf-p133">Die Spitzenauslastung für Peer-zu-Peer-Sitzungen wird basierend auf der Anzahl von Anrufversuchen (Busy Hour Call Attempts, BHCA) zu Spitzenzeiten berechnet. Für diesen Begriff aus der VoIP-Branche wird davon ausgegangen, dass 50 % aller Anrufe an einem Tag innerhalb von 20 % der Gesamtzeit getätigt werden. Der BHCA-Wert wird mithilfe der folgenden Formel berechnet:</span><span class="sxs-lookup"><span data-stu-id="c97cf-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="c97cf-319">Zur Simulation von Spitzenzeiten wurden in Leistungstests VoIP- und andere Peer-zu-Peer-Sitzungen bei einer Spitzenauslastung mit einer Dauer von mindestens 1,6 Stunden pro Tag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c97cf-319">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="c97cf-p134">Für die Spitzenauslastung bei Konferenzen wird davon ausgegangen, dass 75 % aller Konferenzen an einem achtstündigen Arbeitstag innerhalb von vier Stunden zu Spitzenzeiten stattfinden. Für diese Spitzenzeiten wird das 1,5-Fache der durchschnittlichen Konferenzauslastung verzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="c97cf-322">Enterprise-VoIP-Anrufe</span><span class="sxs-lookup"><span data-stu-id="c97cf-322">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="c97cf-323">Für Enterprise-VoIP-Anrufe gelten die folgenden Annahmen:</span><span class="sxs-lookup"><span data-stu-id="c97cf-323">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="c97cf-324">50% der Benutzer sind für Enterprise-VoIP aktiviert, und 60% dieser Benutzer sind für PSTN-Anrufe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c97cf-324">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="c97cf-p135">Jeder dieser Benutzer, für den PSTN-Anrufe aktiviert sind, tätigt 4 PSTN-Anrufe in Spitzenzeiten. Jeder Anruf dauert 3 Minuten.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="c97cf-327">65 % dieser PST-VoIP-Anrufe verwenden die Medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="c97cf-327">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="c97cf-328">Mobilität</span><span class="sxs-lookup"><span data-stu-id="c97cf-328">Mobility</span></span>

<span data-ttu-id="c97cf-p136">Es wird davon ausgegangen, dass für 40 % der registrierten Benutzer die Mobilität aktiviert ist. Für jeden Benutzer mit aktivierter Mobilität wird davon ausgegangen, dass sich die Aktivität des mobilen Clients zur Aktivität der anderen MPOP-Instanzen für diesen Benutzer summiert. Mit Ausnahme von Konferenzinteraktionen, für die der Mobilitätsclient einfach ein weiterer Clienttyp ist, der für die Teilnahme an Konferenzen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="c97cf-331">Beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="c97cf-331">Persistent Chat</span></span>

<span data-ttu-id="c97cf-332">Es wird davon ausgegangen, dass 25 % der registrierten Benutzer an Sitzungen für beständigen Chat beteiligt sind, wobei Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="c97cf-332">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="c97cf-333">Durchschnittlich 1,5 Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="c97cf-333">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="c97cf-334">Jeder Chatroom führt zu 12 Abrufanforderungen pro Stunde, mit einem Zielwert von durchschnittlich je 10 Benutzern</span><span class="sxs-lookup"><span data-stu-id="c97cf-334">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="c97cf-335">Reaktionsgruppe und Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="c97cf-335">Response Group and Call Park</span></span>

<span data-ttu-id="c97cf-p137">Es wird davon ausgegangen, dass 0,15 % der registrierten Benutzer Reaktionsgruppen angehören. Außerdem wird davon ausgegangen, dass 0,02 % der registrierten Benutzer zu einem bestimmten Zeitpunkt Anrufe parken.</span><span class="sxs-lookup"><span data-stu-id="c97cf-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

