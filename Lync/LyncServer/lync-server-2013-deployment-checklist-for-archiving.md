---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung'
description: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung.'
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
ms.openlocfilehash: 0e9fb3085950aa1e8a750d36a0aeb8592bc18113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557711"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="45aee-103">Prüfliste zur Bereitstellung für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45aee-103">Deployment checklist for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45aee-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="45aee-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="45aee-105">Die Archivierung wird automatisch auf jedem Front-End-Server in ihrer lync Server 2013-Bereitstellung installiert, Sie müssen Sie jedoch noch einrichten, bevor Sie Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="45aee-105">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="45aee-106">Die in diesem Abschnitt zusammengefassten Schritte, die für die Einrichtung erforderlich sind, umfassen die Bereitstellung der Archivierung.</span><span class="sxs-lookup"><span data-stu-id="45aee-106">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="45aee-107">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="45aee-107">Deployment Sequence</span></span>

<span data-ttu-id="45aee-108">Die Einrichtung der Archivierung ist abhängig von der jeweiligen Speicheroption:</span><span class="sxs-lookup"><span data-stu-id="45aee-108">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="45aee-109">Wenn Sie Microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie lync Server 2013 Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="45aee-109">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="45aee-110">Konfigurieren Sie stattdessen Ihre Exchange In-Place Hold-Richtlinien zur Unterstützung der Archivierung für Benutzer, die in Exchange 2013 verwaltet werden und deren Postfächer In-Place aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="45aee-110">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="45aee-111">Ausführliche Informationen zum Konfigurieren dieser Richtlinien finden Sie in der Exchange 2013-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-111">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="45aee-112">Wenn Sie Microsoft Exchange Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie lync Server Archivierungsdatenbanken (SQL Server Datenbanken) zu Ihrer Topologie hinzufügen und diese dann veröffentlichen sowie Richtlinien und Einstellungen für Ihre Benutzer konfigurieren, bevor Sie Daten für diese Benutzer archivieren können.</span><span class="sxs-lookup"><span data-stu-id="45aee-112">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="45aee-113">Sie können Archivierungsdatenbanken gleichzeitig bereitstellen, wenn Sie die anfängliche Topologie bereitstellen oder nachdem Sie mindestens eine Front-End-Pool oder Standard Edition-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="45aee-113">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="45aee-114">In diesem Dokument wird beschrieben, wie Sie Archivierungsdatenbanken bereitstellen, indem Sie Sie einer vorhandenen Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="45aee-114">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="45aee-p104">Wenn Sie die Archivierung in einem Front-End-Pool oder auf einem Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, kann möglicherweise die gesamte Sitzung nicht archiviert werden. In diesen Fällen können Sofortnachrichten mit archivierungsfähigen Benutzern trotzdem archiviert werden. Für Konferenzinhaltdateien sowie für den Beitritt bzw. das Verlassen einer Konferenz ist dies jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="45aee-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45aee-119">Wenn die Archivierung aus Kompatibilitätsgründen in Ihrer Organisation kritisch ist, müssen Sie die Archivierung bereitstellen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und diese für alle entsprechenden Benutzer aktivieren, bevor Sie diese Benutzer für lync Server 2013 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="45aee-119">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="45aee-120">Archivierungsbereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="45aee-120">Archiving Deployment Process</span></span>

