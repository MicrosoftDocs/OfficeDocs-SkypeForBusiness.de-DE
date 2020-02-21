---
title: 'Lync Server 2013: Übersicht über die gruppenanrufannahme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9001d3e89e07943915b923ec4bfa8abf2683c78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="949fd-102">Übersicht über die gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="949fd-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="949fd-103">_**Letztes Änderungsstand des Themas:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="949fd-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="949fd-104">Group Call Pickup, ein neues Feature in kumulierten Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe an Ihre Kollegen von ihren eigenen Telefonen aus zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="949fd-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="949fd-105">Dieses neue Feature erhöht die Verfügbarkeit einer Benutzer Leitung, indem andere Benutzer einen eingehenden Anruf annehmen können, indem Sie die Nummer einer Anrufannahme Gruppe wählen.</span><span class="sxs-lookup"><span data-stu-id="949fd-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="949fd-106">Wenn die gruppenanrufannahme bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an Voicemail weitergeleitet werden, erheblich reduziert werden, was besonders nützlich für Anrufe von Kunden ist, die sich außerhalb Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="949fd-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="949fd-107">Das Feature für die gruppenanrufannahme wurde speziell für Geschäftseinheiten in offenen Office-Umgebungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="949fd-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="949fd-108">Eingehende Anrufe sind nicht störend, da Sie nur am vorgesehenen Bestimmungsort Klingeln.</span><span class="sxs-lookup"><span data-stu-id="949fd-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="949fd-109">Andere Benutzer, die den Ring hören, können den Anruf jedoch auch einfach durch Wählen der Gruppennummer abholen.</span><span class="sxs-lookup"><span data-stu-id="949fd-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="949fd-110">In Umgebungen, in denen sich Benutzer nicht in einem offenen Office-Layout befinden oder wenn Benutzer, die eine gemeinsame Verantwortung teilen, geografisch verteilt sind, stellt die Team Anruf Lösung die am besten geeignete Lösung dar.</span><span class="sxs-lookup"><span data-stu-id="949fd-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="949fd-111">Der Hauptunterschied zwischen der gruppenanrufannahme und dem Teamanruf besteht darin, dass bei der gruppenanrufannahme ein eingehender Anruf nur am vorgesehenen Ziel klingelt, aber jeder kann trotzdem entscheiden, ob er eine Antwort erhalten möchte, indem er eine Gruppennummer wählt.</span><span class="sxs-lookup"><span data-stu-id="949fd-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="949fd-112">Bei einem Teamanruf klingelt der Anruf an allen Telefonen der Teammitglieder, und jeder Benutzer im Team kann das Telefon abholen, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="949fd-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="949fd-113">Ein weiterer Unterschied zwischen der gruppenanrufannahme und dem Team Anruf besteht darin, dass die gruppenanrufannahme über lync Server von einem Administrator verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="949fd-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="949fd-114">Mit dem Team Anruf verwalten Endbenutzer das Feature mithilfe des lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="949fd-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="949fd-115">Bei der gruppenanrufannahme kann daher dieser Aspekt der Anrufverwaltung zentralisiert werden.</span><span class="sxs-lookup"><span data-stu-id="949fd-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="949fd-116">Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="949fd-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="949fd-117">Wenn Sie die gruppenanrufannahme bereitstellen, konfigurieren Sie die Orbit-Tabelle für das Parken von Anrufen mit getrennten Bereichen von Durchwahlnummern, die als Nummern für die Anrufannahme Gruppe festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="949fd-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="949fd-118">Wie die Umlaufbahn Nummern für die Anrufannahme müssen Gruppennummern für die Anrufannahme virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="949fd-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="949fd-119">Jede Front-End-Pool, in der Sie die gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche der Anrufannahme Gruppennummern verfügen.</span><span class="sxs-lookup"><span data-stu-id="949fd-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="949fd-120">Die Gruppennummern Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="949fd-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="949fd-121">Nummernbereiche, die als Gruppenanruf-Abhol Nummern in der Orbit-Tabelle für das Parken von Anrufen festgelegt sind, können nicht mithilfe der lync Server-Systemsteuerung verwaltet oder angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="949fd-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="949fd-122">Die einzige Möglichkeit zum Anzeigen aller Nummernbereiche in der Orbit-Tabelle für das Parken von anrufen ist die Verwendung lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="949fd-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="949fd-123">Auf ähnliche Weise ist die einzige Möglichkeit zum Hinzufügen, ändern oder Entfernen von Gruppenanruf-Pickup-Nummern die Verwendung lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="949fd-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="949fd-124">Nachdem Sie die Nummern für die Anrufannahme Gruppe konfiguriert haben, weisen Sie Benutzer einer Anrufannahme Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="949fd-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="949fd-125">Jeder Benutzer, der einer Anrufannahme Gruppe zugewiesen ist, kann seine Anrufe von anderen Benutzern beantworten lassen.</span><span class="sxs-lookup"><span data-stu-id="949fd-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="949fd-126">Wenn ein Anruf an einen Benutzer übertragen wird, der einer Anrufannahme Gruppe zugewiesen ist, kann jeder andere Benutzer, der den Anruf bemerkt, ihn beantworten, indem er die Nummer der Anrufannahme Gruppe manuell anwählt.</span><span class="sxs-lookup"><span data-stu-id="949fd-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="949fd-127">Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="949fd-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="949fd-128">Wenn ein Anruf von einem anderen Benutzer abgeholt wird, wird eine Benachrichtigung an die ursprünglich angerufene Nummer gesendet.</span><span class="sxs-lookup"><span data-stu-id="949fd-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="949fd-129">Ein Benutzer kann nur Mitglied einer Anrufannahme Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="949fd-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="949fd-130">Jeder Benutzer in der lync Server-Bereitstellung kann zwar einen Anruf an ein Mitglied der Anrufannahme Gruppe annehmen, aber die Person, die den Anruf annimmt, muss die richtige Nummer für die Anrufannahme Gruppe kennen, um zu wählen.</span><span class="sxs-lookup"><span data-stu-id="949fd-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="949fd-131">Wenn ein Benutzer eine Anrufannahme-Gruppennummer zum Annehmen eines Anrufs wählt, wenn mehrere Telefone in der Gruppe Klingeln, antwortet der Benutzer mit dem Anruf, der am längsten klingelt.</span><span class="sxs-lookup"><span data-stu-id="949fd-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="949fd-132">Die Einstellungen für das gleichzeitige Klingeln sind für Benutzer mit gruppenanrufannahme funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="949fd-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="949fd-133">Das bedeutet, dass ein Anruf, der an einen Benutzer mit gruppenanrufannahme erfolgt, für alle konfigurierten Ziele klingelt und ein anderer Benutzer den Anruf annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="949fd-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="949fd-134">Die Ausnahme zu dieser Regel besteht darin, dass der Benutzer das gleichzeitige Klingeln so konfiguriert, dass alle Teammitglieder aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="949fd-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="949fd-135">Die gruppenanrufannahme kann nicht zur Beantwortung der folgenden Anruftypen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="949fd-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="949fd-136">Anrufe an eine privatleitungen</span><span class="sxs-lookup"><span data-stu-id="949fd-136">Calls to a private line</span></span>

  - <span data-ttu-id="949fd-137">Anrufe von einem Kontakt, dem die Datenschutz Beziehung "Freunde und Familie" zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="949fd-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="949fd-138">Ein Benutzer, der Mitglied einer Anrufannahme Gruppe ist, kann verhindern, dass bestimmte Anrufe über die gruppenanrufannahme abgerufen werden, indem der Kontakt als persönlicher Kontakt im lync-Client gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="949fd-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="949fd-139">Wenn Sie einen Kontakt als persönlichen Kontakt markieren möchten, legen Sie die Datenschutz Beziehung für den Kontakt auf "Freunde und Familie" fest.</span><span class="sxs-lookup"><span data-stu-id="949fd-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="949fd-140">Alle eingehenden Anrufe von Kontakten mit der Datenschutz Beziehung, die auf Freunde und Familie festgelegt sind, können nicht mithilfe der gruppenanrufannahme abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="949fd-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="949fd-141">Video Teil von Audio/Video-anrufen</span><span class="sxs-lookup"><span data-stu-id="949fd-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="949fd-142">Wenn ein Benutzer auf einen Audio/Video-Anruf antwortet, erhält der Benutzer nur die Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="949fd-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="949fd-143">Entweder der Anrufer oder die Person, die den Anruf annimmt, kann den Anruf eskalieren, um Video hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="949fd-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="949fd-144">Gleichzeitiges Klingeln von anrufen, die an Team Anruf Mitglieder weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="949fd-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="949fd-145">An eine Stellvertretung weitergeleitete Anrufe</span><span class="sxs-lookup"><span data-stu-id="949fd-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="949fd-146">An eine Reaktionsgruppe weitergeleitete Anrufe</span><span class="sxs-lookup"><span data-stu-id="949fd-146">Calls routed to a response group</span></span>

<span data-ttu-id="949fd-147">Die folgenden Benutzertypen können nicht an der gruppenanrufannahme teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="949fd-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="949fd-148">Das heißt, Sie sollten nicht in eine gruppenanrufannahme Gruppe aufgenommen werden, und Sie können keine Anrufe für Benutzer abholen, für die die gruppenanrufannahme aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="949fd-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="949fd-149">Benutzer, die Online in einer hybridbereitstellung verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="949fd-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="949fd-150">Benutzer, die nicht in einem lync Server 2013 Pool mit kumulierten Updates für lync Server 2013 verwaltet werden: 2013. Februar in einer lokalen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="949fd-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="949fd-151">Wenn niemand einen Anruf an ein Mitglied einer Anrufannahme Gruppe beantwortet, wird der Anruf wie in den Clienteinstellungen angegeben weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="949fd-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="949fd-152">Das heißt, der Anruf geht an Voicemail oder wird an ein anderes Ziel weitergeleitet, wie in den Clienteinstellungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="949fd-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

