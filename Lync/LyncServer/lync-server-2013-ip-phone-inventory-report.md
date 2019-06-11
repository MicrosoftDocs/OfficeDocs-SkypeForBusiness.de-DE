---
title: 'Lync Server 2013: IP Phone-Inventurbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335b74b742f3b32437892e27f7db3ecadc5f3b3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="b58ae-102">Bericht zum IP Phone-Inventar in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b58ae-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b58ae-103">_**Letztes Änderungsdatum des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="b58ae-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="b58ae-p101">Der Bericht für den IP-Telefonbestand enthält Informationen zu den IP-Telefonen, die derzeit in der Organisation verwendet werden. Er umfasst eine detaillierte Liste der IP-Telefone, die während des angegebenen Berichtszeitraums tatsächlich verwendet wurden. Mithilfe dieses Berichts können Administratoren unter anderem Informationen dazu erhalten, ob alte oder veraltete Telefone vorhanden sind, die ausgetauscht werden sollten. Zudem können Administratoren darauf hingewiesen werden, dass in der Organisation teure Telefone existieren, die kaum verwendet werden. Solche Informationen können außerordentlich wertvoll sein, wenn es darum geht, neue Telefone zu kaufen oder vorhandene Telefone neu zu verteilen. (Ein Benutzer, der sein teures Telefon selten nutzt, kann beispielsweise gebeten werden, sein Telefon mit einem Benutzer zu tauschen, der sein Telefon häufiger verwendet.)</span><span class="sxs-lookup"><span data-stu-id="b58ae-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="b58ae-109">Es sollte beachtet werden, dass dieser Bericht einige Einschränkungen hat, wenn er als echter Inventarbericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b58ae-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="b58ae-110">Zum einen listet der Bericht IP Phone einfach alle Telefone auf, die sich während des angegebenen Zeitraums bei lync Server angemeldet haben, sortiert nach der letzten Anmeldezeit.</span><span class="sxs-lookup"><span data-stu-id="b58ae-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="b58ae-111">Wenn sich ein Telefon während des angegebenen Zeitraums nicht anmeldet, wird es im Inventurbericht nicht aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b58ae-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="b58ae-112">Dazu gehören Telefone, die sich vor dem Start des Zeitraums anmeldeten und noch während des angegebenen Zeitintervalls angemeldet waren.</span><span class="sxs-lookup"><span data-stu-id="b58ae-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="b58ae-113">Angenommen, Sie möchten die gesamte Telefon Inventur für Juli, 2012, sehen.</span><span class="sxs-lookup"><span data-stu-id="b58ae-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="b58ae-114">Angenommen, dass mehrere Telefone am lync Server am 30. Juni 2012 angemeldet und noch am 1. Juli angemeldet waren.</span><span class="sxs-lookup"><span data-stu-id="b58ae-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="b58ae-115">Diese Telefone werden im Inventarbericht für den 1. Juli nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b58ae-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="b58ae-116">Beachten Sie auch, dass der Inventurbericht Telefone enthalten kann, die in Ihrer Organisation nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b58ae-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="b58ae-117">Nehmen wir beispielsweise an, dass eine Reihe von Fabrikam-Telefonen am System am 1. Juli 2012 angemeldet sind. fünf Tage später hat Ihre Organisation alle diese Fabrikam-Telefone entfernt und durch ein neues Contoso-Modell ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b58ae-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="b58ae-118">Die Fabrikam-Telefone werden nach wie vor im Bericht "Inventar" angezeigt, nur weil Sie sich im Laufe des Monats Juli am System angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="b58ae-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="b58ae-p104">Darüber hinaus werden im Bericht für den IP-Telefonbestand keine zusammenfassenden Gesamtzahlen für die verschiedenen Telefontypen angegeben. Nehmen wir beispielsweise an, Sie besitzen 105 Telefone vom Typ Polycom CX600. Aus dem Bericht wird nicht ersichtlich, dass Sie 105 solcher Telefone haben. Stattdessen sehen Sie lediglich 105 separate Einträge für das Modell Polycom Cx600. Die einzige Möglichkeit, um herauszufinden, dass für das Modell Polycom Cx600 105 Einträge vorliegen, besteht darin, diese Einträge manuell zu zählen.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b58ae-123">Alternativ dazu können Sie die Daten exportieren und die Zählung in Microsoft Excel oder Windows PowerShell vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b58ae-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="b58ae-124">Zugreifen auf den Bericht für den IP-Telefonbestand</span><span class="sxs-lookup"><span data-stu-id="b58ae-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="b58ae-p105">Der Zugriff auf den Bericht für den IP-Telefonbestand erfolgt über die Startseite der Überwachungsberichte. Wenn Sie auf die Metrik „Benutzer-URI“ klicken, können Sie auf den Benutzeraktivitätsbericht für den jeweiligen Benutzer zugreifen. Wenn Sie für einen Peer-to-Peer-Anruf auf die Metrik „Letzte Aktivität“ klicken, gelangen Sie zum Detailbericht über Peer-to-Peer-Sitzungen. Wenn Sie für eine Konferenz auf dieselbe Metrik klicken, gelangen Sie zum detaillierten Konferenzbericht.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="b58ae-128">Optimale Nutzung des Berichts für den IP-Telefonbestand</span><span class="sxs-lookup"><span data-stu-id="b58ae-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="b58ae-129">Wenn Sie nur an Nutzungsinformationen für eine bestimmte Art von Telefon interessiert sind (beispielsweise: "wie oft verwenden Benutzer ein Polycom CX600-Telefon?"), können Sie diese Informationen direkt aus dem Inventarbericht für IP-Telefone abrufen, indem Sie für diese bestimmte Art von Telefon filtern.</span><span class="sxs-lookup"><span data-stu-id="b58ae-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="b58ae-130">Wenn Sie jedoch Zusammenfassungsinformationen für alle ihre Smartphones (wie viele Personen eine Polycom CX600 verwenden, wie viele eine LG-Nortel-IP8540 usw. verwenden) verwenden möchten, müssen Sie die Daten exportieren und eine andere Anwendung (wie Windows PowerShell) verwenden, um diese Art von Analyse.</span><span class="sxs-lookup"><span data-stu-id="b58ae-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="b58ae-131">Nehmen Sie beispielsweise an, dass Sie die Daten in eine Datei mit Komma getrennten Werten (\\C\\:\_Data\_IP\_Phone Inventory Report. CSV) exportieren.</span><span class="sxs-lookup"><span data-stu-id="b58ae-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="b58ae-132">In diesem Fall können Sie mit diesen beiden Befehlen Zusammenfassungsdaten für alle Ihre Telefone bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="b58ae-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="b58ae-133">Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:</span><span class="sxs-lookup"><span data-stu-id="b58ae-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="b58ae-134">Gleichermaßen erhalten Sie mithilfe dieser beiden Befehle Informationen dazu, welche Telefone zwar beim System angemeldet, aber tatsächlich nie zum Telefonieren genutzt wurden (der Wert der Metrik „Letzte Aktivität“ ist leer und gibt somit an, dass es keine letzte Aktivität gab):</span><span class="sxs-lookup"><span data-stu-id="b58ae-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="b58ae-135">Dabei werden für alle nicht verwendeten Telefone Daten zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="b58ae-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="b58ae-136">Eine weitere interessante Möglichkeit zur Verwendung des Inventarberichts für IP-Telefone: Wenn Sie über die Mac-Adresse eines IP-Telefons verfügen, können Sie den Benutzer, der das Telefon zuletzt verwendet hat, einfach über die Adresse in das Textfeld Mac-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="b58ae-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="b58ae-137">Der Bericht IP Phone Inventory meldet dann (unter anderem) die SIP-Adresse des Benutzers, der sich zuletzt mit diesem Telefon angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="b58ae-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="b58ae-138">Sie können auch eine SIP-Adresse des Benutzers (im Feld Benutzer-URI-Präfix) eingeben, um alle Telefone festzustellen, die von diesem Benutzer verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="b58ae-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b58ae-139">Filter</span><span class="sxs-lookup"><span data-stu-id="b58ae-139">Filters</span></span>

