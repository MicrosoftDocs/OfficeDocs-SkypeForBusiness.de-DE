---
title: Konferenz Detail Bericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Zusammenfassung: erfahren Sie mehr über den Konferenz Detail Bericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: 5b88ae62c7d06437b3502bd72dd965fc26fbfcb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305787"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="b6cd1-103">Konferenz Detail Bericht in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b6cd1-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="b6cd1-104">**Zusammenfassung:** Informieren Sie sich über den Konferenz Detail Bericht, der in Skype for Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="b6cd1-p101">Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="b6cd1-109">Zugreifen auf den detaillierten Konferenzbericht</span><span class="sxs-lookup"><span data-stu-id="b6cd1-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="b6cd1-110">Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="b6cd1-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="b6cd1-111">[Call Admission Control Report](call-admission-control-report.md) (durch Klicken auf die Metrik „Detail“ für eine Konferenz)</span><span class="sxs-lookup"><span data-stu-id="b6cd1-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="b6cd1-112">[Failure List Report](failure-list-report.md) (durch Klicken auf die Metrik „Konferenz“)</span><span class="sxs-lookup"><span data-stu-id="b6cd1-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="b6cd1-113">[User Activity Report](call-diagnostic-reports-per-user.md) (durch Klicken auf die Metrik „Konferenz-URI“)</span><span class="sxs-lookup"><span data-stu-id="b6cd1-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="b6cd1-114">Im Konferenz Detail Bericht können Sie auf den [Diagnose](diagnostic-report.md) -Repor zugreifen, indem Sie auf die Metrik Diagnosebericht (Detail) klicken.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="b6cd1-115">Filter</span><span class="sxs-lookup"><span data-stu-id="b6cd1-115">Filters</span></span>

<span data-ttu-id="b6cd1-p102">Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="b6cd1-118">Metriken</span><span class="sxs-lookup"><span data-stu-id="b6cd1-118">Metrics</span></span>

<span data-ttu-id="b6cd1-119">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="b6cd1-120">**Konferenzinformationen – Metriken**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="b6cd1-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-121">**Name**</span></span>                 | <span data-ttu-id="b6cd1-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b6cd1-123">**Konferenz-URI**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="b6cd1-p103">Der Konferenz zugewiesener URI. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b6cd1-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="b6cd1-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="b6cd1-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="b6cd1-127">**Pool-FQDN**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="b6cd1-128">Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="b6cd1-129">**Startzeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-129">**Start time**</span></span> <br/>     | <span data-ttu-id="b6cd1-130">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="b6cd1-131">**Organisator**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="b6cd1-132">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="b6cd1-133">**Endzeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-133">**End time**</span></span> <br/>       | <span data-ttu-id="b6cd1-134">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="b6cd1-135">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="b6cd1-136">**Konferenzteilnahme – Metriken**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="b6cd1-137">**Name**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-137">**Name**</span></span>|<span data-ttu-id="b6cd1-138">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6cd1-139">**User**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-139">**User**</span></span> <br/> |<span data-ttu-id="b6cd1-140">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-141">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-141">**Role**</span></span> <br/> |<span data-ttu-id="b6cd1-142">Rolle (z. B. Referent) des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-143">**Verbindung**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="b6cd1-144">Netzwerkverbindungen (in der Regel „From Internal“ oder „From External“) des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-145">**Beitrittszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-145">**Join time**</span></span> <br/> |<span data-ttu-id="b6cd1-146">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-147">**Beendigungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-147">**Leave time**</span></span> <br/> |<span data-ttu-id="b6cd1-148">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-149">**Benutzer-Agent**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-149">**User agent**</span></span> <br/> |<span data-ttu-id="b6cd1-150">Der Bezeichner für die Software, die vom Endpunkt des Teilnehmers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-151">**Diagnoseberichte**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="b6cd1-p104">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="b6cd1-154">In der folgenden Tabelle sind die Informationen aufgeführt, die im Abschnitt Konferenz Modalitäten des Konferenz Detail Berichts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="b6cd1-155">**Konferenzmodalitäten – Metriken**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="b6cd1-156">**Name**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-156">**Name**</span></span>|<span data-ttu-id="b6cd1-157">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6cd1-158">**User**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-158">**User**</span></span> <br/> |<span data-ttu-id="b6cd1-159">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-160">**Beitrittszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-160">**Join time**</span></span> <br/> |<span data-ttu-id="b6cd1-161">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-162">**Beendigungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-162">**Leave time**</span></span> <br/> |<span data-ttu-id="b6cd1-163">Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-164">**Konferenzserver-URI**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="b6cd1-165">URI für den in der Konferenz verwendeten Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="b6cd1-166">**Diagnoseberichte**</span><span class="sxs-lookup"><span data-stu-id="b6cd1-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="b6cd1-p105">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b6cd1-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


