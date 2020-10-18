---
title: 'Lync Server 2013: Inventurbericht über IP-Telefone'
description: 'Lync Server 2013: Inventurbericht über IP-Telefone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc05017775ad64e0e18f876215aa2c6b3882bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575021"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="8abf7-103">Inventurbericht über IP-Telefone in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8abf7-103">IP Phone Inventory Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8abf7-104">_**Letztes Änderungsstand des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="8abf7-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="8abf7-p101">Der Bericht für den IP-Telefonbestand enthält Informationen zu den IP-Telefonen, die derzeit in der Organisation verwendet werden. Er umfasst eine detaillierte Liste der IP-Telefone, die während des angegebenen Berichtszeitraums tatsächlich verwendet wurden. Mithilfe dieses Berichts können Administratoren unter anderem Informationen dazu erhalten, ob alte oder veraltete Telefone vorhanden sind, die ausgetauscht werden sollten. Zudem können Administratoren darauf hingewiesen werden, dass in der Organisation teure Telefone existieren, die kaum verwendet werden. Solche Informationen können außerordentlich wertvoll sein, wenn es darum geht, neue Telefone zu kaufen oder vorhandene Telefone neu zu verteilen. (Ein Benutzer, der sein teures Telefon selten nutzt, kann beispielsweise gebeten werden, sein Telefon mit einem Benutzer zu tauschen, der sein Telefon häufiger verwendet.)</span><span class="sxs-lookup"><span data-stu-id="8abf7-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="8abf7-110">Es sollte darauf hingewiesen werden, dass dieser Bericht einige Einschränkungen hat, wenn es darum geht, als echter Inventarbericht verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="8abf7-110">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="8abf7-111">Für eine Sache listet der IP-Telefon Bericht einfach alle Telefone auf, die sich bei lync Server während des angegebenen Zeitraums angemeldet haben, sortiert nach der letzten Anmeldezeit.</span><span class="sxs-lookup"><span data-stu-id="8abf7-111">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="8abf7-112">Wenn sich ein Telefon während des angegebenen Zeitraums nicht angemeldet hat, wird es nicht im Inventurbericht aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8abf7-112">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="8abf7-113">Dies umfasst Telefone, die vor dem Start des Zeitraums angemeldet waren und noch während des angegebenen Zeitintervalls angemeldet waren.</span><span class="sxs-lookup"><span data-stu-id="8abf7-113">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="8abf7-114">Nehmen wir beispielsweise an, Sie möchten sich den gesamten Telefon bestand für Juli 2012.</span><span class="sxs-lookup"><span data-stu-id="8abf7-114">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="8abf7-115">Nehmen wir an, dass mehrere Telefone, die am 30. Juni lync Server angemeldet sind, am 2012 und noch am 1. Juli angemeldet waren.</span><span class="sxs-lookup"><span data-stu-id="8abf7-115">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="8abf7-116">Diese Telefone werden nicht im Inventurbericht für den 1. Juli angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8abf7-116">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="8abf7-p103">Weiterhin muss beachtet werden, dass der Bestandsbericht Telefone einschließen kann, die in Ihrer Organisation nicht mehr verwendet werden. Angenommen, eine bestimmte Anzahl Telefone von Fabrikam wurde am 1. Juli 2012 beim System angemeldet. Fünf Tage später hat sich Ihre Organisation dazu entschlossen, diese Fabrikam-Telefone durch ein neueres Modell von Contoso auszutauschen. Die Fabrikam-Telefone werden jedoch weiterhin im "Bestandsbericht" aufgeführt, weil sie im Juli beim System angemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p103">It's also important to note that the inventory report could include phones that your organization no longer uses. For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model. The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="8abf7-p104">Darüber hinaus werden im Bericht für den IP-Telefonbestand keine zusammenfassenden Gesamtzahlen für die verschiedenen Telefontypen angegeben. Nehmen wir beispielsweise an, Sie besitzen 105 Telefone vom Typ Polycom CX600. Aus dem Bericht wird nicht ersichtlich, dass Sie 105 solcher Telefone haben. Stattdessen sehen Sie lediglich 105 separate Einträge für das Modell Polycom Cx600. Die einzige Möglichkeit, um herauszufinden, dass für das Modell Polycom Cx600 105 Einträge vorliegen, besteht darin, diese Einträge manuell zu zählen.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8abf7-124">Alternativ dazu können Sie die Daten exportieren und die Zählung in Microsoft Excel oder Windows PowerShell vornehmen.</span><span class="sxs-lookup"><span data-stu-id="8abf7-124">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="8abf7-125">Zugreifen auf den Bericht für den IP-Telefonbestand</span><span class="sxs-lookup"><span data-stu-id="8abf7-125">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="8abf7-p105">Der Zugriff auf den Bericht für den IP-Telefonbestand erfolgt über die Startseite der Überwachungsberichte. Wenn Sie auf die Metrik "Benutzer-URI" klicken, können Sie auf den Benutzeraktivitätsbericht für den jeweiligen Benutzer zugreifen. Wenn Sie für einen Peer-zu-Peer-Anruf auf die Metrik "Letzte Aktivität" klicken, gelangen Sie zum Detailbericht über Peer-zu-Peer-Sitzungen. Wenn Sie für eine Konferenz auf dieselbe Metrik klicken, gelangen Sie zum detaillierten Konferenzbericht.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="8abf7-129">Optimale Nutzung des Berichts für den IP-Telefonbestand</span><span class="sxs-lookup"><span data-stu-id="8abf7-129">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="8abf7-130">Wenn Sie nur an Verwendungsinformationen für eine bestimmte Art von Telefon interessiert sind (beispielsweise "wie oft verwenden Benutzer ein Polycom CX600-Telefon?"), können Sie diese Informationen direkt aus dem IP-Telefon Inventurbericht abrufen, indem Sie nach dieser bestimmten Art von Telefon filtern.</span><span class="sxs-lookup"><span data-stu-id="8abf7-130">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="8abf7-131">Wenn Sie jedoch Zusammenfassungsinformationen für alle Telefone wünschen (wie viele Benutzer eine Polycom CX600 verwenden, wie viele eine LG-Nortel IP8540 verwenden, usw.), müssen Sie die Daten exportieren und eine andere Anwendung (beispielsweise Windows PowerShell) für diese Art von Analyse verwenden.</span><span class="sxs-lookup"><span data-stu-id="8abf7-131">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="8abf7-132">Nehmen Sie beispielsweise an, dass Sie die Daten in eine Datei mit Komma getrennten Werten exportieren (C: \\ Data \\ IP \_ Phone \_ Inventory \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="8abf7-132">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="8abf7-133">In diesem Fall können Sie diese beiden Befehle verwenden, um zusammenfassende Daten für alle Telefone bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="8abf7-133">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="8abf7-134">Dadurch werden Daten zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="8abf7-134">That will return data similar to this:</span></span>

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

