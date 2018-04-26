---
title: Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a><span data-ttu-id="d66bb-103">Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="d66bb-103">Create or modify a Call Park orbit range in Skype for Business 2015</span></span>
 
<span data-ttu-id="d66bb-104">Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="d66bb-104">Create or modify a Call Park orbit range in Skype for Business 2015</span></span>
  
<span data-ttu-id="d66bb-105">Call Park uses orbits for parking calls.</span><span class="sxs-lookup"><span data-stu-id="d66bb-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="d66bb-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span><span class="sxs-lookup"><span data-stu-id="d66bb-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="d66bb-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span><span class="sxs-lookup"><span data-stu-id="d66bb-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="d66bb-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span><span class="sxs-lookup"><span data-stu-id="d66bb-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="d66bb-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span><span class="sxs-lookup"><span data-stu-id="d66bb-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="d66bb-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span><span class="sxs-lookup"><span data-stu-id="d66bb-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d66bb-p102">Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="d66bb-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span> 
  
<span data-ttu-id="d66bb-114">Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).</span><span class="sxs-lookup"><span data-stu-id="d66bb-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d66bb-115">Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d66bb-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span> 
  
<span data-ttu-id="d66bb-116">Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d66bb-116">Use one of the following procedures to create or modify a call park orbit range.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="d66bb-117">So erstellen oder bearbeiten Sie mit  einen Nummernbereich für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="d66bb-117">To use  to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="d66bb-118">Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle Cs-VoiceAdministrator, Cs-ServerAdministrator oder CsAdministrator an.</span><span class="sxs-lookup"><span data-stu-id="d66bb-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-VoiceAdministrator, Cs-ServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d66bb-119">For details, see **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="d66bb-119">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="d66bb-120">Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="d66bb-120">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d66bb-121">Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.</span><span class="sxs-lookup"><span data-stu-id="d66bb-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>
    
4. <span data-ttu-id="d66bb-122">Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d66bb-122">On the **Call Park** page, do one of the following:</span></span>
    
  - <span data-ttu-id="d66bb-p104">Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.</span><span class="sxs-lookup"><span data-stu-id="d66bb-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d66bb-125">Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="d66bb-125">After you commit the orbit range to the database, you cannot change this name.</span></span> 
  
  - <span data-ttu-id="d66bb-p105">Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig in das Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d66bb-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d66bb-128">Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="d66bb-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="d66bb-129">Be aware:</span><span class="sxs-lookup"><span data-stu-id="d66bb-129">Be aware:</span></span>
    
   - <span data-ttu-id="d66bb-130">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="d66bb-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="d66bb-131">Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="d66bb-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
   - <span data-ttu-id="d66bb-p107">Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</span><span class="sxs-lookup"><span data-stu-id="d66bb-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>
    
   - <span data-ttu-id="d66bb-134">Wenn der Orbitbereich mit dem Zeichen \* oder # beginnt, muss der Bereich größer als 100 sein.</span><span class="sxs-lookup"><span data-stu-id="d66bb-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>
    
   - <span data-ttu-id="d66bb-135">Gültige Werte müssen mit dem regulären Ausdruck [\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8} übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d66bb-135">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="d66bb-136">Dies bedeutet, dass es sich bei dem Wert um eine Zeichenfolge handeln muss, die entweder mit dem Zeichen \* oder # oder einer Zahl zwischen 1 und 9 beginnt (das erste Zeichen darf keine Null sein).</span><span class="sxs-lookup"><span data-stu-id="d66bb-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="d66bb-137">Wenn das erste Zeichen ein Sternchen (\*) oder ein Rautenzeichen (#) ist, muss das folgende Zeichen eine Zahl zwischen 1 und 9 sein (keine Null).</span><span class="sxs-lookup"><span data-stu-id="d66bb-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="d66bb-138">Bei den nachfolgenden Zeichen kann es sich um eine beliebige Zahl zwischen 0 und 9 und zusätzlich sieben Zeichen handeln (Beispiel: „#6000“, „*92000“, „*95551212“ und „915551212“).</span><span class="sxs-lookup"><span data-stu-id="d66bb-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "*95551212", and "915551212").</span></span> <span data-ttu-id="d66bb-139">Wenn es sich bei dem ersten Zeichen nicht um \* oder # handelt, muss das erste Zeichen eine Zahl zwischen 1 und 9 sein (keine Null), gefolgt von bis zu acht Zeichen, bei denen es sich jeweils um eine Zahl zwischen 0 und 9 handeln muss (z. B. „915551212“, „41212“ oder „300“).</span><span class="sxs-lookup"><span data-stu-id="d66bb-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
   - <span data-ttu-id="d66bb-p109">Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer „7000000“ und der Endnummer „8000000“ als Startnummer beispielsweise „7000000“ und als Endnummer „7000100“ an.</span><span class="sxs-lookup"><span data-stu-id="d66bb-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
6. <span data-ttu-id="d66bb-143">Klicken Sie in FQDN des Zielservers auf den vollqualifizierten Domänennamen oder die Dienst-ID des Anwendungsdiensts, der die  hostet.</span><span class="sxs-lookup"><span data-stu-id="d66bb-143">In FQDN of destination server, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the .</span></span> <span data-ttu-id="d66bb-144">Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d66bb-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>
    
7. <span data-ttu-id="d66bb-145">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d66bb-145">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="d66bb-146">So erstellen oder bearbeiten Sie mit  einen Nummernbereich für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="d66bb-146">To use  to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="d66bb-147">Melden Sie sich auf dem Computer, auf dem die  installiert ist, als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter .</span><span class="sxs-lookup"><span data-stu-id="d66bb-147">Log on to the computer where  is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in .</span></span>
    
2. <span data-ttu-id="d66bb-148">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d66bb-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d66bb-149">Mit **** können Sie einen neuen Orbitnummernbereich erstellen.</span><span class="sxs-lookup"><span data-stu-id="d66bb-149">Use **** to create a new range of orbit numbers.</span></span> <span data-ttu-id="d66bb-150">Mit **** können Sie einen bestehenden Orbitnummernbereich bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d66bb-150">Use **** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="d66bb-151">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d66bb-151">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="d66bb-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d66bb-152">For example:</span></span>
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="d66bb-153">Mit dem folgenden Befehl wird das Bearbeiten der Nummern in einem bestehenden Orbitbereich veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="d66bb-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="d66bb-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d66bb-154">See also</span></span>

#### 

[<span data-ttu-id="d66bb-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d66bb-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="d66bb-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d66bb-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="d66bb-157">Delete a Call Park Orbit Range</span><span class="sxs-lookup"><span data-stu-id="d66bb-157">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

