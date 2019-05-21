---
title: Bericht zur Fehlerliste in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Zusammenfassung: erfahren Sie mehr über den Bericht zur Fehlerliste in Skype for Business Server.'
ms.openlocfilehash: 72637863d7a15d26ea997de8a9c3526279afc57f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305759"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="847b4-103">Bericht zur Fehlerliste in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="847b4-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="847b4-104">**Zusammenfassung:** Informieren Sie sich über den Bericht Fehlerliste in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="847b4-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="847b4-p101">Der Fehlerlistenbericht enthält ausführliche Informationen über die einzelnen Teilnehmer, die an einer fehlerhaften Peer-to-Peer-Sitzung oder Konferenzsitzung beteiligt waren. Diese Informationen umfassen den URI des Benutzers, bei dem das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="847b4-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="847b4-107">Zugriff auf den Fehlerlistenbericht</span><span class="sxs-lookup"><span data-stu-id="847b4-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="847b4-108">Der fehlerlistenbericht wird durch Klicken auf eine der folgenden Metriken im Bericht " [Fehlerverteilung" in Skype for Business Server](failure-distribution-report.md)aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="847b4-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="847b4-109">Wichtigste Diagnosegründe (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="847b4-110">Wichtigste Modalitäten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="847b4-111">Wichtigste Pools (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="847b4-112">Wichtigste Quellen (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="847b4-113">Wichtigste Komponenten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="847b4-114">Wichtigste Absenderbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="847b4-115">Wichtigste Empfängerbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="847b4-116">Wichtigste Absenderbenutzer-Agenten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="847b4-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="847b4-117">Im Bericht Fehlerliste können Sie auf den [Bericht Peer-to-Peer-Sitzungsdetails in Skype for Business Server](peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Sitzungs Detail Metrik für eine Peer-to-Peer-Sitzung klicken.</span><span class="sxs-lookup"><span data-stu-id="847b4-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="847b4-118">Sie können ebenfalls auf den detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.</span><span class="sxs-lookup"><span data-stu-id="847b4-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="847b4-119">Bestmögliche Verwendung des Fehlerlistenberichts</span><span class="sxs-lookup"><span data-stu-id="847b4-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="847b4-p103">Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode bzw. jede Diagnose-ID sehen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie zum Beispiel Ihre Maus über die Diagnose-ID 7025 halten, wird in einer QuickInfo folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="847b4-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="847b4-122">Interner Serverfehler erstellt Medien für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="847b4-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="847b4-123">Dabei muss beachtet werden, dass der Fehlerlistenbericht weder eine einfache Methode zum direkten Abrufen einer Liste aller Benutzer, die an mindestens einer fehlerhaften Sitzung beteiligt waren, noch eine Methode zur Ermittlung der Benutzer, die am häufigsten an einer fehlerhaften Sitzung beteiligt waren, darstellt.</span><span class="sxs-lookup"><span data-stu-id="847b4-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="847b4-124">(Zum einen hat der fehlerlistenbericht keine Filterfunktionen.) Wenn Sie die Daten exportieren und dann in eine Datei mit Komma getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um Antworten auf Fragen wie diese zu finden.</span><span class="sxs-lookup"><span data-stu-id="847b4-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="847b4-125">Zum Beispiel können Sie die Daten in einer CSV-Datei mit dem Namen „C:\Data\Failure_List.csv“ speichern.</span><span class="sxs-lookup"><span data-stu-id="847b4-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="847b4-126">Auf Basis der in dieser Datei gespeicherten Daten können mithilfe dieses Befehls alle Benutzer aufgelistet werden, die an mindestens einer fehlerhaften Sitzung beteiligt waren:</span><span class="sxs-lookup"><span data-stu-id="847b4-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="847b4-127">Die Ausgabe für den Befehl ist eine Liste, die der folgenden Liste ähnelt:</span><span class="sxs-lookup"><span data-stu-id="847b4-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="847b4-128">Diese beiden Befehle melden die Gesamtzahl der fehlerhaften Sitzungen zurück, an denen Benutzer beteiligt waren:</span><span class="sxs-lookup"><span data-stu-id="847b4-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="847b4-129">Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:</span><span class="sxs-lookup"><span data-stu-id="847b4-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="847b4-130">Filter</span><span class="sxs-lookup"><span data-stu-id="847b4-130">Filters</span></span>

<span data-ttu-id="847b4-p105">Keine. Sie können den Fehlerlistenbericht nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="847b4-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="847b4-133">Metriken</span><span class="sxs-lookup"><span data-stu-id="847b4-133">Metrics</span></span>

<span data-ttu-id="847b4-134">In der folgenden Tabelle sind die im Fehlerlistenbericht enthaltenen Informationen für jeden fehlerhaften Anruf aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="847b4-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="847b4-135">**Metriken des Fehlerlistenberichts**</span><span class="sxs-lookup"><span data-stu-id="847b4-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="847b4-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="847b4-136">**Name**</span></span>|<span data-ttu-id="847b4-137">**Kann nach dieser Metrik sortiert werden?**</span><span class="sxs-lookup"><span data-stu-id="847b4-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="847b4-138">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="847b4-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="847b4-139">**Gemeldeter Zeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="847b4-139">**Reported time**</span></span> <br/> |<span data-ttu-id="847b4-140">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-140">No</span></span>  <br/> |<span data-ttu-id="847b4-141">Datum und Uhrzeit der Aufzeichnung des Berichts.</span><span class="sxs-lookup"><span data-stu-id="847b4-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="847b4-142">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="847b4-142">**Request**</span></span> <br/> |<span data-ttu-id="847b4-143">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-143">No</span></span>  <br/> |<span data-ttu-id="847b4-p106">Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.</span><span class="sxs-lookup"><span data-stu-id="847b4-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="847b4-146">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="847b4-146">**Response code**</span></span> <br/> |<span data-ttu-id="847b4-147">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-147">No</span></span>  <br/> |<span data-ttu-id="847b4-148">SIP-Antwortcode, der bei einem Konferenzfehler gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="847b4-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="847b4-149">**Diagnose-ID**</span><span class="sxs-lookup"><span data-stu-id="847b4-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="847b4-150">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-150">No</span></span>  <br/> |<span data-ttu-id="847b4-151">Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="847b4-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="847b4-152">**Beitrittszeitraum (ms)**</span><span class="sxs-lookup"><span data-stu-id="847b4-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="847b4-153">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-153">No</span></span>  <br/> |<span data-ttu-id="847b4-154">Zeitraum (in Millisekunden), der erforderlich ist, damit der Benutzer der Konferenz beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="847b4-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="847b4-155">**Absenderbenutzer**</span><span class="sxs-lookup"><span data-stu-id="847b4-155">**From user**</span></span> <br/> |<span data-ttu-id="847b4-156">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-156">No</span></span>  <br/> |<span data-ttu-id="847b4-157">Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="847b4-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="847b4-158">**Von Benutzeragent**</span><span class="sxs-lookup"><span data-stu-id="847b4-158">**From user agent**</span></span> <br/> |<span data-ttu-id="847b4-159">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-159">No</span></span>  <br/> |<span data-ttu-id="847b4-160">Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="847b4-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="847b4-161">**An Benutzer**</span><span class="sxs-lookup"><span data-stu-id="847b4-161">**To user**</span></span> <br/> |<span data-ttu-id="847b4-162">Nein</span><span class="sxs-lookup"><span data-stu-id="847b4-162">No</span></span>  <br/> |<span data-ttu-id="847b4-163">SIP-Adresse des Benutzers, der angerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="847b4-163">SIP address of the user who was being called.</span></span>  <br/> |
   

