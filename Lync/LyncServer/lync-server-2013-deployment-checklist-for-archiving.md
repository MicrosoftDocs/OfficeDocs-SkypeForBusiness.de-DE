---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="15260-102">Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15260-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15260-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="15260-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="15260-104">Die Archivierung wird automatisch auf jedem Front-End-Server in ihrer lync Server 2013-Bereitstellung installiert, Sie müssen Sie aber noch einrichten, bevor Sie Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="15260-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="15260-105">Die erforderlichen Schritte zum Einrichten, wie in diesem Abschnitt zusammengefasst, stellen die Bereitstellung der Archivierung dar.</span><span class="sxs-lookup"><span data-stu-id="15260-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="15260-106">Bereitstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="15260-106">Deployment Sequence</span></span>

<span data-ttu-id="15260-107">Wie Sie die Archivierung einrichten, hängt davon ab, welche Speicheroption Sie auswählen:</span><span class="sxs-lookup"><span data-stu-id="15260-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="15260-108">Wenn Sie die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie die lync Server 2013-Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="15260-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="15260-109">Konfigurieren Sie stattdessen Ihre Exchange-in-situ-Speicherrichtlinien, um die Archivierung für Benutzer in Exchange 2013 zu unterstützen, wobei ihre Postfächer in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="15260-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="15260-110">Details zum Konfigurieren dieser Richtlinien finden Sie in der Exchange 2013-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15260-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="15260-111">Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Ihrer Topologie lync Server-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzufügen und dann veröffentlichen sowie Richtlinien und Einstellungen für Ihre Benutzer konfigurieren, bevor Sie Archivieren Sie Daten für diese Benutzer.</span><span class="sxs-lookup"><span data-stu-id="15260-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="15260-112">Sie können Archivierungsdatenbanken zur gleichen Zeit bereitstellen, in der Sie Ihre anfängliche Topologie bereitstellen, oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="15260-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="15260-113">In diesem Dokument wird beschrieben, wie Archivierungsdatenbanken bereitgestellt werden, indem Sie einer vorhandenen Bereitstellung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="15260-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="15260-114">Wenn Sie die Archivierung in einem Front-End-Pool oder Standard Edition-Server aktivieren, sollten Sie Sie für alle anderen Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="15260-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="15260-115">Dies liegt daran, dass Benutzer, deren Kommunikation archiviert werden muss, zu einer Gruppenunterhaltung oder Besprechungen eingeladen werden können, die in einem anderen Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="15260-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="15260-116">Wenn die Archivierung in dem Pool, in dem die Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, wird die vollständige Sitzung möglicherweise nicht archiviert.</span><span class="sxs-lookup"><span data-stu-id="15260-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="15260-117">In diesen Fällen können IMS mit Archivierungs fähigen Benutzern weiterhin archiviert werden, jedoch nicht für Konferenz Inhaltsdateien und Konferenzteilnahme-oder Leave-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="15260-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15260-118">Wenn die Archivierung aus Kompatibilitätsgründen für Ihre Organisation wichtig ist, stellen Sie sicher, dass Sie die Archivierung bereitstellen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und für alle entsprechenden Benutzer aktivieren, bevor Sie diese Benutzer für lync Server 2013 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="15260-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="15260-119">Archivierungs Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="15260-119">Archiving Deployment Process</span></span>

