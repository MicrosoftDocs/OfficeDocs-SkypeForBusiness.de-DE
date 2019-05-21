---
title: Erstellen oder Ändern eines Umlauf Bereichs für einen Anruf Park in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Erstellen oder ändern Sie in Skype for Business Server Enterprise-VoIP eine Tabelle des Umlauf Bereichs des Anruf Parks.
ms.openlocfilehash: 77be47597e5bbb674719ac2b3192efdf4217a3dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286263"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="73a1c-103">Erstellen oder Ändern eines Umlauf Bereichs für einen Anruf Park in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73a1c-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="73a1c-104">Erstellen oder ändern Sie in Skype for Business Server Enterprise-VoIP eine Tabelle des Umlauf Bereichs des Anruf Parks.</span><span class="sxs-lookup"><span data-stu-id="73a1c-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="73a1c-105">Call Park verwendet Umlaufbahnen für Park Anrufe.</span><span class="sxs-lookup"><span data-stu-id="73a1c-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="73a1c-106">Bevor Benutzer Anrufe parken und abrufen können, müssen Sie die Umlaufbahn Tabelle des Anruf Parks konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="73a1c-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="73a1c-107">Sie müssen die Bereiche der Durchwahlnummern (Orbits) angeben, die Ihre Organisation für Park Anrufe reserviert, und den Arbeitsplan für diese Bereiche definieren, indem Sie angeben, welcher Anruf Park Pool für jeden Bereich zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="73a1c-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="73a1c-108">Wenn Sie Umlaufbahn Bereiche definieren, besteht das Ziel darin, genügend Umlaufbahnen zu haben, damit eine Umlaufbahn nicht zu schnell wieder verwendet wird, aber nicht so viele Umlaufbahnen, dass Sie die Anzahl der für Benutzer oder andere Dienste verfügbaren Erweiterungen einschränken.</span><span class="sxs-lookup"><span data-stu-id="73a1c-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="73a1c-109">Sie können für jeden Skype for Business Server-Pool, in dem die Park-Anwendung bereitgestellt wird, mehrere orbitbereiche für den Anruf Bereich erstellen.</span><span class="sxs-lookup"><span data-stu-id="73a1c-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="73a1c-110">Jeder Orbit-Bereich für das Parken von Anrufen muss einen global eindeutigen Namen und einen eindeutigen Satz von Erweiterungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="73a1c-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73a1c-p102">Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="73a1c-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="73a1c-114">Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).</span><span class="sxs-lookup"><span data-stu-id="73a1c-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="73a1c-115">Das Zuweisen von Direktwahlnummern (DID) als Orbit-Nummern in der Orbit-Tabelle des Anruf Parks wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73a1c-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="73a1c-116">Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="73a1c-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="73a1c-117">So verwenden Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern eines Nummernbereichs für Park Anrufe</span><span class="sxs-lookup"><span data-stu-id="73a1c-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="73a1c-p103">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="73a1c-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="73a1c-120">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73a1c-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="73a1c-121">Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.</span><span class="sxs-lookup"><span data-stu-id="73a1c-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="73a1c-122">Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="73a1c-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="73a1c-p104">Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.</span><span class="sxs-lookup"><span data-stu-id="73a1c-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="73a1c-125">Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="73a1c-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="73a1c-p105">Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig in das Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="73a1c-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="73a1c-128">Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="73a1c-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="73a1c-129">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="73a1c-129">Be aware:</span></span>

   - <span data-ttu-id="73a1c-130">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="73a1c-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="73a1c-131">Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="73a1c-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="73a1c-p107">Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</span><span class="sxs-lookup"><span data-stu-id="73a1c-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="73a1c-134">Wenn der Umlaufbahn Bereich mit dem Zeichen \* oder # beginnt, muss der Bereich größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="73a1c-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="73a1c-135">Gültige Werte: muss mit der Zeichenfolge des regulären Ausdrucks\\übereinstimmen ([\* | #] ? [1{0,7}-9] \d) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="73a1c-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="73a1c-136">Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine NULL sein).</span><span class="sxs-lookup"><span data-stu-id="73a1c-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="73a1c-137">Wenn das erste Zeichen oder \* # ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein).</span><span class="sxs-lookup"><span data-stu-id="73a1c-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="73a1c-138">Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise "#6000"\*, "92000"\*, "95551212" und "915551212").</span><span class="sxs-lookup"><span data-stu-id="73a1c-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="73a1c-139">Wenn das erste Zeichen nicht \* oder # ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, die jeweils eine Zahl von 0 bis 9 aufweisen (beispielsweise "915551212"; "41212"; "300").</span><span class="sxs-lookup"><span data-stu-id="73a1c-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="73a1c-p109">Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer „7000000“ und der Endnummer „8000000“ als Startnummer beispielsweise „7000000“ und als Endnummer „7000100“ an.</span><span class="sxs-lookup"><span data-stu-id="73a1c-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="73a1c-143">Klicken Sie in **FQDN des Zielservers**auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die Dienst-ID des Anwendungsdiensts, der die Anwendung für den Anruf Park hostet.</span><span class="sxs-lookup"><span data-stu-id="73a1c-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="73a1c-144">Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="73a1c-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="73a1c-145">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="73a1c-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="73a1c-146">So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern eines Nummernbereichs für Park Anrufe</span><span class="sxs-lookup"><span data-stu-id="73a1c-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="73a1c-147">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von **Setup Berechtigungen**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73a1c-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="73a1c-148">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="73a1c-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="73a1c-149">Mit **New-CsCallParkOrbit** können Sie einen neuen Orbitnummernbereich erstellen.</span><span class="sxs-lookup"><span data-stu-id="73a1c-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="73a1c-150">Mit **Set-CsCallParkOrbit** können Sie einen bestehenden Orbitnummernbereich bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="73a1c-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="73a1c-151">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="73a1c-151">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="73a1c-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73a1c-152">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="73a1c-153">Mit dem folgenden Befehl wird das Bearbeiten der Nummern in einem bestehenden Orbitbereich veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="73a1c-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="73a1c-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73a1c-154">See also</span></span>

[<span data-ttu-id="73a1c-155">Neu – CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="73a1c-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="73a1c-156">Satz-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="73a1c-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="73a1c-157">Löschen eines Umlauf Bereichs für einen Anruf Park</span><span class="sxs-lookup"><span data-stu-id="73a1c-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
