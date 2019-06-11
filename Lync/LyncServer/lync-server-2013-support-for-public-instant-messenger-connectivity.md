---
title: Lync Server 2013-Unterstützung für öffentliche Instant Messenger-Konnektivität
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="ae8ae-102">Unterstützung für die öffentliche Instant Messenger-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae8ae-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae8ae-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ae8ae-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="ae8ae-104">Unterstützung für öffentliche Instant Messenger-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="ae8ae-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="ae8ae-105">Dieser Artikel enthält Informationen zur Unterstützung öffentlicher Chat Verbindungen (PIC).</span><span class="sxs-lookup"><span data-stu-id="ae8ae-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="ae8ae-106">PIC ist eine Funktion von Microsoft lync, die es Organisationen ermöglicht, ihren lync-Benutzern die Verbindung mit Benutzern bestimmter öffentlicher Instant Messaging-Dienste (im) über Ihre lync-Clients und-Identitäten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="ae8ae-107">Endbenutzer profitieren von der Möglichkeit, mit Kunden, Partnern und Anbietern zu ihren Konditionen in Verbindung zu treten.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="ae8ae-108">Sie profitiert von der Unterstützung eines einzelnen Echt Zeit Kommunikations Clients unter Beibehaltung der Kontroll-, Compliance-und Archivierungsfunktionen von lync.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="ae8ae-109">Lync – Skype-Konnektivität, [öffentlich verfügbar im Mai 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), basiert auf dem Vermächtnis, das lync/Office Communications Server (OCS)/Live Communications Server (LCS) erstmals mit PIC bei der Verbindung zu MSN/Windows Live, AOL und Yahoo eingerichtet hat.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="ae8ae-110">Weitere Informationen zur lync-Skype-Konnektivität finden Sie in der [lync-Skype-Konnektivität](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="ae8ae-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="ae8ae-111">Föderation mit Windows Live, AOL und Yahoo sind jeweils auf einem Weg zum Ende des Lebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="ae8ae-112">Auf dieser Seite wird der Status der einzelnen Dienste dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="ae8ae-113">Um PIC verwenden zu können, mussten Kunden den Dienst für jeden öffentlichen Chatdienst Anbieter aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="ae8ae-114">Die Voraussetzungen und Einzelheiten dazu hängen vom Chatdienst Anbieter und dem zugrunde liegenden Lizenzierungsprogramm des Kunden ab.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="ae8ae-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ae8ae-115">Windows Live Messenger</span></span>

<span data-ttu-id="ae8ae-116">Microsoft hat Windows Live Messenger und Skype zusammengebracht.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="ae8ae-117">Im April 2013 wurden Messenger-Benutzer bei der Anmeldung zu Skype migriert.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="ae8ae-118">Lync-Kunden, die sich auf den Verbund mit Messenger verlassen, können weiterhin mit Ihren Messenger-Kontakten kommunizieren, auch wenn diese Kontakte auf Skype aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="ae8ae-119">Es gibt nichts, was lync-Administratoren oder lync-Endbenutzer tun müssen, um die Kontinuität des Diensts zu gewährleisten, und die Verwaltung dieser Funktion in lync bleibt die gleiche wie für die Kommunikation mit Messenger.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="ae8ae-120">Wenn Messenger-Nutzer sich bei Skype mit Ihren Microsoft-Konten (also den gleichen Anmeldeinformationen, die für Messenger verwendet werden) anmelden, führen Sie alle Ihre Messenger-Kontakte, einschließlich der Partner von lync-Kontakten, in Skype.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="ae8ae-121">Anwesenheits Freigabe und Instant Messaging zwischen Skype und lync sind für diese Kontakte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="ae8ae-122">Lync – Skype-Konnektivität – Kontakt hinzufügen, Anwesenheits Freigabe, Sofortnachrichten und Audioanrufe zwischen lync-und Skype-Benutzern – steht nun auch allen lync-Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="ae8ae-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="ae8ae-123">Yahoo\!</span></span> <span data-ttu-id="ae8ae-124">und AOL-Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="ae8ae-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="ae8ae-125">Föderation mit Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="ae8ae-125">Federation with Yahoo\!</span></span> <span data-ttu-id="ae8ae-126">und AOL sind sowohl auf dem Weg zum Ende der Zeit für Kunden von lync (und Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="ae8ae-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="ae8ae-127">Die Möglichkeit von Microsoft, diese Dienste bereitzustellen, wurde von Yahoo unterstützt.\!</span><span class="sxs-lookup"><span data-stu-id="ae8ae-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="ae8ae-128">und AOL, und die zugrunde liegenden Vereinbarungen dieser beiden werden abgewickelt.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="ae8ae-129">Für Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="ae8ae-129">For both Yahoo\!</span></span> <span data-ttu-id="ae8ae-130">und AOL wird der Service bis Juni 2014 fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="ae8ae-131">**Yahoo** -Service wird bis Juni 2014 fortgesetzt, und Kunden müssen weiterhin mit der Microsoft lync Public Chat-Benutzerabonnementlizenz ("PIC USL") lizenziert werden.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="ae8ae-132">Ab dem 1. September steht 2012, die PIC USL, nicht mehr zum Kauf für neue oder erneuernde Vereinbarungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="ae8ae-133">Kunden mit Lizenzen, die vor diesem Datum erworben wurden, können weiterhin mit Yahoo zusammenarbeiten.\!</span><span class="sxs-lookup"><span data-stu-id="ae8ae-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="ae8ae-134">bis zum vorherigen Datum des Diensts oder nach Ablauf der Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="ae8ae-135">Lesen Sie [die Ankündigung](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) im lync-Teamblog.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="ae8ae-136">Kunden, die über PIC-Lizenzen für Vereinbarungen verfügen, die sich über die letzten 30. Juni-2014 erstrecken, erhalten ein Guthaben im Verhältnis zur Höhe der Zahlungen, die den Zeitraum nach dem 30. Juni 2014 betragen.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="ae8ae-137">**AOL** – am 30. Juni 2014 steht lyncs Chat-Konnektivität ("PIC") nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="ae8ae-138">Um die Kunden-Unterbrechung zu begrenzen, wenn der Service endet, haben wir die Bereitstellung zusätzlicher Kunden Domänen eingestellt.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="ae8ae-139">Bis zum 30. Juni 2014 müssen Kunden nichts Unternehmen, um die Föderations Kommunikation mit AIM weiter zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="ae8ae-140">Über diesen Termin hinaus (oder für Kunden, die in der Zwischenzeit zusätzliche Domänen bereitstellen möchten), steht ein Ersatzdienst direkt bei AOL zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="ae8ae-141">Weitere Informationen zum neuen Dienst von AOL finden Sie unter [Einrichten der direkten Föderation mit AIM](http://aimenterprise.aol.com/pic.php)  (öffnet eine neue Seite auf AOL.com).</span><span class="sxs-lookup"><span data-stu-id="ae8ae-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="ae8ae-142">Zusammenfassung des öffentlichen Chat-Anbieters</span><span class="sxs-lookup"><span data-stu-id="ae8ae-142">Public IM Provider Summary</span></span>

<span data-ttu-id="ae8ae-143">Die folgende Tabelle enthält eine Zusammenfassung der öffentlichen Chat Dienstanbieter, der Verbundfunktionen mit lync und den Lizenzierungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae8ae-144">Öffentlicher Chatdienst Anbieter</span><span class="sxs-lookup"><span data-stu-id="ae8ae-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="ae8ae-145">Verbundfunktionen</span><span class="sxs-lookup"><span data-stu-id="ae8ae-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="ae8ae-146">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="ae8ae-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae8ae-147">Skype</span><span class="sxs-lookup"><span data-stu-id="ae8ae-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-148">Chat, Anwesenheit, Audio</span><span class="sxs-lookup"><span data-stu-id="ae8ae-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-149">Lync Server-Client Zugriffs Lizenzen, lync Online Plan 1/2/3</span><span class="sxs-lookup"><span data-stu-id="ae8ae-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae8ae-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ae8ae-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-151">Chat, Anwesenheit, Audio/Video</span><span class="sxs-lookup"><span data-stu-id="ae8ae-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-152">Lync Server-Client Zugriffs Lizenzen (unterstützt, solange WLM im Markt ist)</span><span class="sxs-lookup"><span data-stu-id="ae8ae-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae8ae-153">AOL</span><span class="sxs-lookup"><span data-stu-id="ae8ae-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-154">Chat, Anwesenheitsstatus</span><span class="sxs-lookup"><span data-stu-id="ae8ae-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-155">Lync Server-Client Zugriffs Lizenzen; wird bis Juni 2014 für bestehende Kunden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae8ae-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ae8ae-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-157">Chat, Anwesenheitsstatus</span><span class="sxs-lookup"><span data-stu-id="ae8ae-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="ae8ae-158">Erfordert zusätzlich zu den lync Server-Client Zugriffs Lizenzen zusätzliche Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL").</span><span class="sxs-lookup"><span data-stu-id="ae8ae-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="ae8ae-159">Ab der 2012-Preisliste vom September steht die PIC-USL nicht mehr zum Kauf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="ae8ae-160">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="ae8ae-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ae8ae-161">Messenger, bis der Dienst das Datum am 30. Juni 2014 beendet hat.</span><span class="sxs-lookup"><span data-stu-id="ae8ae-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