<span data-ttu-id="8abf7-135">Gleichermaßen erhalten Sie mithilfe dieser beiden Befehle Informationen dazu, welche Telefone zwar beim System angemeldet, aber tatsächlich nie zum Telefonieren genutzt wurden (der Wert der Metrik "Letzte Aktivität" ist leer und gibt somit an, dass es keine letzte Aktivität gab):</span><span class="sxs-lookup"><span data-stu-id="8abf7-135">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="8abf7-136">Dabei werden für alle nicht verwendeten Telefone Daten zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="8abf7-136">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="8abf7-137">Eine weitere interessante Möglichkeit, den Bericht über den IP-Telefon bestand zu verwenden, ist Folgendes: Wenn Sie über die Mac-Adresse eines IP-Telefons verfügen, können Sie den Benutzer, der dieses Telefon zuletzt verwendet hat, einfach über die Adresse in das Textfeld Mac-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="8abf7-137">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="8abf7-138">Der Bericht über den IP-Telefon bestand meldet dann (unter anderem) die SIP-Adresse des Benutzers, der sich zuletzt mit dem Telefon angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="8abf7-138">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="8abf7-139">Alternativ können Sie eine SIP-Adresse des Benutzers eingeben (im Feld Benutzer-URI-Präfix), um alle Telefone zu ermitteln, die von diesem Benutzer verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="8abf7-139">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8abf7-140">Filter</span><span class="sxs-lookup"><span data-stu-id="8abf7-140">Filters</span></span>

