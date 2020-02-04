---
title: Parken von Anrufen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn ein Anruf abgestellt wird, wird er an eine temporäre Rufnummer übertragen, in der der Anruf abgehalten wird, bis er von jemandem abgebucht wird, oder wenn der Anruf abläuft. Sie müssen eine Tabelle mit den Bereichen der Durchwahlnummern konfigurieren, die für geparkte Anrufe reserviert werden. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, auf dem die Anwendung "Parken" ausgeführt wird, kann einen oder mehrere Bereichs Erweiterungen aufweisen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: 6519a678c2370e9763dddd3680c3a64257fe4305
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690320"
---
# <a name="call-park"></a><span data-ttu-id="bdb1a-106">Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="bdb1a-106">Call Park</span></span>

<span data-ttu-id="bdb1a-107">Wenn ein Anruf abgestellt wird, wird er an eine temporäre Rufnummer übertragen, in der der Anruf abgehalten wird, bis er von jemandem abgebucht wird, oder wenn der Anruf abläuft. Sie müssen eine Tabelle mit den Bereichen der Durchwahlnummern konfigurieren, die für geparkte Anrufe reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="bdb1a-108">Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist).</span><span class="sxs-lookup"><span data-stu-id="bdb1a-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="bdb1a-109">Jeder Pool, auf dem die Anwendung "Parken" ausgeführt wird, kann einen oder mehrere Bereichs Erweiterungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="bdb1a-110">Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="bdb1a-111">Auf der Seite " **Parken des Anrufs** " wird eine Liste aller für Ihre Organisation definierten Park Nummernbereiche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bdb1a-112">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="bdb1a-112">Tasks you can perform</span></span>

<span data-ttu-id="bdb1a-113">Auf der Seite **Anruf parken** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="bdb1a-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="bdb1a-114">Erstellen eines neuen Nummernbereichs</span><span class="sxs-lookup"><span data-stu-id="bdb1a-114">Create a new number range</span></span>

- <span data-ttu-id="bdb1a-115">Ändern eines vorhandenen Nummernbereichs</span><span class="sxs-lookup"><span data-stu-id="bdb1a-115">Change an existing number range</span></span>

- <span data-ttu-id="bdb1a-116">Löschen eines Nummernbereichs</span><span class="sxs-lookup"><span data-stu-id="bdb1a-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bdb1a-117">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="bdb1a-117">UI Reference</span></span>

<span data-ttu-id="bdb1a-118">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="bdb1a-119">**Neu** Startet einen neuen Anruf Park Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="bdb1a-120">**Bearbeiten** von Öffnet den markierten Zahlenbereich für die Bearbeitung, wählt alle Nummernbereiche in der Liste aus oder löscht den markierten Zahlenbereich.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="bdb1a-121">**Aktualisieren** Aktualisiert die Liste der Nummernbereiche.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="bdb1a-122">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="bdb1a-123">**Name** Der eindeutige Name, der den Zahlenbereich identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="bdb1a-124">**Start Bereich** Die Anfangszahl des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="bdb1a-125">**Endbereich** Die letzte Zahl des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="bdb1a-126">**Ziel** Den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die Dienst-ID des Anwendungsdiensts, der die Anruf Park Anwendung für den Nummernbereich hostet.</span><span class="sxs-lookup"><span data-stu-id="bdb1a-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="bdb1a-127">Details zu den Funktionen und Funktionen des Anruf Parks finden Sie unter [Planen des Anruf Parks in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="bdb1a-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="bdb1a-128">Details zum Arbeiten mit den Rufnummernbereichen des Anruf Parks finden Sie unter [Konfigurieren von Telefonnummern Erweiterungen für Park Anrufe](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="bdb1a-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