<span data-ttu-id="b58ae-p108">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der IP-Telefonbestand ermöglicht Ihnen beispielsweise das Anzeigen von Telefonen eines bestimmten Herstellers oder sogar einer bestimmten Version dieser Telefone. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b58ae-144">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht für den IP-Telefonbestand verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b58ae-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="b58ae-145">Bericht für den IP-Telefonbestand - Filter</span><span class="sxs-lookup"><span data-stu-id="b58ae-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b58ae-146">Name</span><span class="sxs-lookup"><span data-stu-id="b58ae-146">Name</span></span></th>
<th><span data-ttu-id="b58ae-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b58ae-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-148"><strong>Von</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b58ae-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b58ae-151">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="b58ae-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b58ae-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b58ae-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b58ae-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b58ae-154">7/7/2012</span></span></p>
<p><span data-ttu-id="b58ae-155">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b58ae-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b58ae-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b58ae-156">7/3/2012</span></span></p>
<p><span data-ttu-id="b58ae-157">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b58ae-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-158"><strong>Bis</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="b58ae-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b58ae-161">7/7/2012 1:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="b58ae-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b58ae-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="b58ae-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b58ae-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b58ae-164">7/7/2012</span></span></p>
<p><span data-ttu-id="b58ae-165">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="b58ae-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b58ae-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b58ae-166">7/3/2012</span></span></p>
<p><span data-ttu-id="b58ae-167">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="b58ae-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-168"><strong>Hersteller</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-p113">Name des Herstellers des IP-Telefons. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-171"><strong>Hardwareversion</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-172">Versionsnummer des IP-Telefons; mit den Filtern für den Hersteller und die Hardwareversion können Sie einen bestimmten Telefontyp eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b58ae-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="b58ae-173">Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b58ae-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-174"><strong>Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-p115">ID für die vom IP-Telefon verwendete Software. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-177"><strong>MAC-Adresse</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-p116">Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse (Media Access Control) wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="b58ae-p117">Zum Suchen nach Datensätzen mit einer bestimmten MAC-Adresse geben Sie einfach diese Adresse ein, z. B.:</span><span class="sxs-lookup"><span data-stu-id="b58ae-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="b58ae-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="b58ae-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="b58ae-p118">Die Adresse muss vollständig eingegeben werden. Ein Teil einer Adresse (z. B. 00-08-5D) gibt keine Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-185"><strong>Letzte Aktivität vor (Tage)</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-186">Wählen Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="b58ae-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="b58ae-187">[Alle]</span><span class="sxs-lookup"><span data-stu-id="b58ae-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="b58ae-188">10</span><span class="sxs-lookup"><span data-stu-id="b58ae-188">10</span></span></p></li>
<li><p><span data-ttu-id="b58ae-189">20</span><span class="sxs-lookup"><span data-stu-id="b58ae-189">20</span></span></p></li>
<li><p><span data-ttu-id="b58ae-190">30</span><span class="sxs-lookup"><span data-stu-id="b58ae-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-191"><strong>Zuletzt abgemeldet vor (Tage):</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-192">Wählen Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="b58ae-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="b58ae-193">[Alle]</span><span class="sxs-lookup"><span data-stu-id="b58ae-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="b58ae-194">10</span><span class="sxs-lookup"><span data-stu-id="b58ae-194">10</span></span></p></li>
<li><p><span data-ttu-id="b58ae-195">20</span><span class="sxs-lookup"><span data-stu-id="b58ae-195">20</span></span></p></li>
<li><p><span data-ttu-id="b58ae-196">30</span><span class="sxs-lookup"><span data-stu-id="b58ae-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-197"><strong>Präfix des Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-198">SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="b58ae-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b58ae-199">Metriken</span><span class="sxs-lookup"><span data-stu-id="b58ae-199">Metrics</span></span>

