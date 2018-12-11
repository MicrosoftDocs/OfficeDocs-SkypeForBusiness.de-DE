---
title: Konferenzdetailbericht in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Zusammenfassung: Informationen Sie zu den detaillierten Konferenzbericht in Skype für Business Server verwendet wird.'
ms.openlocfilehash: 025e8bda6e26baf261aeb3729907a3f13c220774
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27214595"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="c4479-103">Konferenzdetailbericht in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="c4479-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="c4479-104">**Zusammenfassung:** Informationen Sie zu den detaillierten Konferenzbericht in Skype für Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c4479-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="c4479-p101">Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="c4479-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="c4479-109">Zugreifen auf den detaillierten Konferenzbericht</span><span class="sxs-lookup"><span data-stu-id="c4479-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="c4479-110">Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="c4479-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="c4479-111">[Call Admission Control Report](call-admission-control-report.md) (durch Klicken auf die Metrik „Detail“ für eine Konferenz)</span><span class="sxs-lookup"><span data-stu-id="c4479-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="c4479-112">[Failure List Report](failure-list-report.md) (durch Klicken auf die Metrik „Konferenz“)</span><span class="sxs-lookup"><span data-stu-id="c4479-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="c4479-113">[User Activity Report](call-diagnostic-reports-per-user.md) (durch Klicken auf die Metrik „Konferenz-URI“)</span><span class="sxs-lookup"><span data-stu-id="c4479-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="c4479-114">Über den detaillierten Konferenzbericht können Sie die [Diagnose Berich](diagnostic-report.md) zugreifen, durch Klicken auf die Metrik Diagnosebericht (Detail).</span><span class="sxs-lookup"><span data-stu-id="c4479-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="c4479-115">Filter</span><span class="sxs-lookup"><span data-stu-id="c4479-115">Filters</span></span>

<span data-ttu-id="c4479-p102">Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="c4479-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="c4479-118">Metriken</span><span class="sxs-lookup"><span data-stu-id="c4479-118">Metrics</span></span>

<span data-ttu-id="c4479-119">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4479-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="c4479-120">**Konferenzinformationen – Metriken**</span><span class="sxs-lookup"><span data-stu-id="c4479-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="c4479-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="c4479-121">**Name**</span></span>                 | <span data-ttu-id="c4479-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c4479-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c4479-123">**Konferenz-URI**</span><span class="sxs-lookup"><span data-stu-id="c4479-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="c4479-p103">Der Konferenz zugewiesener URI. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c4479-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="c4479-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="c4479-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="c4479-127">**Pool-FQDN**</span><span class="sxs-lookup"><span data-stu-id="c4479-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="c4479-128">Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c4479-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="c4479-129">**Startzeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="c4479-129">**Start time**</span></span> <br/>     | <span data-ttu-id="c4479-130">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="c4479-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="c4479-131">**Organisator**</span><span class="sxs-lookup"><span data-stu-id="c4479-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="c4479-132">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="c4479-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="c4479-133">**Endzeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="c4479-133">**End time**</span></span> <br/>       | <span data-ttu-id="c4479-134">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="c4479-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="c4479-135">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4479-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="c4479-136">**Konferenzteilnahme – Metriken**</span><span class="sxs-lookup"><span data-stu-id="c4479-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="c4479-137">**Name**</span><span class="sxs-lookup"><span data-stu-id="c4479-137">**Name**</span></span>|<span data-ttu-id="c4479-138">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c4479-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4479-139">**User**</span><span class="sxs-lookup"><span data-stu-id="c4479-139">**User**</span></span> <br/> |<span data-ttu-id="c4479-140">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="c4479-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-141">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="c4479-141">**Role**</span></span> <br/> |<span data-ttu-id="c4479-142">Rolle (z. B. Referent) des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="c4479-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="c4479-143">**Verbindung**</span><span class="sxs-lookup"><span data-stu-id="c4479-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="c4479-144">Netzwerkverbindungen (in der Regel „From Internal“ oder „From External“) des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="c4479-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="c4479-145">**Beitrittszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="c4479-145">**Join time**</span></span> <br/> |<span data-ttu-id="c4479-146">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c4479-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-147">**Beendigungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="c4479-147">**Leave time**</span></span> <br/> |<span data-ttu-id="c4479-148">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="c4479-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-149">**Benutzer-Agent**</span><span class="sxs-lookup"><span data-stu-id="c4479-149">**User agent**</span></span> <br/> |<span data-ttu-id="c4479-150">Der Bezeichner für die vom Endpunkt des Teilnehmers verwendete Software.</span><span class="sxs-lookup"><span data-stu-id="c4479-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="c4479-151">**Diagnoseberichte**</span><span class="sxs-lookup"><span data-stu-id="c4479-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="c4479-p104">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4479-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="c4479-154">In der folgenden Tabelle sind die Informationen in den Abschnitt zu Konferenzmodalitäten des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4479-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="c4479-155">**Konferenzmodalitäten – Metriken**</span><span class="sxs-lookup"><span data-stu-id="c4479-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="c4479-156">**Name**</span><span class="sxs-lookup"><span data-stu-id="c4479-156">**Name**</span></span>|<span data-ttu-id="c4479-157">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c4479-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4479-158">**User**</span><span class="sxs-lookup"><span data-stu-id="c4479-158">**User**</span></span> <br/> |<span data-ttu-id="c4479-159">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="c4479-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-160">**Beitrittszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="c4479-160">**Join time**</span></span> <br/> |<span data-ttu-id="c4479-161">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c4479-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-162">**Beendigungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="c4479-162">**Leave time**</span></span> <br/> |<span data-ttu-id="c4479-163">Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="c4479-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-164">**Konferenzserver-URI**</span><span class="sxs-lookup"><span data-stu-id="c4479-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="c4479-165">URI für den in der Konferenz verwendeten Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="c4479-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="c4479-166">**Diagnoseberichte**</span><span class="sxs-lookup"><span data-stu-id="c4479-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="c4479-p105">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c4479-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


