---
title: 'Lync Server 2013: Betriebs Abhängigkeiten'
description: 'Lync Server 2013: Betriebs Abhängigkeiten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579191"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="fa2f6-103">Betriebs Abhängigkeiten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa2f6-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa2f6-104">_**Letztes Änderungsstand des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="fa2f6-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="fa2f6-105">Die in diesem Dokument beschriebene Referenzarchitektur hilft sicherzustellen, dass Sie über eine lync Server 2013-Bereitstellung verfügen, die nicht nur auf die Anforderungen der Organisation skaliert, sondern gemäß den bewährten Methoden von Microsoft entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="fa2f6-106">Es kann sein, dass die lync Server 2013 Implementierung ein dynamischer Dienst ist und wie jeder andere Dienst im Unternehmen weiterhin eine Überwachung und proaktive Verwaltung benötigt, um dem Unternehmen hohe Serviceverfügbarkeit und Servicequalität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="fa2f6-107">Da lync Server 2013 im täglichen Geschäft der Organisation tief verwurzelt ist, ist es wichtig, dass der Dienst durch eine präzise und greifbare Service Level-Verwaltung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="fa2f6-108">Die lync-Systemarchitektur kann komplex und sehr integriert werden, um ein effektives Service Level-Management beizubehalten und SLAs für lync Server 2013 einzurichten, um die Abhängigkeiten des Systems von anderen Plattformen und Servern zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="fa2f6-109">Ebenso wichtig ist es, festzustellen, welche Unternehmensdienste wie VoIP-und UC-integrierte Anwendungen von lync abhängig werden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="fa2f6-110">Lync Server 2013 muss festgestellt werden, wobei alle genannten Abhängigkeiten berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="fa2f6-111">Mit der Service Map können Sie eine SLA zwischen lync und dem dazugehörigen Dienst formulieren und einen Ausgangspunkt für die SLA-Aushandlung bieten.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="fa2f6-112">In der folgenden Tabelle sind die typischen Abhängigkeitsdienste für eine lync-Infrastruktur aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="fa2f6-113">Jede dieser Technologien sollte über eine eigene proaktive Überwachung verfügen.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="fa2f6-114">Typische Abhängigkeitsdienste</span><span class="sxs-lookup"><span data-stu-id="fa2f6-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa2f6-115">Abhängigkeitsdienst</span><span class="sxs-lookup"><span data-stu-id="fa2f6-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-116">Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="fa2f6-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-117">Server Hardware</span><span class="sxs-lookup"><span data-stu-id="fa2f6-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa2f6-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-119">Öffentliche Schlüsselinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="fa2f6-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-120">Domänen Benennungsdienst</span><span class="sxs-lookup"><span data-stu-id="fa2f6-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-121">Datenbankdienste</span><span class="sxs-lookup"><span data-stu-id="fa2f6-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-122">Speicherdienste</span><span class="sxs-lookup"><span data-stu-id="fa2f6-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-123">System Verwaltung – Überwachung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="fa2f6-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-124">Sicherheitsdienste – Antivirus</span><span class="sxs-lookup"><span data-stu-id="fa2f6-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-125">Netzwerkinfrastruktur – Internet</span><span class="sxs-lookup"><span data-stu-id="fa2f6-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-126">Netzwerkinfrastruktur – intern (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="fa2f6-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-127">Telefonie-Infrastruktur – IP-PBX und Gateways</span><span class="sxs-lookup"><span data-stu-id="fa2f6-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-128">Cloud-Dienste</span><span class="sxs-lookup"><span data-stu-id="fa2f6-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa2f6-129">Es wird davon ausgegangen, dass die Organisation operativ ausgereift ist, indem Sie grundlegende Service Level-Verwaltungsfunktionen wie Change, Incident and Release Management gemäß der vorgeschriebenen MOF-Funktion ausüben.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="fa2f6-130">Die lync-Lösung sollte von diesen Funktionen übernommen werden und den gleichen betrieblichen Verwaltungsprozessen unterworfen werden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="fa2f6-131">Aufbauend auf den oben gewonnenen Informationen haben wir nun ein besseres Verständnis dafür, was sich auf den lync-Dienst im Unternehmen auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="fa2f6-132">Um die Verfügbarkeit und Qualität von lync Server 2013 Diensten sicherzustellen, müssen die folgenden Überwachungstools mit der Bereitstellung der Referenzarchitektur einhergehen:</span><span class="sxs-lookup"><span data-stu-id="fa2f6-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="fa2f6-133">Überwachungstools</span><span class="sxs-lookup"><span data-stu-id="fa2f6-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa2f6-134">Komponente</span><span class="sxs-lookup"><span data-stu-id="fa2f6-134">Component</span></span></th>
<th><span data-ttu-id="fa2f6-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa2f6-135">Description</span></span></th>
<th><span data-ttu-id="fa2f6-136">Zutreffende Website</span><span class="sxs-lookup"><span data-stu-id="fa2f6-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-137">Lync Server 2013 Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="fa2f6-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-138">Stellen Sie mindestens eine lync Server 2013 Monitoring Server-Rolle pro zentraler Standort bereit, und konfigurieren Sie das QoE-Berichtspaket (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="fa2f6-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="fa2f6-139">Weitere Informationen finden Sie in der Dokumentation zur lync Server 2013-Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="fa2f6-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="fa2f6-140"><a href="lync-server-2013-deploying-monitoring.md">Bereitstellen der Überwachung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fa2f6-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fa2f6-141">Zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="fa2f6-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="fa2f6-142">Binden Sie jeden Pool an die nächstgelegene Instanz der Monitoring Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-143">Zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="fa2f6-143">Central sites</span></span></p>
<p><span data-ttu-id="fa2f6-144">Zweigstellenstandorte</span><span class="sxs-lookup"><span data-stu-id="fa2f6-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="fa2f6-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-146">System Center Operations Manager 2012, in dem das Microsoft lync Server 2013 Management Pack (MP) importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="fa2f6-147">Das Management Pack implementiert herkömmliches Ereignisprotokoll und Leistungsindikator basierte Instrumentation wird verwendet und ermöglicht die neu verfügbare Instrumentation in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-148">Zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="fa2f6-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="fa2f6-149">Stellen Sie sicher, dass die zentrale Ermittlung der zu überwachenden Rollen und Komponenten automatisch basierend auf einem zentralen Ermittlungsskript ausgeführt wird, das das in der zentralen Verwaltungsdatenbank veröffentlichte Topologie-Dokument liest.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-150">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-150">Central Site</span></span></p>
<p><span data-ttu-id="fa2f6-151">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-151">Branch Site</span></span></p>
<p><span data-ttu-id="fa2f6-152">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="fa2f6-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="fa2f6-153">Bereitstellen von System Center Operations Manager 2007-Agents auf allen bereitgestellten Servern mit lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-154">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-154">Central Site</span></span></p>
<p><span data-ttu-id="fa2f6-155">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-155">Branch Site</span></span></p>
<p><span data-ttu-id="fa2f6-156">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="fa2f6-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="fa2f6-157">Stellen Sie sicher, dass priorisierte Warnungen für die Benachrichtigung konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="fa2f6-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="fa2f6-158">Warnungen mit hoher Priorität</span><span class="sxs-lookup"><span data-stu-id="fa2f6-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="fa2f6-159">Warnungen mittlerer Priorität</span><span class="sxs-lookup"><span data-stu-id="fa2f6-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="fa2f6-160">Andere Warnungen.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-161">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-161">Central Site</span></span></p>
<p><span data-ttu-id="fa2f6-162">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-162">Branch Site</span></span></p>
<p><span data-ttu-id="fa2f6-163">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="fa2f6-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="fa2f6-164">Konfigurieren Sie die Port Überwachung für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-165">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-165">Central Site</span></span></p>
<p><span data-ttu-id="fa2f6-166">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-166">Branch Site</span></span></p>
<p><span data-ttu-id="fa2f6-167">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="fa2f6-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="fa2f6-168">Konfigurieren der URL-Überwachung für Ihre Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="fa2f6-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-169">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-170">Integration von lync und System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="fa2f6-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-171">Bereitstellen der Anruf Zuverlässigkeit und Medienqualität MonitoringCall Zuverlässigkeit und Medien Qualitätsüberwachung verwenden Sie den Monitoring Server Computer als Monitor Knoten, um die Anruf Zuverlässigkeit und Medienqualität von lync Server zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="fa2f6-172">Beide Funktionen Abfrage der Monitoring Server Datenbanken zu tun Analyse.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-173">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-173">Central Site</span></span></p>
<p><span data-ttu-id="fa2f6-174">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="fa2f6-175">Stellen Sie sicher, dass die Warnschwellen für Medienqualität genau konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="fa2f6-176">In der folgenden Tabelle werden die maximalen Netzwerk mittleren Meinungs Bewertungen nach Codec angegeben.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="fa2f6-177">In der Produktion sollten diese Ergebnisse für einen festgelegten Zeitraum überwacht werden, und es müssen akzeptable Schwellenwerte basierend auf den jeweiligen NMOS-Ergebnissen der Organisation festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-178">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-178">Central Site</span></span></p>
<p><span data-ttu-id="fa2f6-179">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-180">Lync Server 2013er synthetischer Transaktionsmonitor</span><span class="sxs-lookup"><span data-stu-id="fa2f6-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-181">Stellen Sie eine dedizierte lync Server als synthetischen Transaktionsmonitor bereit.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="fa2f6-182">Synthetische Transaktionen sind lync Server 2013 Windows PowerShell-Cmdlets, die vom Management Pack automatisch in einem vordefinierten Intervall ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="fa2f6-183">Diese werden auf einem Knoten mit synthetischen Transaktions Monitoren ausgeführt, der ein vom Administrator festgelegter Server ist, der für die Ermittlung und Ausführung von STS für jeden Pool zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="fa2f6-184">Es wird nicht empfohlen, einen vorhandenen Microsoft lync Server 2013 Server als synthetischen Transaktionsmonitor Knoten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="fa2f6-185">Dies ist auf die hohen Anforderungen an die CPU/Arbeitsspeichernutzung für die Ausführung von STS zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="fa2f6-186">Verwenden Sie für den Knoten synthetischer Transaktionsmonitor einen neuen Server Computer (oder einen virtuellen Server).</span><span class="sxs-lookup"><span data-stu-id="fa2f6-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-187">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="fa2f6-188">Bereitstellen des Monitor Knotens für synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="fa2f6-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="fa2f6-189">Lesen Sie das MonitoringCS_withSCOM.docx Dokument in der UCTAP Connect-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-190">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="fa2f6-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="fa2f6-191">Maximale Anzahl von Netzwerk-Mos-Bewertungen Pro Codec</span><span class="sxs-lookup"><span data-stu-id="fa2f6-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa2f6-192">Szenario</span><span class="sxs-lookup"><span data-stu-id="fa2f6-192">Scenario</span></span></th>
<th><span data-ttu-id="fa2f6-193">Codec</span><span class="sxs-lookup"><span data-stu-id="fa2f6-193">Codec</span></span></th>
<th><span data-ttu-id="fa2f6-194">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="fa2f6-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-195">UC-UC-Anruf</span><span class="sxs-lookup"><span data-stu-id="fa2f6-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-196">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="fa2f6-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-197">4.10</span><span class="sxs-lookup"><span data-stu-id="fa2f6-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-198">UC-UC-Anruf</span><span class="sxs-lookup"><span data-stu-id="fa2f6-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-199">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="fa2f6-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-200">2,95</span><span class="sxs-lookup"><span data-stu-id="fa2f6-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-201">Konferenzanruf</span><span class="sxs-lookup"><span data-stu-id="fa2f6-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-202">Sirene</span><span class="sxs-lookup"><span data-stu-id="fa2f6-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-203">3,72</span><span class="sxs-lookup"><span data-stu-id="fa2f6-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2f6-204">UC-PSTN-Anruf</span><span class="sxs-lookup"><span data-stu-id="fa2f6-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-205">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="fa2f6-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-206">2,95</span><span class="sxs-lookup"><span data-stu-id="fa2f6-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2f6-207">UC-PSTN-Anruf</span><span class="sxs-lookup"><span data-stu-id="fa2f6-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-208">G-711</span><span class="sxs-lookup"><span data-stu-id="fa2f6-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="fa2f6-209">3,61</span><span class="sxs-lookup"><span data-stu-id="fa2f6-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa2f6-210">Neben den vorherigen proaktiven Überwachungsaktivitäten sollten Wartungsaufgaben für zentrale, Edge-und Zweigstellenstandorte auf einer wiederkehrenden täglichen, wöchentlichen und monatlichen Basis gemäß der Definition im lync RA-Betriebshandbuch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa2f6-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

