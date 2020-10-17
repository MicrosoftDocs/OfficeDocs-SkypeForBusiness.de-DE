---
title: Lync Server 2013 Benutzererfahrung beim Pool Ausfall
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2d6733f2db3a988f604554df55a25f866f5099
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530192"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="778ee-102">Benutzererfahrung beim Pool Fehler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ee-102">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="778ee-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="778ee-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="778ee-104">Wenn für einen Pool ein Failover vorgenommen wurde, werden alle Benutzer des betroffenen Pools gezwungen, sich abzumelden und sich beim Sicherungspool anzumelden.</span><span class="sxs-lookup"><span data-stu-id="778ee-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="778ee-105">Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="778ee-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="778ee-106">Im Ausfall Sicherheitsmodus können Benutzer keine Aufgaben ausführen, die eine beständige Änderung auf lync Server verursachen würden, beispielsweise das Hinzufügen eines Kontakts.</span><span class="sxs-lookup"><span data-stu-id="778ee-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="778ee-107">Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.</span><span class="sxs-lookup"><span data-stu-id="778ee-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="778ee-108">Sämtliche Sitzungen, über die ein Benutzer verfügt, während ein Pool ausfällt, werden unterbrochen, und der Benutzer muss diese Sitzungen wiederherstellen, um nach dem Failover fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="778ee-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="778ee-p102">Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Home-Pool wiederhergestellt wird, kann der Administrator über ein Failback diese Benutzer wieder über ihren ursprünglichen Home-Pool verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="778ee-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="778ee-112">Hinweis in lync 2013 wird die Datenbank des Standort Informationsservers nicht in den Sicherungspool repliziert.</span><span class="sxs-lookup"><span data-stu-id="778ee-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="778ee-113">Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="778ee-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="778ee-114">Benutzerfreundlichkeit während des Failovers</span><span class="sxs-lookup"><span data-stu-id="778ee-114">User Experience During Failover</span></span>

<span data-ttu-id="778ee-p104">Befindet sich ein Benutzer in einem ausfallenden Pool, wird der Benutzer abgemeldet. Sämtliche Peer-zu-Peer-Sitzungen, an denen der Benutzer teilgenommen hat, werden abgebrochen, wie auch die von diesem Benutzer organisierten Konferenzen. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Nur dann sind Benutzer in der Lage, neue Sitzungen zu erstellen oder vorherige Sitzungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="778ee-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="778ee-120">Benutzerfreundlichkeit während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="778ee-120">User Experience During Failback</span></span>

