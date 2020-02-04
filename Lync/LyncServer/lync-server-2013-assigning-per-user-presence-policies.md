---
title: 'Lync Server 2013: Zuweisen von Anwesenheitsrichtlinien für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="257ae-102">Zuweisen von Anwesenheitsrichtlinien für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="257ae-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="257ae-103">_**Letztes Änderungsdatum des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="257ae-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="257ae-104">Eine Anwesenheitsrichtlinie besteht aus einer Reihe von Grenzwerten und Einschränkungen, die sich auf die Anwesenheit auswirken.</span><span class="sxs-lookup"><span data-stu-id="257ae-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="257ae-105">In der folgenden Tabelle werden die in lync Server 2013 verfügbaren Anwesenheitsrichtlinien Einstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="257ae-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="257ae-106">Einstellungen für Anwesenheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="257ae-106">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="257ae-107">XML-Name</span><span class="sxs-lookup"><span data-stu-id="257ae-107">XML name</span></span></th>
<th><span data-ttu-id="257ae-108">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="257ae-108">Display name</span></span></th>
<th><span data-ttu-id="257ae-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="257ae-109">Description</span></span></th>
<th><span data-ttu-id="257ae-110">Typ</span><span class="sxs-lookup"><span data-stu-id="257ae-110">Type</span></span></th>
<th><span data-ttu-id="257ae-111">Wert</span><span class="sxs-lookup"><span data-stu-id="257ae-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="257ae-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="257ae-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="257ae-113">Maximale Anzahl von Abonnenten Kategorie-Abonnements</span><span class="sxs-lookup"><span data-stu-id="257ae-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="257ae-114">Begrenzt die Anzahl der Abonnements für Abonnenten Kategorien.</span><span class="sxs-lookup"><span data-stu-id="257ae-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="257ae-115">Wenn Communicator beispielsweise die Anwesenheit eines Benutzers abonniert, erhält er ein Kategorie-Abonnement für jede Visitenkarte, Kalenderdaten, Notizen, Dienste und Zustandskategorien.</span><span class="sxs-lookup"><span data-stu-id="257ae-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="257ae-116">Eine Einstellung von "0" bedeutet, dass der Benutzer oder das Kontaktobjekt nicht von anderen abonniert werden kann.</span><span class="sxs-lookup"><span data-stu-id="257ae-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="257ae-117">Diese Einstellung kann erhebliche Auswirkungen auf die Leistung haben, wenn Sie auf eine hohe Zahl festgelegt ist und der durchschnittliche Benutzer eine große Anzahl von Benutzern abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="257ae-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="257ae-118">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="257ae-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="257ae-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="257ae-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="257ae-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="257ae-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="257ae-121">Maximale Anzahl von Benachrichtigungen für Anwesenheitsabonnements in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="257ae-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="257ae-122">Schränkt die Anzahl von Einträgen in der Tabelle "angeforderte Abonnenten" ein.</span><span class="sxs-lookup"><span data-stu-id="257ae-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="257ae-123">Diese Einstellung bestimmt die maximale Anzahl von Eingabeaufforderungen, die für einen bestimmten Benutzer in die Warteschlange gestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="257ae-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="257ae-124">Wenn Benutzer a beispielsweise die Anwesenheit von Benutzer b abonniert hat, erhält Benutzer b eine Aufforderung, dass Benutzer a jetzt Benutzer b abonniert hat, und in der Tabelle mit der Aufforderung "Abonnenten" von Benutzer b wird eine Bestätigungsaufforderung erstellt.</span><span class="sxs-lookup"><span data-stu-id="257ae-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="257ae-125">Nachdem der Benutzer b das Abonnement akzeptiert oder bestätigt hat, wird die Bestätigungsaufforderung aus der Tabelle "angeforderte Abonnenten" von Benutzer b entfernt.</span><span class="sxs-lookup"><span data-stu-id="257ae-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="257ae-126">Eine Einstellung von "0" bedeutet, dass der Benutzer nicht dazu aufgefordert wird, wenn jemand seine Anwesenheit abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="257ae-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="257ae-127">Ganzzahl oder Token</span><span class="sxs-lookup"><span data-stu-id="257ae-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="257ae-128">0-500</span><span class="sxs-lookup"><span data-stu-id="257ae-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="257ae-129">Standardmäßig werden beim Bereitstellen von lync Server die Richtlinien **Standardrichtlinie** und **Dienst: Medium** -Anwesenheitsrichtlinien installiert.</span><span class="sxs-lookup"><span data-stu-id="257ae-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="257ae-130">In der folgenden Tabelle werden die spezifischen Einstellungen der beiden Anwesenheitsrichtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="257ae-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="257ae-131">Anwesenheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="257ae-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="257ae-132">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="257ae-132">Policy name</span></span></th>
<th><span data-ttu-id="257ae-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="257ae-133">Description</span></span></th>
<th><span data-ttu-id="257ae-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="257ae-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="257ae-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="257ae-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="257ae-136">Standardrichtlinie</span><span class="sxs-lookup"><span data-stu-id="257ae-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="257ae-137">Richtlinie für typische Benutzer.</span><span class="sxs-lookup"><span data-stu-id="257ae-137">Policy for typical users.</span></span> <span data-ttu-id="257ae-138">Dies ist die standardmäßige Anwesenheitsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="257ae-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="257ae-139">1000</span><span class="sxs-lookup"><span data-stu-id="257ae-139">1000</span></span></p></td>
<td><p><span data-ttu-id="257ae-140">200</span><span class="sxs-lookup"><span data-stu-id="257ae-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="257ae-141">Dienst: Mittel</span><span class="sxs-lookup"><span data-stu-id="257ae-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="257ae-142">Richtlinie für Anwendungen, die mehr Benutzer benötigen, um die Anwesenheit des Objekts zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="257ae-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="257ae-143">1000</span><span class="sxs-lookup"><span data-stu-id="257ae-143">1000</span></span></p></td>
<td><p><span data-ttu-id="257ae-144">0</span><span class="sxs-lookup"><span data-stu-id="257ae-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

