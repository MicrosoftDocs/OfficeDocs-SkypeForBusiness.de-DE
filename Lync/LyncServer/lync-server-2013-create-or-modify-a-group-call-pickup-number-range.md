---
title: 'Lync Server 2013: Erstellen oder Ändern eines Nummernbereichs für eine Gruppenanruf Abholung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d215fe6959b169ec5f092757174d105a75a5402a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="15a17-102">Erstellen oder Ändern eines Nummernbereichs für die gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a17-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15a17-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="15a17-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="15a17-104">Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahme Gruppe in der Orbit-Tabelle für das Parken von Anrufen zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="15a17-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15a17-105">Sie müssen lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Abhol Nummernbereichen in der Orbit-Tabelle für das Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="15a17-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="15a17-106">Gruppenanruf-Pickup-Nummernbereiche sind in lync Server-Systemsteuerung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="15a17-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15a17-107">Dem Nummernbereich für die Anrufannahme Gruppe muss ein GroupPickup-Typ zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="15a17-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="15a17-108">Benutzer sind für die gruppenanrufannahme nur aktiviert, wenn die Gruppennummer, der Sie zugeordnet sind, dem Typ GroupPickup entspricht.</span><span class="sxs-lookup"><span data-stu-id="15a17-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="15a17-109">Die Nummernbereiche der Anrufannahme Gruppe müssen den folgenden Regeln entsprechen:</span><span class="sxs-lookup"><span data-stu-id="15a17-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="15a17-110">Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="15a17-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="15a17-111">Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="15a17-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="15a17-112">Der Nummernbereich muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="15a17-112">The number range must be unique.</span></span> <span data-ttu-id="15a17-113">Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</span><span class="sxs-lookup"><span data-stu-id="15a17-113">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="15a17-114">Wenn der Nummernbereich mit dem Zeichen \* oder \#beginnt, muss der Bereich größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="15a17-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="15a17-115">Gültige Werte: muss mit der Zeichenfolge für reguläre\[\\\*|\#\]Ausdrücke\[ übereinstimmen (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="15a17-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="15a17-116">Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder \# mit dem Zeichen oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf nicht NULL sein).</span><span class="sxs-lookup"><span data-stu-id="15a17-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="15a17-117">Wenn das erste Zeichen oder \* \#ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein).</span><span class="sxs-lookup"><span data-stu-id="15a17-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="15a17-118">Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (Beispiels\#Weise "6000"\*, "92000"\*, "95551212" und "915551212").</span><span class="sxs-lookup"><span data-stu-id="15a17-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="15a17-119">Wenn das erste Zeichen nicht \* oder \#ist, muss das erste Zeichen eine Zahl 1 bis 9 (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl 0 bis 9 (beispielsweise "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="15a17-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="15a17-120">So erstellen oder ändern Sie einen Gruppenbereich für Anruf Pickups</span><span class="sxs-lookup"><span data-stu-id="15a17-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="15a17-121">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15a17-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="15a17-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="15a17-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15a17-123">Verwenden Sie **New-CsCallParkOrbit** , um einen neuen Bereich von Nummern für die Anrufannahme Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15a17-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="15a17-124">Verwenden Sie die **Einstellung CsCallParkOrbit** , um einen vorhandenen Bereich von Anrufannahme Nummern zu ändern.</span><span class="sxs-lookup"><span data-stu-id="15a17-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="15a17-125">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="15a17-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="15a17-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15a17-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="15a17-127">Im folgenden Beispiel wird gezeigt, wie Sie einen Nummernbereich von Orbits für das Parken von Anrufen zum Aufrufen von Abhol Gruppen ändern.</span><span class="sxs-lookup"><span data-stu-id="15a17-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15a17-128">Verwenden Sie dieses Cmdlet, um den dem Nummernbereich zugewiesenen Typ nur dann zu ändern, wenn Sie anfänglich den falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15a17-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="15a17-129">Wenn Sie den Nummernbereich von CallPark zu GroupPickup oder umgekehrt ändern und der Nummernbereich bereits verwendet wird, wird entweder die Anrufannahme oder die gruppenanrufannahme für diesen Nummernbereich beendet.</span><span class="sxs-lookup"><span data-stu-id="15a17-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="15a17-130">Wenn Sie beispielsweise einen Nummernbereich von CallPark in GroupPick ändern, kann der Anwendung zum Parken von Anrufen diesen Bereich von Umlaufbahnen nicht mehr zum Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="15a17-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15a17-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15a17-131">See Also</span></span>


[<span data-ttu-id="15a17-132">Löschen eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a17-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="15a17-133">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="15a17-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="15a17-134">Gruppe-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="15a17-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