<span data-ttu-id="8abf7-p108">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der IP-Telefonbestand ermöglicht Ihnen beispielsweise das Anzeigen von Telefonen eines bestimmten Herstellers oder sogar einer bestimmten Version dieser Telefone. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8abf7-145">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht für den IP-Telefonbestand verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8abf7-145">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="8abf7-146">Bericht für den IP-Telefonbestand – Filter</span><span class="sxs-lookup"><span data-stu-id="8abf7-146">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8abf7-147">Name</span><span class="sxs-lookup"><span data-stu-id="8abf7-147">Name</span></span></th>
<th><span data-ttu-id="8abf7-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8abf7-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-p109">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="8abf7-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8abf7-152">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="8abf7-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8abf7-p110">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="8abf7-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8abf7-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8abf7-155">7/7/2012</span></span></p>
<p><span data-ttu-id="8abf7-156">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="8abf7-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8abf7-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8abf7-157">7/3/2012</span></span></p>
<p><span data-ttu-id="8abf7-158">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="8abf7-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-159"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-p111">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="8abf7-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8abf7-162">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="8abf7-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8abf7-p112">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="8abf7-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8abf7-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8abf7-165">7/7/2012</span></span></p>
<p><span data-ttu-id="8abf7-166">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="8abf7-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8abf7-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8abf7-167">7/3/2012</span></span></p>
<p><span data-ttu-id="8abf7-168">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="8abf7-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-169"><strong>Hersteller</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-169"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-p113">Name des Herstellers des IP-Telefons. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-172"><strong>Hardwareversion</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-172"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-173">Versionsnummer des IP-Telefons; mit den Filtern für den Hersteller und die Hardwareversion können Sie einen bestimmten Telefontyp eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8abf7-173">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="8abf7-174">Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8abf7-174">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-175"><strong>Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-175"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-p115">ID für die vom IP-Telefon verwendete Software. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-178"><strong>MAC-Adresse</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-178"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-p116">Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse (Media Access Control) wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="8abf7-p117">Zum Suchen nach Datensätzen mit einer bestimmten MAC-Adresse geben Sie einfach diese Adresse ein, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8abf7-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="8abf7-183">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="8abf7-183">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="8abf7-p118">Die Adresse muss vollständig eingegeben werden. Ein Teil einer Adresse (z. B. 00-08-5D) gibt keine Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-186"><strong>Letzte Aktivität vor (Tage)</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-186"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-187">Wählen Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="8abf7-187">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="8abf7-188">Alle</span><span class="sxs-lookup"><span data-stu-id="8abf7-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="8abf7-189">10 </span><span class="sxs-lookup"><span data-stu-id="8abf7-189">10</span></span></p></li>
<li><p><span data-ttu-id="8abf7-190">20</span><span class="sxs-lookup"><span data-stu-id="8abf7-190">20</span></span></p></li>
<li><p><span data-ttu-id="8abf7-191">30</span><span class="sxs-lookup"><span data-stu-id="8abf7-191">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-192"><strong>Zuletzt abgemeldet vor (Tage)</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-192"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-193">Wählen Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="8abf7-193">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="8abf7-194">Alle</span><span class="sxs-lookup"><span data-stu-id="8abf7-194">[All]</span></span></p></li>
<li><p><span data-ttu-id="8abf7-195">10 </span><span class="sxs-lookup"><span data-stu-id="8abf7-195">10</span></span></p></li>
<li><p><span data-ttu-id="8abf7-196">20</span><span class="sxs-lookup"><span data-stu-id="8abf7-196">20</span></span></p></li>
<li><p><span data-ttu-id="8abf7-197">30</span><span class="sxs-lookup"><span data-stu-id="8abf7-197">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-198"><strong>Präfix des Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-199">SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="8abf7-199">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8abf7-200">Metriken</span><span class="sxs-lookup"><span data-stu-id="8abf7-200">Metrics</span></span>

<span data-ttu-id="8abf7-201">In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht für den IP-Telefonbestand angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8abf7-201">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="8abf7-202">Bericht für den IP-Telefonbestand – Metriken</span><span class="sxs-lookup"><span data-stu-id="8abf7-202">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8abf7-203">Name</span><span class="sxs-lookup"><span data-stu-id="8abf7-203">Name</span></span></th>
<th><span data-ttu-id="8abf7-204">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="8abf7-204">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8abf7-205">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8abf7-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-206"><strong>Hersteller</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-206"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-207">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-208">Name des Herstellers des IP-Telefons.</span><span class="sxs-lookup"><span data-stu-id="8abf7-208">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-209"><strong>Hardwareversion</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-209"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-210">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-211">Versionsnummer des IP-Telefons.</span><span class="sxs-lookup"><span data-stu-id="8abf7-211">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-212"><strong>MAC-Adresse</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-212"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-213">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-p119">Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</span><span class="sxs-lookup"><span data-stu-id="8abf7-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-216"><strong>Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-216"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-217">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-218">SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="8abf7-218">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-219"><strong>Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-219"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-220">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-221">ID für die vom IP-Telefon verwendete Software.</span><span class="sxs-lookup"><span data-stu-id="8abf7-221">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-222"><strong>Zuletzt angemeldet um:</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-222"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-223">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-224">Datum und Uhrzeit der letzten Anmeldung des IP-Telefons bei lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abf7-224">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abf7-225"><strong>Zuletzt abgemeldet um:</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-225"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-226">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-227">Datum und Uhrzeit, zu denen das IP-Telefon zuletzt von lync Server abgemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="8abf7-227">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abf7-228"><strong>Letzte Aktivität</strong></span><span class="sxs-lookup"><span data-stu-id="8abf7-228"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="8abf7-229">Ja</span><span class="sxs-lookup"><span data-stu-id="8abf7-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="8abf7-230">Datum und Uhrzeit der letzten Verwendung des IP-Telefons.</span><span class="sxs-lookup"><span data-stu-id="8abf7-230">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

