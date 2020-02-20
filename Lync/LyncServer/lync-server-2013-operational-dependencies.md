---
title: 'Lync Server 2013: Betriebs Abhängigkeiten'
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
ms.openlocfilehash: 9901d664f667dce2e669b9f20e040b6b2b7ff1a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="a962c-102">Betriebs Abhängigkeiten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a962c-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a962c-103">_**Letztes Änderungsstand des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a962c-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a962c-104">Die in diesem Dokument beschriebene Referenzarchitektur hilft sicherzustellen, dass Sie über eine lync Server 2013-Bereitstellung verfügen, die nicht nur auf die Anforderungen der Organisation skaliert, sondern gemäß den bewährten Methoden von Microsoft entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="a962c-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="a962c-105">Es kann sein, dass die lync Server 2013 Implementierung ein dynamischer Dienst ist und wie jeder andere Dienst im Unternehmen weiterhin eine Überwachung und proaktive Verwaltung benötigt, um dem Unternehmen hohe Serviceverfügbarkeit und Servicequalität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a962c-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="a962c-106">Da lync Server 2013 im täglichen Geschäft der Organisation tief verwurzelt ist, ist es wichtig, dass der Dienst durch eine präzise und greifbare Service Level-Verwaltung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="a962c-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="a962c-107">Die lync-Systemarchitektur kann komplex und sehr integriert werden, um ein effektives Service Level-Management beizubehalten und SLAs für lync Server 2013 einzurichten, um die Abhängigkeiten des Systems von anderen Plattformen und Servern zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="a962c-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="a962c-108">Ebenso wichtig ist es, festzustellen, welche Unternehmensdienste wie VoIP-und UC-integrierte Anwendungen von lync abhängig werden.</span><span class="sxs-lookup"><span data-stu-id="a962c-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="a962c-109">Lync Server 2013 muss festgestellt werden, wobei alle genannten Abhängigkeiten berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="a962c-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="a962c-110">Mit der Service Map können Sie eine SLA zwischen lync und dem dazugehörigen Dienst formulieren und einen Ausgangspunkt für die SLA-Aushandlung bieten.</span><span class="sxs-lookup"><span data-stu-id="a962c-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="a962c-111">In der folgenden Tabelle sind die typischen Abhängigkeitsdienste für eine lync-Infrastruktur aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a962c-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="a962c-112">Jede dieser Technologien sollte über eine eigene proaktive Überwachung verfügen.</span><span class="sxs-lookup"><span data-stu-id="a962c-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="a962c-113">Typische Abhängigkeitsdienste</span><span class="sxs-lookup"><span data-stu-id="a962c-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a962c-114">Abhängigkeitsdienst</span><span class="sxs-lookup"><span data-stu-id="a962c-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a962c-115">Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="a962c-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-116">Server Hardware</span><span class="sxs-lookup"><span data-stu-id="a962c-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-117">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="a962c-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-118">Öffentliche Schlüsselinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="a962c-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-119">Domänen Benennungsdienst</span><span class="sxs-lookup"><span data-stu-id="a962c-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-120">Datenbankdienste</span><span class="sxs-lookup"><span data-stu-id="a962c-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-121">Speicherdienste</span><span class="sxs-lookup"><span data-stu-id="a962c-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-122">System Verwaltung – Überwachung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="a962c-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-123">Sicherheitsdienste – Antivirus</span><span class="sxs-lookup"><span data-stu-id="a962c-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-124">Netzwerkinfrastruktur – Internet</span><span class="sxs-lookup"><span data-stu-id="a962c-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-125">Netzwerkinfrastruktur – intern (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="a962c-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-126">Telefonie-Infrastruktur – IP-PBX und Gateways</span><span class="sxs-lookup"><span data-stu-id="a962c-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-127">Cloud-Dienste</span><span class="sxs-lookup"><span data-stu-id="a962c-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a962c-128">Es wird davon ausgegangen, dass die Organisation operativ ausgereift ist, indem Sie grundlegende Service Level-Verwaltungsfunktionen wie Change, Incident and Release Management gemäß der vorgeschriebenen MOF-Funktion ausüben.</span><span class="sxs-lookup"><span data-stu-id="a962c-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="a962c-129">Die lync-Lösung sollte von diesen Funktionen übernommen werden und den gleichen betrieblichen Verwaltungsprozessen unterworfen werden.</span><span class="sxs-lookup"><span data-stu-id="a962c-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="a962c-130">Aufbauend auf den oben gewonnenen Informationen haben wir nun ein besseres Verständnis dafür, was sich auf den lync-Dienst im Unternehmen auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="a962c-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="a962c-131">Um die Verfügbarkeit und Qualität von lync Server 2013 Diensten sicherzustellen, müssen die folgenden Überwachungstools mit der Bereitstellung der Referenzarchitektur einhergehen:</span><span class="sxs-lookup"><span data-stu-id="a962c-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="a962c-132">Überwachungstools</span><span class="sxs-lookup"><span data-stu-id="a962c-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a962c-133">Komponente</span><span class="sxs-lookup"><span data-stu-id="a962c-133">Component</span></span></th>
<th><span data-ttu-id="a962c-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a962c-134">Description</span></span></th>
<th><span data-ttu-id="a962c-135">Zutreffende Website</span><span class="sxs-lookup"><span data-stu-id="a962c-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a962c-136">Lync Server 2013 Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="a962c-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="a962c-137">Stellen Sie mindestens eine lync Server 2013 Monitoring Server-Rolle pro zentraler Standort bereit, und konfigurieren Sie das QoE-Berichtspaket (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="a962c-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="a962c-138">Weitere Informationen finden Sie in der Dokumentation zur lync Server 2013-Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="a962c-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="a962c-139"><a href="lync-server-2013-deploying-monitoring.md">Bereitstellen der Überwachung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a962c-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a962c-140">Zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="a962c-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a962c-141">Binden Sie jeden Pool an die nächstgelegene Instanz der Monitoring Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="a962c-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="a962c-142">Zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="a962c-142">Central sites</span></span></p>
<p><span data-ttu-id="a962c-143">Zweigstellenstandorte</span><span class="sxs-lookup"><span data-stu-id="a962c-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a962c-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="a962c-145">System Center Operations Manager 2012, in dem das Microsoft lync Server 2013 Management Pack (MP) importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a962c-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="a962c-146">Das Management Pack implementiert herkömmliches Ereignisprotokoll und Leistungsindikator basierte Instrumentation wird verwendet und ermöglicht die neu verfügbare Instrumentation in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a962c-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="a962c-147">Zentrale Standorte</span><span class="sxs-lookup"><span data-stu-id="a962c-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a962c-148">Stellen Sie sicher, dass die zentrale Ermittlung der zu überwachenden Rollen und Komponenten automatisch basierend auf einem zentralen Ermittlungsskript ausgeführt wird, das das in der zentralen Verwaltungsdatenbank veröffentlichte Topologie-Dokument liest.</span><span class="sxs-lookup"><span data-stu-id="a962c-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="a962c-149">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-149">Central Site</span></span></p>
<p><span data-ttu-id="a962c-150">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="a962c-150">Branch Site</span></span></p>
<p><span data-ttu-id="a962c-151">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="a962c-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a962c-152">Bereitstellen von System Center Operations Manager 2007-Agents auf allen bereitgestellten Servern mit lync Server.</span><span class="sxs-lookup"><span data-stu-id="a962c-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="a962c-153">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-153">Central Site</span></span></p>
<p><span data-ttu-id="a962c-154">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="a962c-154">Branch Site</span></span></p>
<p><span data-ttu-id="a962c-155">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="a962c-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a962c-156">Stellen Sie sicher, dass priorisierte Warnungen für die Benachrichtigung konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="a962c-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="a962c-157">Warnungen mit hoher Priorität</span><span class="sxs-lookup"><span data-stu-id="a962c-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="a962c-158">Warnungen mittlerer Priorität</span><span class="sxs-lookup"><span data-stu-id="a962c-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="a962c-159">Andere Warnungen.</span><span class="sxs-lookup"><span data-stu-id="a962c-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="a962c-160">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-160">Central Site</span></span></p>
<p><span data-ttu-id="a962c-161">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="a962c-161">Branch Site</span></span></p>
<p><span data-ttu-id="a962c-162">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="a962c-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a962c-163">Konfigurieren Sie die Port Überwachung für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a962c-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="a962c-164">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-164">Central Site</span></span></p>
<p><span data-ttu-id="a962c-165">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="a962c-165">Branch Site</span></span></p>
<p><span data-ttu-id="a962c-166">Edge-Website</span><span class="sxs-lookup"><span data-stu-id="a962c-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a962c-167">Konfigurieren der URL-Überwachung für Ihre Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a962c-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="a962c-168">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-169">Integration von lync und System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a962c-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="a962c-170">Bereitstellen der Anruf Zuverlässigkeit und Medienqualität MonitoringCall Zuverlässigkeit und Medien Qualitätsüberwachung verwenden Sie den Monitoring Server Computer als Monitor Knoten, um die Anruf Zuverlässigkeit und Medienqualität von lync Server zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a962c-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="a962c-171">Beide Funktionen Abfrage der Monitoring Server Datenbanken zu tun Analyse.</span><span class="sxs-lookup"><span data-stu-id="a962c-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="a962c-172">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-172">Central Site</span></span></p>
<p><span data-ttu-id="a962c-173">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="a962c-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a962c-174">Stellen Sie sicher, dass die Warnschwellen für Medienqualität genau konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a962c-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="a962c-175">In der folgenden Tabelle werden die maximalen Netzwerk mittleren Meinungs Bewertungen nach Codec angegeben.</span><span class="sxs-lookup"><span data-stu-id="a962c-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="a962c-176">In der Produktion sollten diese Ergebnisse für einen festgelegten Zeitraum überwacht werden, und es müssen akzeptable Schwellenwerte basierend auf den jeweiligen NMOS-Ergebnissen der Organisation festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a962c-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="a962c-177">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-177">Central Site</span></span></p>
<p><span data-ttu-id="a962c-178">Zweigstellenstandort</span><span class="sxs-lookup"><span data-stu-id="a962c-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-179">Lync Server 2013er synthetischer Transaktionsmonitor</span><span class="sxs-lookup"><span data-stu-id="a962c-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="a962c-180">Stellen Sie eine dedizierte lync Server als synthetischen Transaktionsmonitor bereit.</span><span class="sxs-lookup"><span data-stu-id="a962c-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="a962c-181">Synthetische Transaktionen sind lync Server 2013 Windows PowerShell-Cmdlets, die vom Management Pack automatisch in einem vordefinierten Intervall ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="a962c-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="a962c-182">Diese werden auf einem Knoten mit synthetischen Transaktions Monitoren ausgeführt, der ein vom Administrator festgelegter Server ist, der für die Ermittlung und Ausführung von STS für jeden Pool zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="a962c-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="a962c-183">Es wird nicht empfohlen, einen vorhandenen Microsoft lync Server 2013 Server als synthetischen Transaktionsmonitor Knoten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a962c-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="a962c-184">Dies ist auf die hohen Anforderungen an die CPU/Arbeitsspeichernutzung für die Ausführung von STS zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="a962c-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="a962c-185">Verwenden Sie für den Knoten synthetischer Transaktionsmonitor einen neuen Server Computer (oder einen virtuellen Server).</span><span class="sxs-lookup"><span data-stu-id="a962c-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="a962c-186">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a962c-187">Bereitstellen des Monitor Knotens für synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="a962c-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="a962c-188">Lesen Sie das Dokument MonitoringCS_withSCOM. docx in der UCTAP Connect-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a962c-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="a962c-189">Zentraler Standort</span><span class="sxs-lookup"><span data-stu-id="a962c-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="a962c-190">Maximale Anzahl von Netzwerk-Mos-Bewertungen Pro Codec</span><span class="sxs-lookup"><span data-stu-id="a962c-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a962c-191">Szenario</span><span class="sxs-lookup"><span data-stu-id="a962c-191">Scenario</span></span></th>
<th><span data-ttu-id="a962c-192">Codec</span><span class="sxs-lookup"><span data-stu-id="a962c-192">Codec</span></span></th>
<th><span data-ttu-id="a962c-193">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="a962c-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a962c-194">UC-UC-Anruf</span><span class="sxs-lookup"><span data-stu-id="a962c-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a962c-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="a962c-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="a962c-196">4.10</span><span class="sxs-lookup"><span data-stu-id="a962c-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-197">UC-UC-Anruf</span><span class="sxs-lookup"><span data-stu-id="a962c-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a962c-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a962c-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a962c-199">2,95</span><span class="sxs-lookup"><span data-stu-id="a962c-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-200">Konferenzanruf</span><span class="sxs-lookup"><span data-stu-id="a962c-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="a962c-201">Sirene</span><span class="sxs-lookup"><span data-stu-id="a962c-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="a962c-202">3,72</span><span class="sxs-lookup"><span data-stu-id="a962c-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a962c-203">UC-PSTN-Anruf</span><span class="sxs-lookup"><span data-stu-id="a962c-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a962c-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a962c-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a962c-205">2,95</span><span class="sxs-lookup"><span data-stu-id="a962c-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a962c-206">UC-PSTN-Anruf</span><span class="sxs-lookup"><span data-stu-id="a962c-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a962c-207">G-711</span><span class="sxs-lookup"><span data-stu-id="a962c-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="a962c-208">3,61</span><span class="sxs-lookup"><span data-stu-id="a962c-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a962c-209">Neben den vorherigen proaktiven Überwachungsaktivitäten sollten Wartungsaufgaben für zentrale, Edge-und Zweigstellenstandorte auf einer wiederkehrenden täglichen, wöchentlichen und monatlichen Basis gemäß der Definition im lync RA-Betriebshandbuch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a962c-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

