---
title: 'Lync Server 2013: Übersicht über die Abholung von Gruppen anrufen'
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
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="376a3-102">Übersicht über die Gruppenanruf Abholung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="376a3-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376a3-103">_**Letztes Änderungsdatum des Themas:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="376a3-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="376a3-104">Der Gruppenanruf Pickup, ein neues Feature in kumulativen Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe von ihren eigenen Telefonen an Ihre Kollegen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="376a3-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="376a3-105">Dieses neue Feature erhöht die Verfügbarkeit einer Benutzer Zeile, indem es anderen Benutzern ermöglicht, einen eingehenden Anruf zu beantworten, indem Sie eine Gruppennummer für die Anruf Abholung wählen.</span><span class="sxs-lookup"><span data-stu-id="376a3-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="376a3-106">Wenn die Gruppenanruf Abholung bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an die Voicemail weitergeleitet werden, erheblich reduziert werden, was besonders für Anrufe von Kunden nützlich ist, die sich außerhalb Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="376a3-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="376a3-107">Das Feature für die Gruppenanruf Abholung ist insbesondere für Unternehmenseinheiten in offenen Office-Umgebungen konzipiert.</span><span class="sxs-lookup"><span data-stu-id="376a3-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="376a3-108">Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Zieltelefon klingeln.</span><span class="sxs-lookup"><span data-stu-id="376a3-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="376a3-109">Andere Benutzer, die das Klingeln hören, können den Anruf dennoch annehmen, indem sie einfach die Gruppennummer wählen.</span><span class="sxs-lookup"><span data-stu-id="376a3-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="376a3-110">In Umgebungen, in denen sich Benutzer nicht in einer offenen Büroanordnung oder – trotz gemeinsamer Verantwortungsbereiche – an verschiedenen geografischen Standorten befinden, ist die Teamanruffunktion die am besten geeignete Lösung.</span><span class="sxs-lookup"><span data-stu-id="376a3-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="376a3-111">Der Hauptunterschied zwischen Gruppenanruf Abholung und Teamanruf besteht darin, dass ein eingehender Anruf nur an dem vorgesehenen Ziel klingelt, aber jeder kann ihn trotzdem durch Wählen einer Gruppennummer beantworten.</span><span class="sxs-lookup"><span data-stu-id="376a3-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="376a3-112">Bei einem Teamanruf klingeln die Telefone aller Gruppenmitglieder und jeder Benutzer im Team kann den Anruf annehmen.</span><span class="sxs-lookup"><span data-stu-id="376a3-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="376a3-113">Ein weiterer Unterschied zwischen Gruppenanruf Abholung und Team Anruf besteht darin, dass die Abholung von Gruppen anrufen von einem Administrator über lync Server verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="376a3-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="376a3-114">Mit Team Anruf verwalten Endbenutzer das Feature mithilfe des lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="376a3-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="376a3-115">Mit der Gruppenanruf-Abholung kann dieser Aspekt der Anrufverwaltung also zentralisiert werden.</span><span class="sxs-lookup"><span data-stu-id="376a3-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="376a3-116">Die Abholung von Gruppen anrufen basiert auf der Anwendung für den Anruf Park.</span><span class="sxs-lookup"><span data-stu-id="376a3-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="376a3-117">Wenn Sie die Gruppenanruf Abholung bereitstellen, konfigurieren Sie die Orbit-Tabelle des Anruf Parks mit getrennten Bereichen von Durchwahlnummern, die als Gruppennummern für die Anruf Abholung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="376a3-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="376a3-118">Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Anrufannahmegruppe um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="376a3-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="376a3-119">Jeder Front-End-Pool, in dem Sie die Gruppenanruf Abholung bereitstellen, kann über einen oder mehrere Bereiche der Gruppennummern für die Anruf Abholung verfügen.</span><span class="sxs-lookup"><span data-stu-id="376a3-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="376a3-120">Die Gruppennummern Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="376a3-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="376a3-121">Nummernkreise, die als Gruppenanruf-Abhol Nummern in der Orbit-Tabelle des Anruf Parks bezeichnet werden, können mithilfe der lync Server-Systemsteuerung nicht verwaltet oder angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="376a3-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="376a3-122">Die einzige Möglichkeit, alle Nummernbereiche in der Orbit-Tabelle des Anruf Parks anzuzeigen, besteht darin, die lync Server-Verwaltungsshell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="376a3-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="376a3-123">Ebenso besteht die einzige Möglichkeit zum Hinzufügen, ändern oder Entfernen von Gruppenanruf-Pickup-Nummern darin, die lync Server-Verwaltungsshell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="376a3-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="376a3-p106">Nach dem Konfigurieren der Nummern für die Anrufannahmegruppe weisen Sie Benutzer einer Anrufannahmegruppe zu. Die Anrufe jedes Benutzers, der einer Anrufannahmegruppe zugewiesen ist, können von anderen Personen angenommen werden. Wenn ein Anruf an einen Benutzer eingeht, der einer Anrufannahmegruppe zugewiesen ist, kann ein beliebiger anderer Benutzer diesen Anruf annehmen, indem er manuell die Nummer für die Anrufannahmegruppe wählt. Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer angenommen wird, wird eine Benachrichtigung an den Benutzer gesendet, dessen Nummer ursprünglich gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="376a3-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="376a3-129">Ein Benutzer kann nur in einer Anrufannahmegruppe Mitglied sein.</span><span class="sxs-lookup"><span data-stu-id="376a3-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="376a3-130">Obwohl jeder Benutzer in der lync Server-Bereitstellung einen Anruf an ein Mitglied der Anruf Abholungs Gruppe annehmen kann, muss die Person, die den Anruf annimmt, die richtige Anruf-Abhol Gruppennummer kennen, um zu wählen.</span><span class="sxs-lookup"><span data-stu-id="376a3-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="376a3-131">Wenn ein Benutzer zum Annehmen eines Anrufs die Nummer für die Anrufannahmegruppe wählt und mehrere Telefone in der Gruppe klingeln, nimmt der Benutzer den Anruf an, der bereits am längsten klingelt.</span><span class="sxs-lookup"><span data-stu-id="376a3-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="376a3-132">Einstellungen für gleichzeitig eingehende Anrufe funktionieren für Benutzer mit GroupCallPickup.</span><span class="sxs-lookup"><span data-stu-id="376a3-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="376a3-133">Das bedeutet, dass ein Anruf an einen Benutzer, der eine Gruppenanruf-Abholung hat, für alle konfigurierten Ziele klingelt und ein anderer Benutzer den Anruf annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="376a3-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="376a3-134">Eine Ausnahme zu dieser Regel tritt auf, wenn der Benutzer gleichzeitig eingehende Anrufe so konfiguriert, dass sie an alle Teammitglieder eingehen.</span><span class="sxs-lookup"><span data-stu-id="376a3-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="376a3-135">Die Gruppenanruf Abholung kann nicht zur Beantwortung der folgenden Anrufarten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="376a3-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="376a3-136">Anrufe an eine Privatleitung</span><span class="sxs-lookup"><span data-stu-id="376a3-136">Calls to a private line</span></span>

  - <span data-ttu-id="376a3-137">Anrufe von Kontakten, denen die private Beziehung „Freunde und Familie“ zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="376a3-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="376a3-138">Ein Benutzer, der Mitglied einer Anruf Abhol Gruppe ist, kann verhindern, dass bestimmte Anrufe über die Gruppenanruf Abholung abgerufen werden, indem der Kontakt als persönlicher Kontakt im lync-Client markiert wird.</span><span class="sxs-lookup"><span data-stu-id="376a3-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="376a3-139">Zum Kennzeichnen eines Kontakts als persönlichen Kontakt legen Sie die private Beziehung für den Kontakt auf „Freunde und Familie“ fest.</span><span class="sxs-lookup"><span data-stu-id="376a3-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="376a3-140">Alle eingehenden Anrufe von Kontakten mit der privaten Beziehung, die auf Freunde und Familie eingestellt sind, können mit der Gruppenanruf-Abholung nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="376a3-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="376a3-141">Videoteil von Audio-/Videoanrufen</span><span class="sxs-lookup"><span data-stu-id="376a3-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="376a3-p109">Wenn ein Benutzer einen Audio-/Videoanruf annimmt, empfängt er nur den Audioteil. Der Anruf kann entweder vom Anrufer oder von der Person, die den Anruf annimmt, hochgestuft und damit der Videoteil hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="376a3-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="376a3-144">Gleichzeitig eingehende Anrufe, die an Teamanrufmitglieder weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="376a3-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="376a3-145">An einen Stellvertreter weitergeleitete Anrufe</span><span class="sxs-lookup"><span data-stu-id="376a3-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="376a3-146">An eine Antwortgruppe weitergeleitete Anrufe</span><span class="sxs-lookup"><span data-stu-id="376a3-146">Calls routed to a response group</span></span>

<span data-ttu-id="376a3-147">Die folgenden Benutzertypen können nicht an der Gruppenanruf Abholung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="376a3-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="376a3-148">Das heißt, Sie sollten nicht in eine Gruppenanruf-Abhol Gruppe aufgenommen werden, und Sie können keine Anrufe für Benutzer aufnehmen, die die Gruppenanruf Abholung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="376a3-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="376a3-149">Benutzer, die online in einer Hybridbereitstellung gehostet sind</span><span class="sxs-lookup"><span data-stu-id="376a3-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="376a3-150">Benutzer, die nicht in einem lync Server 2013-Pool mit kumulativen Updates für lync Server 2013: Februar 2013 in einer lokalen Bereitstellung verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="376a3-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="376a3-p111">Wenn ein Anruf an ein Mitglied einer Anrufannahmegruppe nicht angenommen wird, wird der Anruf gemäß den Angaben in den Clienteinstellungen weitergeleitet. Das bedeutet, dass der Anruf an Voicemail oder wie in den Clienteinstellungen angegeben an ein anderes Zieltelefon weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="376a3-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

