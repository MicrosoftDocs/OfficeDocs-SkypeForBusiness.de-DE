---
title: Lync Server 2013-Benutzererfahrung beim Pool Fehler
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca33dc8f77ac697b7eea9cc89fee9aa401318566
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="9249e-102">Benutzererfahrung beim Pool Fehler in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9249e-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9249e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9249e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9249e-104">Wenn ein Pool fehlerhaft ist, müssen sich alle Benutzer des betroffenen Pools abmelden und sich dann beim Sicherungspool anmelden.</span><span class="sxs-lookup"><span data-stu-id="9249e-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="9249e-105">Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="9249e-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="9249e-106">Im Resilienz-Modus können Benutzer keine Aufgaben ausführen, die zu einer dauerhaften Änderung auf lync Server führen, wie etwa das Hinzufügen eines Kontakts.</span><span class="sxs-lookup"><span data-stu-id="9249e-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="9249e-107">Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.</span><span class="sxs-lookup"><span data-stu-id="9249e-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="9249e-108">Alle Sitzungen, die ein Benutzer hat, wenn der Pool ausfällt, werden gestört, und der Benutzer muss diese Sitzungen nach einem Failover erneut einrichten, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="9249e-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="9249e-109">Benutzer werden während eines Failovers oder Failbacks nicht verlagert.</span><span class="sxs-lookup"><span data-stu-id="9249e-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="9249e-110">Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9249e-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="9249e-111">Wenn der Home-Pool wiederhergestellt wird, kann der Administrator diese Benutzer zurückschlagen, um von Ihrem ursprünglichen privaten Pool gewartet zu werden.</span><span class="sxs-lookup"><span data-stu-id="9249e-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="9249e-112">Hinweis in lync 2013 wird die Standort Informations Server-Datenbank nicht in den Sicherungspool repliziert.</span><span class="sxs-lookup"><span data-stu-id="9249e-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="9249e-113">Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="9249e-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="9249e-114">Benutzerfreundlichkeit während eines Failovers</span><span class="sxs-lookup"><span data-stu-id="9249e-114">User Experience During Failover</span></span>

<span data-ttu-id="9249e-115">Wenn sich ein Benutzer in einem Pool befindet, der fehlschlägt, wird der Benutzer abgemeldet. Jede Peer-to-Peer-Sitzung, an der der Benutzer teilgenommen hat, wird beendet, ebenso wie Konferenzen, die von diesem Benutzer organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9249e-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="9249e-116">Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="9249e-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="9249e-117">Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet.</span><span class="sxs-lookup"><span data-stu-id="9249e-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="9249e-118">Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9249e-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="9249e-119">Nur dann kann der Benutzer neue Sitzungen einrichten oder frühere Sitzungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="9249e-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="9249e-120">Benutzerfreundlichkeit während des Failback</span><span class="sxs-lookup"><span data-stu-id="9249e-120">User Experience During Failback</span></span>

