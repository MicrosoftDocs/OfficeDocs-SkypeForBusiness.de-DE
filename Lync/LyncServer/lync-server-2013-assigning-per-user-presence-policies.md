---
title: 'Lync Server 2013: Zuweisen von benutzerspezifischen Anwesenheitsrichtlinien'
description: 'Lync Server 2013: Zuweisen von benutzerspezifischen Anwesenheitsrichtlinien.'
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
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563371"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="83380-103">Zuweisen von benutzerspezifischen Präsenz Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83380-103">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83380-104">_**Letztes Änderungsstand des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="83380-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="83380-105">Bei einer Anwesenheitsrichtlinie handelt es sich um eine Reihe von Beschränkungen und Einschränkungen, die sich auf die Anwesenheit auswirken.</span><span class="sxs-lookup"><span data-stu-id="83380-105">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="83380-106">In der folgenden Tabelle werden die verfügbaren Anwesenheitsrichtlinien Einstellungen in lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="83380-106">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="83380-107">Einstellungen für Anwesenheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="83380-107">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="83380-108">XML-Name</span><span class="sxs-lookup"><span data-stu-id="83380-108">XML name</span></span></th>
<th><span data-ttu-id="83380-109">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="83380-109">Display name</span></span></th>
<th><span data-ttu-id="83380-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83380-110">Description</span></span></th>
<th><span data-ttu-id="83380-111">Typ</span><span class="sxs-lookup"><span data-stu-id="83380-111">Type</span></span></th>
<th><span data-ttu-id="83380-112">Wert</span><span class="sxs-lookup"><span data-stu-id="83380-112">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83380-113">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="83380-113">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="83380-114">Maximale Anzahl von Abonnenten Kategorie-Abonnements</span><span class="sxs-lookup"><span data-stu-id="83380-114">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="83380-115">Schränkt die Anzahl der Abonnenten Kategorie-Abonnements ein.</span><span class="sxs-lookup"><span data-stu-id="83380-115">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="83380-116">Wenn Communicator beispielsweise die Anwesenheit eines Benutzers abonniert, erhält es ein Kategorie-Abonnement für jede Visitenkarte, Kalenderdaten, Notizen, Dienste und Status Kategorien.</span><span class="sxs-lookup"><span data-stu-id="83380-116">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="83380-117">Eine Einstellung von 0 bedeutet, dass das Benutzer-oder Kontaktobjekt nicht von anderen abonniert werden kann.</span><span class="sxs-lookup"><span data-stu-id="83380-117">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="83380-118">Diese Einstellung kann erhebliche Auswirkungen auf die Leistung haben, wenn Sie auf eine hohe Zahl festgelegt ist, und der durchschnittliche Benutzer hat eine große Anzahl von Benutzern, die seine Anwesenheit abonnieren.</span><span class="sxs-lookup"><span data-stu-id="83380-118">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="83380-119">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="83380-119">Integer</span></span></p></td>
<td><p><span data-ttu-id="83380-120">0-3000</span><span class="sxs-lookup"><span data-stu-id="83380-120">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83380-121">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="83380-121">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="83380-122">Maximale Anzahl von Benachrichtigungen in der Warteschlange für Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="83380-122">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="83380-123">Schränkt die Anzahl der Einträge in der Tabelle "angeforderte Abonnenten" ein.</span><span class="sxs-lookup"><span data-stu-id="83380-123">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="83380-124">Diese Einstellung bestimmt die maximale Anzahl von Ansagen, die für einen bestimmten Benutzer in die Warteschlange gestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="83380-124">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="83380-125">Wenn Benutzer a beispielsweise die Anwesenheit von Benutzer b abonniert, erhält Benutzer b eine Aufforderung, dass Benutzer a jetzt Benutzer b abonniert hat, und in der Tabelle mit den Teilnehmern von Benutzer b wird eine Bestätigungsaufforderung erstellt.</span><span class="sxs-lookup"><span data-stu-id="83380-125">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="83380-126">Nachdem der Benutzer b das Abonnement akzeptiert oder bestätigt hat, wird die Bestätigungsaufforderung aus Benutzer b-Tabelle "angeforderte Abonnenten" entfernt.</span><span class="sxs-lookup"><span data-stu-id="83380-126">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="83380-127">Eine Einstellung von 0 bedeutet, dass der Benutzer nicht aufgefordert wird, wenn jemand seine Anwesenheit abonniert.</span><span class="sxs-lookup"><span data-stu-id="83380-127">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="83380-128">Ganze Zahl oder Token</span><span class="sxs-lookup"><span data-stu-id="83380-128">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="83380-129">0-500</span><span class="sxs-lookup"><span data-stu-id="83380-129">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83380-130">Standardmäßig werden die **Standardrichtlinien** und- **Dienste: mittlere** Anwesenheitsrichtlinien installiert, wenn Sie lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="83380-130">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="83380-131">In der folgenden Tabelle werden die spezifischen Einstellungen der beiden Anwesenheitsrichtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="83380-131">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="83380-132">Anwesenheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="83380-132">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83380-133">Name der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="83380-133">Policy name</span></span></th>
<th><span data-ttu-id="83380-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83380-134">Description</span></span></th>
<th><span data-ttu-id="83380-135">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="83380-135">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="83380-136">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="83380-136">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83380-137">Standardrichtlinie</span><span class="sxs-lookup"><span data-stu-id="83380-137">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="83380-138">Richtlinie für typische Benutzer.</span><span class="sxs-lookup"><span data-stu-id="83380-138">Policy for typical users.</span></span> <span data-ttu-id="83380-139">Dies ist die standardmäßige Anwesenheitsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="83380-139">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="83380-140">1000</span><span class="sxs-lookup"><span data-stu-id="83380-140">1000</span></span></p></td>
<td><p><span data-ttu-id="83380-141">200</span><span class="sxs-lookup"><span data-stu-id="83380-141">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83380-142">Dienst: Mittel</span><span class="sxs-lookup"><span data-stu-id="83380-142">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="83380-143">Richtlinie für Anwendungen, die mehr Benutzer benötigen, um die Anwesenheit des Objekts zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="83380-143">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="83380-144">1000</span><span class="sxs-lookup"><span data-stu-id="83380-144">1000</span></span></p></td>
<td><p><span data-ttu-id="83380-145">0</span><span class="sxs-lookup"><span data-stu-id="83380-145">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