<span data-ttu-id="b58ae-200">In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht für den IP-Telefonbestand angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b58ae-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="b58ae-201">Bericht für den IP-Telefonbestand - Metriken</span><span class="sxs-lookup"><span data-stu-id="b58ae-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b58ae-202">Name</span><span class="sxs-lookup"><span data-stu-id="b58ae-202">Name</span></span></th>
<th><span data-ttu-id="b58ae-203">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="b58ae-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b58ae-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b58ae-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-205"><strong>Hersteller</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-206">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-207">Name des Herstellers des IP-Telefons.</span><span class="sxs-lookup"><span data-stu-id="b58ae-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-208"><strong>Hardwareversion</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-209">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-210">Versionsnummer des IP-Telefons.</span><span class="sxs-lookup"><span data-stu-id="b58ae-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-211"><strong>MAC-Adresse</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-212">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-p119">Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</span><span class="sxs-lookup"><span data-stu-id="b58ae-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-215"><strong>Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-216">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-217">SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="b58ae-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-218"><strong>Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-219">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-220">ID für die vom IP-Telefon verwendete Software.</span><span class="sxs-lookup"><span data-stu-id="b58ae-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-221"><strong>Zuletzt angemeldet um:</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-222">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-223">Datum und Uhrzeit der letzten Anmeldung des IP-Telefons bei lync Server.</span><span class="sxs-lookup"><span data-stu-id="b58ae-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b58ae-224"><strong>Zuletzt abgemeldet um:</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-225">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-226">Datum und Uhrzeit, zu dem das IP-Telefon zuletzt von lync Server abgemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="b58ae-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b58ae-227"><strong>Letzte Aktivität</strong></span><span class="sxs-lookup"><span data-stu-id="b58ae-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="b58ae-228">Ja</span><span class="sxs-lookup"><span data-stu-id="b58ae-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="b58ae-229">Datum und Uhrzeit der letzten Verwendung des IP-Telefons.</span><span class="sxs-lookup"><span data-stu-id="b58ae-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