<span data-ttu-id="9249e-121">Pool-Failbacks können auftreten, wenn der betroffene Benutzer während des Failbacks weiterhin an einem Sicherungspool angemeldet ist und arbeitet.</span><span class="sxs-lookup"><span data-stu-id="9249e-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="9249e-122">Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="9249e-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="9249e-123">Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="9249e-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="9249e-124">In den folgenden Tabellen werden weitere Details dazu angezeigt, wie ein Benutzer mit einem lync 2013-Client oder einem Microsoft lync 2010-Client während und nach dem Failback betroffen ist, und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit ihm interagieren, der wieder fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="9249e-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="9249e-125">Benutzer mit Microsoft Office Communicator 2007 R2-Clients können sich erst anmelden, wenn der Front-End-Pool komplett Fehler zurück ist.)</span><span class="sxs-lookup"><span data-stu-id="9249e-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="9249e-126">Der Begriff *betroffener Benutzer* bezieht sich auf sämtliche Benutzer, bei denen ein Failover im Home-Pool aufgetreten ist und die daher vom Sicherungspool verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9249e-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="9249e-127">Definitionsgemäß ist jeder Benutzer, der ursprünglich im Sicherungspool beheimatet ist, kein betroffener Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9249e-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="9249e-128">Benutzererfahrung eines betroffenen Benutzers bei einem Pool in Failback</span><span class="sxs-lookup"><span data-stu-id="9249e-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9249e-129">Benutzerstatus oder -aufgabe</span><span class="sxs-lookup"><span data-stu-id="9249e-129">User state or task</span></span></th>
<th><span data-ttu-id="9249e-130">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="9249e-130">During failback</span></span></th>
<th><span data-ttu-id="9249e-131">Nach abgeschlossenem Failback</span><span class="sxs-lookup"><span data-stu-id="9249e-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9249e-132">Benutzerstatus des bereits angemeldeten Benutzers</span><span class="sxs-lookup"><span data-stu-id="9249e-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="9249e-p108">Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="9249e-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9249e-135">Benutzer bleibt angemeldet und wechselt in den regulären Modus.</span><span class="sxs-lookup"><span data-stu-id="9249e-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9249e-136">Neuer Benutzer meldet sich an.</span><span class="sxs-lookup"><span data-stu-id="9249e-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="9249e-137">Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.</span><span class="sxs-lookup"><span data-stu-id="9249e-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9249e-138">Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.</span><span class="sxs-lookup"><span data-stu-id="9249e-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9249e-139">Von betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9249e-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="9249e-p109">Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="9249e-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9249e-p110">Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9249e-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9249e-144">Von nicht betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9249e-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="9249e-p111">Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist auf die Aktionen beschränkt, die er im Ausfallsicherheitsmodus ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="9249e-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9249e-147">Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="9249e-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9249e-148">Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9249e-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="9249e-149">Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="9249e-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9249e-150">Für alle Modalitäten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9249e-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9249e-151">Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird</span><span class="sxs-lookup"><span data-stu-id="9249e-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="9249e-152">Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="9249e-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="9249e-153">Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus. Anwesenheitsänderungen werden nun reflektiert.</span><span class="sxs-lookup"><span data-stu-id="9249e-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9249e-154">Verfügbarkeit von Kontaktlisten und Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="9249e-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="9249e-155">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="9249e-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="9249e-156">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="9249e-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9249e-157">Alle Peer-zu-Peer-Sitzungen und -modalitäten</span><span class="sxs-lookup"><span data-stu-id="9249e-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="9249e-158">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="9249e-158">Available</span></span></p></td>
<td><p><span data-ttu-id="9249e-159">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="9249e-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="9249e-160">Benutzererfahrung mit einem verwalteten Benutzer in einem nicht betroffenen Pool während eines Failbacks eines anderen Pools</span><span class="sxs-lookup"><span data-stu-id="9249e-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9249e-161">Benutzeraufgabe</span><span class="sxs-lookup"><span data-stu-id="9249e-161">User task</span></span></th>
<th><span data-ttu-id="9249e-162">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="9249e-162">During failback</span></span></th>
<th><span data-ttu-id="9249e-163">Nach abgeschlossenem Failback</span><span class="sxs-lookup"><span data-stu-id="9249e-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9249e-164">Anwesenheitsinformationen des betroffenen Benutzers anzeigen</span><span class="sxs-lookup"><span data-stu-id="9249e-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="9249e-165">Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.</span><span class="sxs-lookup"><span data-stu-id="9249e-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="9249e-p112">In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="9249e-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9249e-168">Von betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9249e-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="9249e-169">Alle Modalitäten der Konferenz werden abgebrochen</span><span class="sxs-lookup"><span data-stu-id="9249e-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="9249e-p113">Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9249e-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9249e-172">Von nicht betroffenen Benutzern organisierte laufende Konferenzen</span><span class="sxs-lookup"><span data-stu-id="9249e-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="9249e-173">Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="9249e-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="9249e-174">Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.</span><span class="sxs-lookup"><span data-stu-id="9249e-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9249e-175">Alle Peer-zu-Peer-Sitzungen und -modalitäten</span><span class="sxs-lookup"><span data-stu-id="9249e-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="9249e-176">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="9249e-176">Available</span></span></p></td>
<td><p><span data-ttu-id="9249e-177">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="9249e-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