<span data-ttu-id="45aee-121">Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="45aee-121">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45aee-122">Phase</span><span class="sxs-lookup"><span data-stu-id="45aee-122">Phase</span></span></th>
<th><span data-ttu-id="45aee-123">Schritte</span><span class="sxs-lookup"><span data-stu-id="45aee-123">Steps</span></span></th>
<th><span data-ttu-id="45aee-124">Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="45aee-124">Roles and group memberships</span></span></th>
<th><span data-ttu-id="45aee-125">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="45aee-125">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45aee-126"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="45aee-126"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="45aee-127">Wenn Sie Microsoft Exchange Integration (mithilfe von Exchange 2013 für Archivierungsspeicher für einige oder alle Benutzer) verwenden möchten, benötigen Sie eine vorhandene Exchange 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="45aee-127">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="45aee-128">Wenn Sie separate Archivierungsdatenbanken (Verwendung von SQL Server-Datenbanken) als Archivierungsspeicher für einige oder alle Benutzer verwenden möchten, muss SQL Server auf dem Server ausgeführt werden, auf dem die Archivierungsdaten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="45aee-128">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="45aee-p105">Die Archivierung wird auf Front-End-Servern in einem Enterprise-Pool und Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.</span><span class="sxs-lookup"><span data-stu-id="45aee-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="45aee-131">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="45aee-131">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="45aee-132"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-132"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="45aee-133"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-133"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="45aee-134"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-134"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="45aee-135"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Einrichten von Systemen und Infrastruktur für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-135"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="45aee-136"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Unterstützung von Exchange Server und SharePoint-Integration in lync Server 2013</a> in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-136"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45aee-137"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur, wenn keine Microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung verwendet wird)</strong></span><span class="sxs-lookup"><span data-stu-id="45aee-137"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="45aee-138">Führen Sie den Topologie-Generator aus, um der Topologie lync Server 2013 Archivierungsdatenbanken (SQL Server-Datenbanken) hinzuzufügen, und veröffentlichen Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="45aee-138">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="45aee-139">Zum Definieren einer Topologie für die Einbindung von Archivierungsdatenbanken; ein Konto, das Mitglied der Gruppe der lokalen Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="45aee-139">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="45aee-140">So veröffentlichen Sie die Topologie, ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und die über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die Dateifreigabe verfügt, die für den lync Server 2013 Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</span><span class="sxs-lookup"><span data-stu-id="45aee-140">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="45aee-141"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen lync Server 2013-Bereitstellung</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-141"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45aee-142"><strong>Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung Microsoft Exchange Integration)</strong></span><span class="sxs-lookup"><span data-stu-id="45aee-142"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="45aee-143">Konfigurieren von Servern, um die Authentifizierung zwischen lync Server 2013 und Exchange 2013 zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="45aee-143">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="45aee-144">Es wird empfohlen, die Exchange-Archivierungsspeicher Konnektivität vor dem Aktivieren der Archivierung mit <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – Folder Container</strong> zu validieren.</span><span class="sxs-lookup"><span data-stu-id="45aee-144">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="45aee-145">Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.</span><span class="sxs-lookup"><span data-stu-id="45aee-145">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="45aee-146"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</a> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-146"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45aee-147"><strong>Konfigurieren von Archivierungsrichtlinien und -konfigurationen</strong></span><span class="sxs-lookup"><span data-stu-id="45aee-147"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="45aee-148">Konfigurieren Sie die Archivierung, einschließlich der Frage, ob Sie Microsoft Exchange Integration, die globale Richtlinie und alle Standort-und Benutzerrichtlinien verwenden möchten (wenn Sie nicht die Microsoft Exchange Integration für alle Datenspeicher verwenden), sowie bestimmte Archivierungsoptionen, beispielsweise den kritischen Modus und den Datenexport und das Löschen.</span><span class="sxs-lookup"><span data-stu-id="45aee-148">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="45aee-149">Wenn Sie Microsoft Exchange Integration verwenden, konfigurieren Sie die Exchange In-Place-Aufbewahrungsrichtlinien entsprechend.</span><span class="sxs-lookup"><span data-stu-id="45aee-149">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="45aee-150">Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“</span><span class="sxs-lookup"><span data-stu-id="45aee-150">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="45aee-151"><a href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45aee-151"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="45aee-152">Exchange-Produktdokumentation (bei Verwendung Microsoft Exchange Integration).</span><span class="sxs-lookup"><span data-stu-id="45aee-152">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="45aee-153">Bereitstellen von lync Server und Microsoft Exchange in unterschiedlichen Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="45aee-153">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="45aee-154">Wenn Exchange Server nicht in derselben Gesamtstruktur wie lync Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert sind, in der lync Server bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="45aee-154">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="45aee-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="45aee-155">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="45aee-156">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45aee-156">proxyAddresses</span></span>

<span data-ttu-id="45aee-p107">Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen, nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="45aee-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

