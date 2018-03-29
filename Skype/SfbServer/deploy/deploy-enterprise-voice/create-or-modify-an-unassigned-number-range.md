---
title: Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Skype for Business Server 2015
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Erstellen Sie, ändern Sie oder löschen Sie nicht zugewiesener Nummernbereiche für ansageanwendung in Skype für Business Server Enterprise-VoIP. Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.
ms.openlocfilehash: e4a62072eeffd1cfe8d1cb81fceeb4e52cc68199
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server-2015"></a><span data-ttu-id="bdc6d-104">Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bdc6d-104">Create or modify an unassigned number range in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bdc6d-105">Erstellen Sie, ändern Sie oder löschen Sie nicht zugewiesener Nummernbereiche für ansageanwendung in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="bdc6d-106">Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="bdc6d-107">Skype für Business Server können Sie sagen, was geschieht, um eingehende Anrufe an externe Telefonnummern, die für Ihre Organisation gültig sind, aber nicht für einen Benutzer oder ein Telefon zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="bdc6d-108">Zum Abwickeln solcher Anrufe richten Sie eine Tabelle mit nicht zugewiesenen Nummern ein.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="bdc6d-109">Die Tabelle können die Anrufe an eine ankündigungsanwendung oder mit einem Exchange UM-Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="bdc6d-p104">Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr dann eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="bdc6d-116">Konfigurieren von nicht zugewiesenen Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="bdc6d-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="bdc6d-117">Verwenden Sie eines der folgenden Verfahren zum Konfigurieren nicht zugewiesener Nummernbereiche für die Ankündigung an.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bdc6d-118">Bevor Sie den Tabelle mit nicht zugewiesenen Nummern konfigurieren, muss Ihr System müssen bereits Ansagen definiert oder eine automatische Telefonzentrale von Exchange Unified Messaging (UM) eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="bdc6d-119">Wenn Sie angerufen werden eine nicht zugewiesene Nummer, Skype für Business Server durchsucht den Tabelle nicht zugewiesenen Nummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="bdc6d-120">Sie sollten also als letzte Lösungsmöglichkeit eine Aktion definieren, die für den letzten Bereich in der Tabelle ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="bdc6d-121">Mit der Skype Business Server-Systemsteuerung konfigurieren nicht zugewiesener Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="bdc6d-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="bdc6d-122">Melden Sie sich an dem Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder csadministrator an.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bdc6d-123">Weitere Informationen hierzu finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bdc6d-124">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bdc6d-125">Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und klicken Sie dann auf **Nicht zugewiesene Nummer**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="bdc6d-126">Führen Sie auf der Seite **Nicht zugewiesene Nummer** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="bdc6d-p107">Wenn Sie einen neuen Nummernbereich erstellen möchten, klicken Sie auf **Neu**. Geben Sie unter **Name** den Namen für diesen Nummernbereich ein.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bdc6d-129">Nachdem Sie den neuen Bereich nicht zugewiesener Nummern per Commit in die Datenbank übernommen haben, können Sie diesen Namen nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="bdc6d-p108">Wenn Sie einen vorhandenen Nummernbereich ändern möchten, geben Sie im Suchfeld den gesamten Namen oder einen Teil des Namens für den Nummernbereich ein. Klicken Sie in der Ergebnisliste der Nummernbereiche auf den gewünschten Namen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bdc6d-132">Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="bdc6d-133">Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="bdc6d-134">Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="bdc6d-135">Die Anzahl muss mit den regulären Ausdruck übereinstimmen (tel:) ? (\+) [1-9] ? \d {0,17} (; Ext = [1-9] \d {0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="bdc6d-136">Dies bedeutet, dass die Anzahl beginnt mit der Zeichenfolge tel: (Wenn Sie diese Zeichenfolge nicht angeben, es wird automatisch hinzugefügt werden für Sie), ein Pluszeichen (+) sowie ein Zahl von 1 bis 9.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="bdc6d-137">Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format „;ext=“ plus der Durchwahlnummer.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="bdc6d-138">Führen Sie im Abschnitt **Ansagedienst** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="bdc6d-139">Klicken Sie auf **Ansage**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="bdc6d-140">Klicken Sie auf **Exchange UM**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="bdc6d-141">Wenn Sie im vorherigen Schritt auf **Ansage** geklickt haben, führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="bdc6d-142">a.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-142">a.</span></span> <span data-ttu-id="bdc6d-143">Klicken Sie unter **FQDN des Zielservers**klicken Sie auf **auswählen**, klicken Sie auf die Dienst-ID des Anwendungsdiensts, der die ankündigungsanwendung ausgeführt, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern behandelt werden sollen wird, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="bdc6d-144">b.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-144">b.</span></span> <span data-ttu-id="bdc6d-145">Klicken Sie im Abschnitt **Ansage** auf die Ansage, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="bdc6d-146">Wenn Sie im vorherigen Schritt auf **Exchange UM** geklickt haben, klicken Sie unter **Nummer der automatischen Telefonzentrale** auf **Auswählen**, klicken Sie auf die für diesen Bereich nicht zugewiesener Nummern zu verwendende Telefonnummer und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="bdc6d-147">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="bdc6d-p112">Stellen Sie sicher, dass die Bereiche nicht zugewiesener Nummern auf der Seite **Nicht zugewiesene Nummer** in der gewünschten Reihenfolge angezeigt werden. Wenn Sie die Position eines Bereichs in der Tabelle ändern möchten, klicken Sie auf einen oder mehrere aufeinanderfolgende Namen in der Liste der Bereiche und klicken Sie anschließend auf den Aufwärts- oder Abwärtspfeil.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bdc6d-150">Skype für Business Server sucht den Tabelle nicht zugewiesenen Nummern von oben nach unten und verwendet den ersten Bereich, der nicht zugewiesene Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="bdc6d-151">Wenn sich Bereiche überlappen und auf einen Bereich als letzte Aktion zurückgegriffen werden soll, stellen Sie sicher, dass sich dieser Bereich ganz unten in der Liste befindet.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="bdc6d-152">Wenn Sie die Bereiche nicht zugewiesener Nummern in der gewünschten Reihenfolge angeordnet haben, klicken Sie auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="bdc6d-153">Skype für Business Server-Verwaltungsshell verwenden, zum Konfigurieren nicht zugewiesener Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="bdc6d-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="bdc6d-154">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bdc6d-155">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bdc6d-156">Verwenden Sie **New-CsUnassignedNumber** , um einen neuen Bereichs nicht zugewiesener Nummern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="bdc6d-157">Verwenden Sie **Set-CsUnassignedNumber** , um einen vorhandenen nicht zugewiesenen Nummern ändern.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bdc6d-p115">Wenn sich Bereiche überlappen und die Bereiche in einer bestimmten Reihenfolge angewendet werden sollen, fügen Sie den Parameter „Priority“ ein. Daraufhin wird der Bereich mit der höchsten Priorität für den Anruf angewendet.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-p115">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span> 
  
    <span data-ttu-id="bdc6d-160">Führen Sie in der Befehlszeile eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-160">At the command line, do one of the following:</span></span>
    
     - <span data-ttu-id="bdc6d-161">Führen Sie zum Erstellen eines Nummernbereichs für einen Ankündigungsdienst Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-161">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="bdc6d-162">Oder führen Sie zum Erstellen eines Nummernbereichs für die automatische Exchange UM-Telefonzentrale Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-162">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="bdc6d-163">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-163">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="bdc6d-164">Oder</span><span class="sxs-lookup"><span data-stu-id="bdc6d-164">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

    <span data-ttu-id="bdc6d-165">Im folgenden Beispiel wird veranschaulicht, wie Sie die Nummern in einem vorhandenen Bereich nicht zugewiesener Nummern ändern:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-165">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="bdc6d-166">Löschen eines Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="bdc6d-166">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="bdc6d-167">Skype Business Server-Systemsteuerung verwenden, um einen nicht zugewiesenen Nummern zu löschen</span><span class="sxs-lookup"><span data-stu-id="bdc6d-167">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="bdc6d-168">Melden Sie sich an dem Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder csadministrator an.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-168">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bdc6d-169">Weitere Informationen hierzu finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-169">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bdc6d-170">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bdc6d-171">Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und klicken Sie dann auf **Nicht zugewiesene Nummer**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-171">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="bdc6d-172">Geben Sie auf der Seite **Nicht zugewiesene Nummer** im Suchfeld Teile oder den vollständigen Namen des Bereichs nicht zugewiesener Nummern ein, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-172">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="bdc6d-173">Klicken Sie in der resultierenden Liste der Nummernbereiche auf den Namen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-173">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="bdc6d-174">Klicken Sie auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-174">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="bdc6d-175">Skype für Business Server-Verwaltungsshell verwenden, um einen nicht zugewiesenen Nummern zu löschen</span><span class="sxs-lookup"><span data-stu-id="bdc6d-175">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="bdc6d-176">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-176">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bdc6d-177">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bdc6d-177">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bdc6d-178">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-178">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="bdc6d-179">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bdc6d-179">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="bdc6d-180">Ausführliche Informationen zu weiteren Optionen finden Sie unter [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bdc6d-180">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bdc6d-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdc6d-181">See also</span></span>

#### 

[<span data-ttu-id="bdc6d-182">Neue CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="bdc6d-182">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="bdc6d-183">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="bdc6d-183">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="bdc6d-184">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="bdc6d-184">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)