<span data-ttu-id="15260-120">Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="15260-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15260-121">Phase</span><span class="sxs-lookup"><span data-stu-id="15260-121">Phase</span></span></th>
<th><span data-ttu-id="15260-122">Schritte</span><span class="sxs-lookup"><span data-stu-id="15260-122">Steps</span></span></th>
<th><span data-ttu-id="15260-123">Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="15260-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="15260-124">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="15260-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15260-125"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="15260-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="15260-126">Wenn Sie die Microsoft Exchange-Integration (mit Exchange 2013 für die Archivierung von Speicher für einige oder alle Benutzer) verwenden möchten, benötigen Sie eine vorhandene Exchange 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="15260-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="15260-127">So verwenden Sie separate Archivierungsdatenbanken (mithilfe von SQL Server-Datenbanken) zum Archivieren von Speicher für einige oder alle Benutzer, SQL Server auf dem Server, auf dem Archivierungsdaten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="15260-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="15260-128">Die Archivierung wird auf Front-End-Servern eines Enterprise-Pools und von Standard Edition-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15260-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="15260-129">Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.</span><span class="sxs-lookup"><span data-stu-id="15260-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="15260-130">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="15260-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="15260-131"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="15260-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="15260-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung für Server Software und-Infrastruktur in lync Server 2013</a> in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="15260-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="15260-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15260-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="15260-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Einrichten von Systemen und Infrastruktur für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="15260-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="15260-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Unterstützung für Exchange Server und SharePoint-Integration in lync Server 2013</a> in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="15260-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15260-136"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur, wenn Sie nicht die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden)</strong></span><span class="sxs-lookup"><span data-stu-id="15260-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="15260-137">Führen Sie den Topologie-Generator aus, um der Topologie lync Server 2013-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzuzufügen, und veröffentlichen Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="15260-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="15260-138">So definieren Sie eine Topologie für die Integration von Archivierungsdatenbanken: ein Konto, das ein Mitglied der lokalen Benutzergruppe ist.</span><span class="sxs-lookup"><span data-stu-id="15260-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="15260-139">So veröffentlichen Sie die Topologie: ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und das Vollzugriffsberechtigungen (Lesen/Schreiben/ändern) für die Dateifreigabe hat, die für den lync Server 2013-Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</span><span class="sxs-lookup"><span data-stu-id="15260-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="15260-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen lync Server 2013-Bereitstellung</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="15260-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15260-141"><strong>Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung der Microsoft Exchange-Integration)</strong></span><span class="sxs-lookup"><span data-stu-id="15260-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="15260-142">Konfigurieren Sie Server, um die Authentifizierung zwischen lync Server 2013 und Exchange 2013 zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="15260-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="15260-143">Wir empfehlen die Ausführung von <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – Ordner Papierkorb</strong> , um die Exchange-Archivierungsspeicher Konnektivität zu überprüfen, bevor die Archivierung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="15260-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="15260-144">Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.</span><span class="sxs-lookup"><span data-stu-id="15260-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="15260-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</a> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15260-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15260-146"><strong>Konfigurieren von Archivierungsrichtlinien und-Konfigurationen</strong></span><span class="sxs-lookup"><span data-stu-id="15260-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="15260-147">Konfigurieren Sie die Archivierung, einschließlich der Frage, ob Sie die Microsoft Exchange-Integration, die globale Richtlinie und alle Website-und Benutzerrichtlinien verwenden möchten (wenn Sie die Microsoft Exchange-Integration nicht für alle Datenspeicher verwenden), und bestimmte Archivierungsoptionen wie kritischer Modus und Daten Exportieren und bereinigen.</span><span class="sxs-lookup"><span data-stu-id="15260-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="15260-148">Wenn Sie die Microsoft Exchange-Integration verwenden, konfigurieren Sie Exchange-in-situ-Speicherrichtlinien nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="15260-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="15260-149">Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“</span><span class="sxs-lookup"><span data-stu-id="15260-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="15260-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="15260-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="15260-151">Exchange-Produktdokumentation (bei Verwendung der Microsoft Exchange-Integration).</span><span class="sxs-lookup"><span data-stu-id="15260-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="15260-152">Bereitstellen von lync Server und Microsoft Exchange in verschiedenen Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="15260-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="15260-153">Wenn Microsoft Exchange Server nicht in derselben Gesamtstruktur wie lync Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert werden, in der lync Server bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="15260-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="15260-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="15260-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="15260-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="15260-155">proxyAddresses</span></span>

<span data-ttu-id="15260-p107">Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen und nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="15260-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

