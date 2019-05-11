---
title: Parken von Anrufen Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Parken Nummernbereiche definieren die temporären Nummern, in dem Geparkte Anrufe gehalten werden, bis eine Person oder Timeout abgerufen.
ms.openlocfilehash: 4788cf3bf51785005d88dbde6977f7f86e2efbb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916042"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="c0bf8-103">Funktion zum Parken von Anrufen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="c0bf8-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="c0bf8-104">Parken Nummernbereiche definieren die temporären Nummern, in dem Geparkte Anrufe gehalten werden, bis eine Person oder Timeout abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c0bf8-105">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="c0bf8-105">UI Reference</span></span>

<span data-ttu-id="c0bf8-106">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c0bf8-107">**Name** Geben Sie einen beschreibenden Namen, der den Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="c0bf8-108">Nach dem Speichern des Nummernbereichs kann dieser Name nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="c0bf8-109">**Zahlenbereich** Geben Sie im ersten Feld die Anfangsnummer des Bereichs an.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="c0bf8-110">Geben Sie im zweiten Feld die Endnummer des Nummernbereichs ein.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="c0bf8-111">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="c0bf8-112">Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="c0bf8-p103">Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="c0bf8-115">Wenn der Nummernbereich mit dem Zeichen beginnt \* oder #, der Bereich muss größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="c0bf8-116">Gültige Werte: Zeichenfolge des regulären Ausdrucks muss übereinstimmen ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="c0bf8-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="c0bf8-117">Dies bedeutet, dass der Wert muss eine Zeichenfolge beginnend mit entweder die Zeichen \* oder # oder eine Zahl zwischen 1 und 9 (das erste Zeichen darf nicht NULL sein).</span><span class="sxs-lookup"><span data-stu-id="c0bf8-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="c0bf8-118">Wenn das erste Zeichen ist \* oder #, in das folgende Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein).</span><span class="sxs-lookup"><span data-stu-id="c0bf8-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="c0bf8-119">Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzliche Zeichen sein (z. B. "#6000", "\*92000", "\*95551212" und "915551212").</span><span class="sxs-lookup"><span data-stu-id="c0bf8-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="c0bf8-120">Wenn das erste Zeichen nicht ist \* oder #, in das erste Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein), gefolgt von bis zu acht Zeichen jedes eine Zahl von 0 bis 9 (zum Beispiel: 915551212; 41212; 300).</span><span class="sxs-lookup"><span data-stu-id="c0bf8-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="c0bf8-p105">Sie sollten über maximal 50.000 Nummern pro Pool verfügen. Jeder Nummernbereich umfasst normalerweise maximal 100 Nummern, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Nummern). Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="c0bf8-124">**FQDN des Zielservers** Wählen Sie den vollqualifizierten Domänennamen (FQDN) oder die Dienst-ID des Anwendungsdiensts, die die Anwendung zum Parken von Anrufen gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="c0bf8-125">Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Nummernbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c0bf8-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="c0bf8-126">Weitere Informationen zu parken Features und Funktionen finden Sie unter [Planen des Parkens von Anrufen in Skype für Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="c0bf8-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="c0bf8-127">Ausführliche Informationen zum Arbeiten mit Parken Nummernbereiche finden Sie unter [Konfigurieren Telefon Anzahl Erweiterungen für das Parken von Anrufen](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0bf8-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


