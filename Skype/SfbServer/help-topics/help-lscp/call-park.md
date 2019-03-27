---
title: Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Wenn Sie ein Anruf geparkt wurde, wird er übertragen in eine temporäre Zahl ist, in dem der Anruf gehalten, bis jemand ruft sie ab, oder das Zeitlimit überschritten. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für Geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, der die Anwendung zum Parken ausgeführt wird kann eine oder mehrere Bereiche von Erweiterungen verfügen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: 2470d820b6536fdcd966e25d8719cd89903b4519
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878850"
---
# <a name="call-park"></a><span data-ttu-id="dd944-106">Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="dd944-106">Call Park</span></span>

<span data-ttu-id="dd944-107">Wenn Sie ein Anruf geparkt wurde, wird er übertragen in eine temporäre Zahl ist, in dem der Anruf gehalten, bis jemand ruft sie ab, oder das Zeitlimit überschritten. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für Geparkte Anrufe reservieren.</span><span class="sxs-lookup"><span data-stu-id="dd944-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="dd944-108">Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist).</span><span class="sxs-lookup"><span data-stu-id="dd944-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="dd944-109">Jeder Pool, der die Anwendung zum Parken ausgeführt wird kann eine oder mehrere Bereiche von Erweiterungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="dd944-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="dd944-110">Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="dd944-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="dd944-111">Die Seite **Anruf Parken** zeigt eine Liste aller die Nummer des Parkens von Anrufen-Bereiche, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dd944-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="dd944-112">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="dd944-112">Tasks you can perform</span></span>

<span data-ttu-id="dd944-113">Auf der Seite **Anruf parken** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="dd944-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="dd944-114">Erstellen eines neuen Nummernbereichs</span><span class="sxs-lookup"><span data-stu-id="dd944-114">Create a new number range</span></span>

- <span data-ttu-id="dd944-115">Ändern eines vorhandenen Nummernbereichs</span><span class="sxs-lookup"><span data-stu-id="dd944-115">Change an existing number range</span></span>

- <span data-ttu-id="dd944-116">Löschen eines Nummernbereichs</span><span class="sxs-lookup"><span data-stu-id="dd944-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="dd944-117">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="dd944-117">UI Reference</span></span>

<span data-ttu-id="dd944-118">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd944-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="dd944-119">**Neue** Startet einen neuen Nummernbereich Parken.</span><span class="sxs-lookup"><span data-stu-id="dd944-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="dd944-120">**Bearbeiten** Öffnet den ausgewählten Nummernbereich zur Bearbeitung, wählt alle Nummernbereiche in der Liste aus oder löscht den ausgewählten Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="dd944-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="dd944-121">**Aktualisieren** Aktualisiert die Liste der Nummernbereiche.</span><span class="sxs-lookup"><span data-stu-id="dd944-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="dd944-122">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd944-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="dd944-123">**Name** Der eindeutige Name, der den Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="dd944-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="dd944-124">**Anfangsbereich gibt** Die Anfangsnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="dd944-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="dd944-125">**Endbereich** Die Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="dd944-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="dd944-126">**Ziel** Der vollqualifizierte Domänenname (FQDN) oder Dienst-ID des Anwendungsdiensts, die die Anwendung zum Parken von Anrufen für den Nummernbereich hostet.</span><span class="sxs-lookup"><span data-stu-id="dd944-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="dd944-127">Weitere Informationen zu parken Features und Funktionen finden Sie unter [Planen des Parkens von Anrufen in Skype für Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="dd944-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="dd944-128">Ausführliche Informationen zum Arbeiten mit Parken Nummernbereiche finden Sie unter [Konfigurieren Telefon Anzahl Erweiterungen für das Parken von Anrufen](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="dd944-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


