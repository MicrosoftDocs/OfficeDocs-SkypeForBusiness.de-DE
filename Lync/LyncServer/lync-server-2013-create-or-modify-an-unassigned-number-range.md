---
title: 'Lync Server 2013: Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4409a0c5688d131b34c792230c992142dd4f9c51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514682"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="e3cd1-102">Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3cd1-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3cd1-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e3cd1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e3cd1-104">Verwenden Sie eines der folgenden Verfahren, um nicht zugewiesene Nummernbereiche für die Ankündigungsanwendung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e3cd1-105">Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine automatische Exchange Unified Messaging-Telefonzentrale (UM) eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e3cd1-106">So verwenden Sie lync Server-Systemsteuerung zum Konfigurieren nicht zugewiesener Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="e3cd1-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="e3cd1-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e3cd1-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e3cd1-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e3cd1-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3cd1-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e3cd1-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e3cd1-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen**, und klicken Sie dann auf **Nicht zugewiesene Nummer**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="e3cd1-112">Führen Sie auf der Seite **Nicht zugewiesene Nummer** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e3cd1-p103">Wenn Sie einen neuen Nummernbereich erstellen möchten, klicken Sie auf **Neu**. Geben Sie unter **Name** den Namen für diesen Nummernbereich ein.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-p103">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e3cd1-115">Nachdem Sie den neuen Bereich nicht zugewiesener Nummern per Commit in die Datenbank übernommen haben, können Sie diesen Namen nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="e3cd1-p104">Wenn Sie einen vorhandenen Nummernbereich ändern möchten, geben Sie im Suchfeld den gesamten Namen oder einen Teil des Namens für den Nummernbereich ein. Klicken Sie in der Ergebnisliste der Nummernbereiche auf den gewünschten Namen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-p104">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e3cd1-118">Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich ein, und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="e3cd1-119">Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e3cd1-120">Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen, und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e3cd1-121">Die Zahl muss mit dem regulären Ausdruck übereinstimmen (Tel:)? ( \+ )? [1-9] \d {0,17} (; ext = [1-9] \d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="e3cd1-122">Demnach kann die Nummer mit der Zeichenfolge "tel:" (wenn Sie diese Zeichenfolge nicht angeben, wird sie automatisch hinzugefügt) sowie einem Pluszeichen (+) und einer Zahl zwischen 1 und 9 beginnen.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="e3cd1-123">Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format ";ext=" plus der Durchwahlnummer.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="e3cd1-124">Führen Sie im Abschnitt **Ansagedienst** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="e3cd1-125">Klicken Sie auf **Ansage**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="e3cd1-126">Klicken Sie auf **Exchange UM**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="e3cd1-127">Wenn Sie im vorherigen Schritt auf **Ansage** geklickt haben, führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="e3cd1-128">Klicken Sie unter **FQDN des Zielservers** auf **Auswählen**, klicken Sie auf die Dienst-ID des Anwendungsdiensts, der die Ansageanwendung ausführt, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern verarbeitet, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="e3cd1-129">Klicken Sie im Abschnitt **Ansage** auf die Ansage, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="e3cd1-130">Wenn Sie im vorherigen Schritt auf **Exchange UM** geklickt haben, klicken Sie unter **Nummer der automatischen Telefonzentrale** auf **Auswählen**, klicken Sie auf die für diesen Bereich nicht zugewiesener Nummern zu verwendende Telefonnummer, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="e3cd1-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-131">Click **OK**.</span></span>

10. <span data-ttu-id="e3cd1-p106">Stellen Sie sicher, dass die Bereiche nicht zugewiesener Nummern auf der Seite **Nicht zugewiesene Nummer** in der gewünschten Reihenfolge angezeigt werden. Wenn Sie die Position eines Bereichs in der Tabelle ändern möchten, klicken Sie auf einen oder mehrere aufeinanderfolgende Namen in der Liste der Bereiche, und klicken Sie anschließend auf den Aufwärts- oder Abwärtspfeil.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-p106">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e3cd1-134">Lync Server durchsucht die Tabelle nicht zugewiesene Nummern von oben nach unten und verwendet den ersten Bereich, der mit der nicht zugewiesenen Zahl übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="e3cd1-135">Wenn sich Bereiche überlappen und auf einen Bereich als letzte Aktion zurückgegriffen werden soll, stellen Sie sicher, dass sich dieser Bereich ganz unten in der Liste befindet.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="e3cd1-136">Wenn Sie die Bereiche nicht zugewiesener Nummern in der gewünschten Reihenfolge angeordnet haben, klicken Sie auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e3cd1-137">So verwenden Sie Windows PowerShell zum Konfigurieren nicht zugewiesener Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="e3cd1-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="e3cd1-138">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e3cd1-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e3cd1-140">Verwenden Sie **New-CsUnassignedNumber**zum Erstellen eines neuen Bereichs nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="e3cd1-141">Verwenden Sie **Set-CsUnassignedNumber** zum Ändern eines vorhandenen Bereichs nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e3cd1-p109">Wenn sich Bereiche überlappen und die Bereiche in einer bestimmten Reihenfolge angewendet werden sollen, fügen Sie den Parameter "Priority" ein. Daraufhin wird der Bereich mit der höchsten Priorität für den Anruf angewendet.</span><span class="sxs-lookup"><span data-stu-id="e3cd1-p109">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="e3cd1-144">Führen Sie in der Befehlszeile eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="e3cd1-145">Führen Sie zum Erstellen eines Nummernbereichs für einen Ankündigungsdienst Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="e3cd1-146">Oder führen Sie zum Erstellen eines Nummernbereichs für die automatische Exchange UM-Telefonzentrale Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="e3cd1-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="e3cd1-148">Oder</span><span class="sxs-lookup"><span data-stu-id="e3cd1-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="e3cd1-149">Im folgenden Beispiel wird veranschaulicht, wie Sie die Nummern in einem vorhandenen Bereich nicht zugewiesener Nummern ändern:</span><span class="sxs-lookup"><span data-stu-id="e3cd1-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3cd1-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3cd1-150">See Also</span></span>


[<span data-ttu-id="e3cd1-151">Löschen eines Bereichs nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3cd1-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="e3cd1-152">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e3cd1-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="e3cd1-153">Gruppe-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e3cd1-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="e3cd1-154">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e3cd1-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

