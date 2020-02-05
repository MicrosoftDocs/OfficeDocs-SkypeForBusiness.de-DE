---
title: Erstellen oder Ändern eines Gruppenanruf-Pickup-Nummernbereichs in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: In Skype for Business Server Enterprise-VoIP können Sie einen Gruppenanruf-Abhol Nummernbereich erstellen oder ändern.
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767878"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="fb41e-103">Erstellen oder Ändern eines Gruppenanruf-Pickup-Nummernbereichs in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fb41e-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="fb41e-104">In Skype for Business Server Enterprise-VoIP können Sie einen Gruppenanruf-Abhol Nummernbereich erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="fb41e-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="fb41e-105">Die Abholung von Gruppen anrufen basiert auf der Anwendung "Parken".</span><span class="sxs-lookup"><span data-stu-id="fb41e-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="fb41e-106">Wenn Sie die Gruppenanruf Abholung bereitstellen, müssen Sie die Umlaufbahn Tabelle des Anruf Parks mit Bereichen von Telefonnummern konfigurieren, die als Gruppennummern für die Anruf Abholung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="fb41e-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="fb41e-107">Bei diesen Gruppennummern handelt es sich um Nummern, die Benutzer wählen, um Anrufe anzunehmen, die an einen Benutzer eingehen.</span><span class="sxs-lookup"><span data-stu-id="fb41e-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="fb41e-108">Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Gruppenanrufannahme um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fb41e-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="fb41e-109">Jeder Front-End-Pool, in dem Sie die Gruppenanruf Abholung bereitstellen, kann über einen oder mehrere Bereiche der Gruppennummern für die Anruf Abholung verfügen.</span><span class="sxs-lookup"><span data-stu-id="fb41e-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="fb41e-110">Die Gruppennummernbereiche müssen in der in Ihrer Bereitstellung global eindeutig sein und müssen als Typ **GroupPickup** zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fb41e-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="fb41e-111">Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fb41e-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="fb41e-112">Sie müssen die Skype for Business Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Pickup-Nummernbereichen in der Orbit-Tabelle des Anruf Parks verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb41e-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="fb41e-113">Nummernbereiche für Gruppenanrufe sind in der Skype for Business Server-Systemsteuerung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb41e-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="fb41e-114">Die Nummernbereiche für die Anrufannahmegruppe müssen folgenden Regeln entsprechen:</span><span class="sxs-lookup"><span data-stu-id="fb41e-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="fb41e-115">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="fb41e-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="fb41e-116">Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="fb41e-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="fb41e-p104">Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</span><span class="sxs-lookup"><span data-stu-id="fb41e-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="fb41e-119">Wenn der Zahlenbereich mit dem Zeichen \* oder # beginnt, muss der Bereich größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="fb41e-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="fb41e-120">Gültige Werte: muss mit der Zeichenfolge für den regulären\\Ausdruck übereinstimmen ([\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="fb41e-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="fb41e-121">Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine NULL sein).</span><span class="sxs-lookup"><span data-stu-id="fb41e-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="fb41e-122">Wenn das erste Zeichen oder \* # ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein).</span><span class="sxs-lookup"><span data-stu-id="fb41e-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="fb41e-123">Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise "#6000"\*, "92000"\*, "95551212" und "915551212").</span><span class="sxs-lookup"><span data-stu-id="fb41e-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="fb41e-124">Wenn das erste Zeichen nicht \* oder # ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, die jeweils eine Zahl von 0 bis 9 aufweisen (beispielsweise "915551212"; "41212"; "300").</span><span class="sxs-lookup"><span data-stu-id="fb41e-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="fb41e-125">So erstellen oder ändern Sie einen Bereich für die Anrufannahmegruppe</span><span class="sxs-lookup"><span data-stu-id="fb41e-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="fb41e-126">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb41e-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="fb41e-127">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="fb41e-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="fb41e-128">Mit **New-CsCallParkOrbit** erstellen Sie einen neuen Nummernbereich für die Anrufannahmegruppe.</span><span class="sxs-lookup"><span data-stu-id="fb41e-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="fb41e-129">Mit **Set-CsCallParkOrbit** ändern Sie einen vorhandenen Nummernbereich für die Anrufannahmegruppe.</span><span class="sxs-lookup"><span data-stu-id="fb41e-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="fb41e-130">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="fb41e-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="fb41e-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb41e-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="fb41e-132">Das folgende Beispiel zeigt, wie ein Nummernbereich von Orbits für das Parken von Anrufen zu Anrufannahmegruppen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="fb41e-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="fb41e-133">Verwenden Sie dieses Cmdlet zum Ändern der zugewiesenen Nummernbereiche nur dann, wenn Sie ursprünglich einen falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb41e-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="fb41e-134">Wenn der Nummernbereich bereits verwendet wird und Sie den Typ von „CallPark“ zu „GroupPickup“ oder umgekehrt ändern, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="fb41e-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="fb41e-135">Wenn Sie beispielsweise einen Zahlenbereich von CallPark in GroupPick ändern, kann die Anwendung für den Anruf Park diesen Bereich von Umlaufbahnen nicht mehr zum Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb41e-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb41e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb41e-136">See also</span></span>

[<span data-ttu-id="fb41e-137">Neu – CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="fb41e-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="fb41e-138">Satz-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="fb41e-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="fb41e-139">Löschen eines Umlauf Bereichs für einen Anruf Park</span><span class="sxs-lookup"><span data-stu-id="fb41e-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
