---
title: Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Unternehmen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 0032d46507c6cb91629b94662ec67bf9c67b7cc4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885610"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="2b168-103">Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2b168-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="2b168-104">Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="2b168-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="2b168-105">Gruppe aufrufen Pickup-basiert auf die Anwendung zum Parken.</span><span class="sxs-lookup"><span data-stu-id="2b168-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="2b168-106">Bei der Bereitstellung von Gruppe aufrufen Pickup-müssen Sie die orbittabelle für das Parken von Anrufen mit Bereichen von Telefonnummern konfigurieren, die als Rufnummern pickup Gruppe festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2b168-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="2b168-107">Bei diesen Gruppennummern handelt es sich um Nummern, die Benutzer wählen, um Anrufe anzunehmen, die an einen Benutzer eingehen.</span><span class="sxs-lookup"><span data-stu-id="2b168-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="2b168-108">Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Gruppenanrufannahme um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2b168-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2b168-109">Jeder Front-End-Pool, in der Gruppe anrufen Pickup-bereitstellen, kann ein oder mehrere Bereiche des pickup Gruppe Rufnummern haben.</span><span class="sxs-lookup"><span data-stu-id="2b168-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="2b168-110">Die Gruppennummernbereiche müssen in der in Ihrer Bereitstellung global eindeutig sein und müssen als Typ **GroupPickup** zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2b168-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="2b168-111">Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2b168-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="2b168-112">Sie müssen die Skype für Business Server-Verwaltungsshell verwenden, erstellen, ändern, entfernen und anzeigen Gruppe aufrufen Pickup-Nummernbereiche in der orbittabelle für das Parken von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="2b168-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="2b168-113">Gruppe aufrufen Pickup-Nummernbereiche stehen nicht in Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="2b168-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="2b168-114">Die Nummernbereiche für die Anrufannahmegruppe müssen folgenden Regeln entsprechen:</span><span class="sxs-lookup"><span data-stu-id="2b168-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="2b168-115">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="2b168-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="2b168-116">Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="2b168-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="2b168-p104">Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</span><span class="sxs-lookup"><span data-stu-id="2b168-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="2b168-119">Wenn der Nummernbereich mit dem Zeichen beginnt \* oder #, der Bereich muss größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="2b168-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="2b168-120">Gültige Werte: Zeichenfolge des regulären Ausdrucks muss übereinstimmen ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="2b168-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="2b168-121">Dies bedeutet, dass der Wert muss eine Zeichenfolge beginnend mit entweder die Zeichen \* oder # oder eine Zahl zwischen 1 und 9 (das erste Zeichen darf nicht NULL sein).</span><span class="sxs-lookup"><span data-stu-id="2b168-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="2b168-122">Wenn das erste Zeichen ist \* oder #, in das folgende Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein).</span><span class="sxs-lookup"><span data-stu-id="2b168-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="2b168-123">Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzliche Zeichen sein (z. B. "#6000", "\*92000", "\*95551212" und "915551212").</span><span class="sxs-lookup"><span data-stu-id="2b168-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="2b168-124">Wenn das erste Zeichen nicht ist \* oder #, in das erste Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein), gefolgt von bis zu acht Zeichen jedes eine Zahl von 0 bis 9 (beispielsweise "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="2b168-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="2b168-125">So erstellen oder ändern Sie einen Bereich für die Anrufannahmegruppe</span><span class="sxs-lookup"><span data-stu-id="2b168-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="2b168-126">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="2b168-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="2b168-127">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="2b168-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="2b168-128">Mit **New-CsCallParkOrbit** erstellen Sie einen neuen Nummernbereich für die Anrufannahmegruppe.</span><span class="sxs-lookup"><span data-stu-id="2b168-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="2b168-129">Mit **Set-CsCallParkOrbit** ändern Sie einen vorhandenen Nummernbereich für die Anrufannahmegruppe.</span><span class="sxs-lookup"><span data-stu-id="2b168-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="2b168-130">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2b168-130">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="2b168-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2b168-131">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="2b168-132">Das folgende Beispiel zeigt, wie ein Nummernbereich von Orbits für das Parken von Anrufen zu Anrufannahmegruppen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2b168-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="2b168-133">Verwenden Sie dieses Cmdlet zum Ändern der zugewiesenen Nummernbereiche nur dann, wenn Sie ursprünglich einen falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2b168-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="2b168-134">Wenn der Nummernbereich bereits verwendet wird und Sie den Typ von „CallPark“ zu „GroupPickup“ oder umgekehrt ändern, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="2b168-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="2b168-135">Angenommen, wenn Sie einen Nummernbereich von CallPark in GroupPick ändern, können die Anwendung zum Parken nicht mehr diesem Bereich der Orbits für das Parken von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="2b168-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b168-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b168-136">See also</span></span>

[<span data-ttu-id="2b168-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="2b168-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="2b168-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="2b168-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="2b168-139">Löschen eines Orbitbereichs für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="2b168-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