<span data-ttu-id="778ee-p105">Pool-Failbacks können auftreten, während der betroffene Benutzer an einem Sicherungspool angemeldet ist und der Benutzer während des Failbacks weiterhin angemeldet ist und arbeitet. Hinweis: Es dauert mehrere Minuten, bis der Failback-Prozess abgeschlossen ist.  Zur Orientierung: Erwartungsgemäß dauert ein Pool mit 20.000 Benutzern bis zu 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="778ee-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="778ee-124">Die folgenden Tabellen zeigen ausführlichere Informationen darüber, wie ein Benutzer mit einem lync 2013-Client oder einem Microsoft lync 2010-Client während und nach dem Failback betroffen ist und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit diesem interagieren, der zurückgeschlagen wird.</span><span class="sxs-lookup"><span data-stu-id="778ee-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="778ee-125">Benutzer mit Microsoft Office Communicator 2007 R2 Clients können sich erst anmelden, wenn der Front-End-Pool vollständig zurückgetreten ist.)</span><span class="sxs-lookup"><span data-stu-id="778ee-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="778ee-p107">Der Begriff *betroffener Benutzer* bezieht sich auf sämtliche Benutzer, bei denen beim Home-Pool ein Failover auftrat und die daher vom Sicherungspool verarbeitet werden. Definitionsgemäß sind sämtliche Benutzer, die ursprünglich auf dem Sicherungspool verwaltet wurden, keine betroffenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="778ee-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="778ee-128">Benutzerfreundlichkeit für einen betroffenen Benutzer für einen in einem Failback befindlichen Pool</span><span class="sxs-lookup"><span data-stu-id="778ee-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="778ee-129">Benutzerstatus oder -aufgabe</span><span class="sxs-lookup"><span data-stu-id="778ee-129">User state or task</span></span></th>
<th><span data-ttu-id="778ee-130">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="778ee-130">During failback</span></span></th>
<th><span data-ttu-id="778ee-131">Nach abgeschlossenem Failback</span><span class="sxs-lookup"><span data-stu-id="778ee-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="778ee-132">Benutzerstatus des bereits angemeldeten Benutzers</span><span class="sxs-lookup"><span data-stu-id="778ee-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="778ee-p108">Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="778ee-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="778ee-135">Benutzer bleibt angemeldet und wechselt in den regulären Modus.</span><span class="sxs-lookup"><span data-stu-id="778ee-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ee-136">Neuer Benutzer meldet sich an</span><span class="sxs-lookup"><span data-stu-id="778ee-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="778ee-137">Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.</span><span class="sxs-lookup"><span data-stu-id="778ee-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="778ee-138">Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.</span><span class="sxs-lookup"><span data-stu-id="778ee-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778ee-139">Vom betroffenen Benutzer organisierte laufende Konferenz</span><span class="sxs-lookup"><span data-stu-id="778ee-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="778ee-p109">Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="778ee-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="778ee-p110">Alle Modalitäten funktionieren jetzt. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="778ee-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ee-144">Vom nicht betroffenen Benutzer organisierte laufende Konferenz</span><span class="sxs-lookup"><span data-stu-id="778ee-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="778ee-p111">Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist darauf beschränkt, was er im Ausfallsicherheitsmodus ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="778ee-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="778ee-147">Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="778ee-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778ee-148">Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="778ee-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="778ee-149">Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="778ee-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="778ee-150">Für alle Modalitäten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="778ee-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ee-151">Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird</span><span class="sxs-lookup"><span data-stu-id="778ee-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="778ee-152">Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="778ee-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="778ee-153">Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus, und Anwesenheitsänderungen werden nun reflektiert.</span><span class="sxs-lookup"><span data-stu-id="778ee-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778ee-154">Verfügbarkeit von Kontaktlisten und Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="778ee-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="778ee-155">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="778ee-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="778ee-156">Available</span><span class="sxs-lookup"><span data-stu-id="778ee-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ee-157">Alle Peer-zu-Peer-Sitzungen und -modalitäten</span><span class="sxs-lookup"><span data-stu-id="778ee-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="778ee-158">Available</span><span class="sxs-lookup"><span data-stu-id="778ee-158">Available</span></span></p></td>
<td><p><span data-ttu-id="778ee-159">Available</span><span class="sxs-lookup"><span data-stu-id="778ee-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="778ee-160">Benutzerfreundlichkeit für einen in einem nicht betroffenen Pool verwalteten Benutzer während eines Failbacks eines anderen Pools</span><span class="sxs-lookup"><span data-stu-id="778ee-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="778ee-161">Benutzeraufgabe</span><span class="sxs-lookup"><span data-stu-id="778ee-161">User task</span></span></th>
<th><span data-ttu-id="778ee-162">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="778ee-162">During failback</span></span></th>
<th><span data-ttu-id="778ee-163">Nach abgeschlossenem Failback</span><span class="sxs-lookup"><span data-stu-id="778ee-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="778ee-164">Anwesenheitsinformationen des betroffenen Benutzers anzeigen</span><span class="sxs-lookup"><span data-stu-id="778ee-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="778ee-165">Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.</span><span class="sxs-lookup"><span data-stu-id="778ee-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="778ee-p112">In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="778ee-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ee-168">Von betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="778ee-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="778ee-169">Alle Modalitäten der Konferenz werden abgebrochen</span><span class="sxs-lookup"><span data-stu-id="778ee-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="778ee-p113">Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="778ee-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="778ee-172">Von nicht betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="778ee-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="778ee-173">Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="778ee-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="778ee-174">Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="778ee-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ee-175">Alle Peer-zu-Peer-Sitzungen und -modalitäten</span><span class="sxs-lookup"><span data-stu-id="778ee-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="778ee-176">Available</span><span class="sxs-lookup"><span data-stu-id="778ee-176">Available</span></span></p></td>
<td><p><span data-ttu-id="778ee-177">Available</span><span class="sxs-lookup"><span data-stu-id="778ee-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

