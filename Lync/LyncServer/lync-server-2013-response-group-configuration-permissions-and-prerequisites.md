---
title: 'Lync Server 2013: Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="a4287-102">Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4287-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4287-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a4287-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a4287-104">Response Group ist eine Enterprise-VoIP-anrufverwaltungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="a4287-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="a4287-105">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die Reaktionsgruppe und die administrativen Anmeldeinformationen und Berechtigungen konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="a4287-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="a4287-106">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur Reaktionsgruppe gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="a4287-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="a4287-107">Ausführliche Informationen finden Sie unter [Planen der Anruf Verwaltungsfeatures in lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a4287-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="a4287-108">Konfigurations Tools und Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="a4287-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="a4287-109">Sie können die folgenden Verwaltungstools verwenden, um die Reaktionsgruppe zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a4287-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="a4287-110">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a4287-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="a4287-111">Konfigurationstool für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="a4287-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="a4287-112">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="a4287-112">Lync Server Management Shell</span></span>

<span data-ttu-id="a4287-113">Für die Konfiguration von Reaktionsgruppen müssen Sie über mindestens eine der folgenden Administratorrollen verfügen:</span><span class="sxs-lookup"><span data-stu-id="a4287-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4287-114"><strong>Active Directory-Sicherheitsgruppe (1)</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="a4287-115">Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="a4287-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="a4287-116">Zuweisen eines Managers</span><span class="sxs-lookup"><span data-stu-id="a4287-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="a4287-117">Erstellen/Zuweisen von Agents und Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="a4287-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="a4287-118">Erstellen/Verwalten von Feiertagen und Geschäftszeiten</span><span class="sxs-lookup"><span data-stu-id="a4287-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="a4287-119">Workflow aktivieren/deaktivieren</span><span class="sxs-lookup"><span data-stu-id="a4287-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="a4287-120">Workflow konfigurieren (IVR-Gruppe oder Sammelanschlüsse)</span><span class="sxs-lookup"><span data-stu-id="a4287-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4287-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="a4287-122">√</span><span class="sxs-lookup"><span data-stu-id="a4287-122">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-123">√</span><span class="sxs-lookup"><span data-stu-id="a4287-123">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-124">√</span><span class="sxs-lookup"><span data-stu-id="a4287-124">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-125">√</span><span class="sxs-lookup"><span data-stu-id="a4287-125">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-126">√</span><span class="sxs-lookup"><span data-stu-id="a4287-126">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-127">√</span><span class="sxs-lookup"><span data-stu-id="a4287-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4287-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="a4287-129">√(2)</span><span class="sxs-lookup"><span data-stu-id="a4287-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="a4287-130">√(3)</span><span class="sxs-lookup"><span data-stu-id="a4287-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="a4287-131">√(3)</span><span class="sxs-lookup"><span data-stu-id="a4287-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="a4287-132">√(3)</span><span class="sxs-lookup"><span data-stu-id="a4287-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="a4287-133">√(3)</span><span class="sxs-lookup"><span data-stu-id="a4287-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4287-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="a4287-135">√</span><span class="sxs-lookup"><span data-stu-id="a4287-135">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-136">√</span><span class="sxs-lookup"><span data-stu-id="a4287-136">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-137">√</span><span class="sxs-lookup"><span data-stu-id="a4287-137">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-138">√</span><span class="sxs-lookup"><span data-stu-id="a4287-138">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-139">√</span><span class="sxs-lookup"><span data-stu-id="a4287-139">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-140">√</span><span class="sxs-lookup"><span data-stu-id="a4287-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4287-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="a4287-142">√</span><span class="sxs-lookup"><span data-stu-id="a4287-142">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-143">√</span><span class="sxs-lookup"><span data-stu-id="a4287-143">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-144">√</span><span class="sxs-lookup"><span data-stu-id="a4287-144">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-145">√</span><span class="sxs-lookup"><span data-stu-id="a4287-145">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-146">√</span><span class="sxs-lookup"><span data-stu-id="a4287-146">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-147">√</span><span class="sxs-lookup"><span data-stu-id="a4287-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4287-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="a4287-149">√</span><span class="sxs-lookup"><span data-stu-id="a4287-149">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-150">√</span><span class="sxs-lookup"><span data-stu-id="a4287-150">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-151">√</span><span class="sxs-lookup"><span data-stu-id="a4287-151">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-152">√</span><span class="sxs-lookup"><span data-stu-id="a4287-152">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-153">√</span><span class="sxs-lookup"><span data-stu-id="a4287-153">√</span></span></p></td>
<td><p><span data-ttu-id="a4287-154">√</span><span class="sxs-lookup"><span data-stu-id="a4287-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4287-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="a4287-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="a4287-156">√(4)</span><span class="sxs-lookup"><span data-stu-id="a4287-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="a4287-157">√(4)</span><span class="sxs-lookup"><span data-stu-id="a4287-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="a4287-158">√(4)</span><span class="sxs-lookup"><span data-stu-id="a4287-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="a4287-159">√(4)</span><span class="sxs-lookup"><span data-stu-id="a4287-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="a4287-160">√(4)</span><span class="sxs-lookup"><span data-stu-id="a4287-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="a4287-161">√(4)</span><span class="sxs-lookup"><span data-stu-id="a4287-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a4287-162"><STRONG>(1)</STRONG> ein Active Directory-Domänendienste-Benutzerobjekt muss ein Mitglied der angegebenen Active Directory-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="a4287-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="a4287-163">Ein Administrator oder ein anderes delegiertes Active Directory-Gruppenmitglied mit den entsprechenden Berechtigungen zum Hinzufügen von Benutzern zu einer Sicherheitsgruppe (beispielsweise Administrator, Kontooperatoren) muss ein Benutzerobjekt zur aufgelisteten Sicherheitsgruppe oder Gruppe hinzufügen, damit der Benutzer Führen Sie die aufgelisteten Funktionen aus.</span><span class="sxs-lookup"><span data-stu-id="a4287-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="a4287-164"><STRONG>(2)</STRONG> nur für Workflows, die der CsResponseGroupAdministrator dem CsResponseGroupManager zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="a4287-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="a4287-165"><STRONG>(3)</STRONG> ein Antwortgruppen-Manager kann einem Workflow, den der aktuelle Manager bereits verwaltet, ein weiteres Mitglied von CsResponseGroupManager zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a4287-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="a4287-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator kann nur "Get"-Cmdlets der lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4287-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="a4287-167">Voraussetzungen für die Reaktionsgruppen Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a4287-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="a4287-168">Für die Reaktionsgruppe sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a4287-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="a4287-169">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="a4287-169">Application service</span></span>

  - <span data-ttu-id="a4287-170">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="a4287-170">Response Group application</span></span>

  - <span data-ttu-id="a4287-171">Sprachpakete</span><span class="sxs-lookup"><span data-stu-id="a4287-171">Language packs</span></span>

  - <span data-ttu-id="a4287-172">Dateispeicher (für Audiodateien)</span><span class="sxs-lookup"><span data-stu-id="a4287-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="a4287-173">Webdienste (umfasst das Konfigurations Tool für Reaktionsgruppen und die Anmelde-und Abmelde Konsole des Agents)</span><span class="sxs-lookup"><span data-stu-id="a4287-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="a4287-174">Alle diese Komponenten werden standardmäßig installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a4287-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="a4287-175">Möglicherweise müssen Sie die folgenden Aufgaben ausführen, bevor Sie die Reaktionsgruppe konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a4287-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="a4287-176">Aktivieren von Benutzern für lync Server 2013 und Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="a4287-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="a4287-177">Ändern einer Konfigurationsdatei für FIPS-Konformität (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="a4287-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="a4287-178">Ändern der Datenbanksortierung für die Unterstützung von Yi-, Meng- und Zang-Zeichen für Warteschleifen- und Agentgruppennamen.</span><span class="sxs-lookup"><span data-stu-id="a4287-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="a4287-179">Aktivieren von Benutzern</span><span class="sxs-lookup"><span data-stu-id="a4287-179">Enabling Users</span></span>

<span data-ttu-id="a4287-180">Der erste Schritt beim Konfigurieren der Reaktionsgruppe besteht im Erstellen von Agentengruppen.</span><span class="sxs-lookup"><span data-stu-id="a4287-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="a4287-181">Bevor Sie eine Agentengruppe erstellen können, müssen Sie die Benutzer aktivieren, die Agents für die Reaktionsgruppe für lync Server 2013 und Enterprise-VoIP sein sollen.</span><span class="sxs-lookup"><span data-stu-id="a4287-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="a4287-182">Das Aktivieren von Benutzern für lync Server 2013 ist in der Regel ein Schritt in der Enterprise Edition-Server-oder Standard Edition-Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a4287-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="a4287-183">Details zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="a4287-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="a4287-184">Das Aktivieren von Benutzern für Enterprise-VoIP ist in der Regel ein Schritt in der Enterprise Voice-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a4287-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="a4287-185">Ausführliche Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="a4287-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="a4287-186">Erfüllen von FIPS-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4287-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="a4287-187">Dieser Abschnitt ist nur relevant, wenn Ihre Organisation FIPS-Konformität (Federal Information Processing Standards) sicherstellen muss.</span><span class="sxs-lookup"><span data-stu-id="a4287-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="a4287-188">Zur Einhaltung von FIPS müssen Sie die Datei „Web.config“ auf Anwendungsebene nach der Installation der Webdienste ändern, um einen anderen Kryptografiealgorithmus zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4287-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="a4287-189">Sie müssen angeben, dass ASP.NET zur Verarbeitung von Anzeigestatusdaten den 3DES-Algorithmus (Triple Data Encryption Standard) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4287-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="a4287-190">Für die reaktionsgruppenanwendung gilt diese Anforderung für das Reaktionsgruppen-Konfigurations Tool und die Agent-Anmeldung und-Abmelde Konsole.</span><span class="sxs-lookup"><span data-stu-id="a4287-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="a4287-191">Ausführliche Informationen zu dieser Anforderung finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)Microsoft Knowledge Base-Artikel 911722, "möglicherweise erhalten Sie eine Fehlermeldung, wenn Sie auf ASP.NET-Webseiten zugreifen, bei denen ViewState nach dem Upgrade von ASP.NET 1,1 auf ASP.NET 2,0" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a4287-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="a4287-192">Führen Sie zum Ändern der Datei „Web.config“ die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a4287-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="a4287-193">Öffnen Sie in einem Text-Editor (z. B. Editor) die Datei „Web.config“ auf Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="a4287-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="a4287-194">Suchen Sie in der Datei Web. config nach `<system.web>` dem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a4287-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="a4287-195">Fügen Sie im `<machineKey>` `<system.web>` Abschnitt den folgenden Abschnitt hinzu:</span><span class="sxs-lookup"><span data-stu-id="a4287-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="a4287-196">Speichern Sie die Datei „Web.config“.</span><span class="sxs-lookup"><span data-stu-id="a4287-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="a4287-197">Starten Sie den Dienst Internet Informationsdienste (IIS) neu, indem Sie an einer Eingabeaufforderung den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="a4287-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="a4287-198">Unterstützen von Yi-, Meng- und Zang-Zeichen</span><span class="sxs-lookup"><span data-stu-id="a4287-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="a4287-199">Dieser Abschnitt ist nur relevant, wenn Ihre Organisation Yi-, Meng- oder Zang-Zeichen unterstützen muss.</span><span class="sxs-lookup"><span data-stu-id="a4287-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4287-200">Informationen dazu, was die Zeichen Yi, Meng und Zang sind und warum Sie für Ihre Bereitstellung wichtig sein können, finden Sie in den Informationen zu den GB18030 <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>-Zeichensätzen.</span><span class="sxs-lookup"><span data-stu-id="a4287-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="a4287-p106">Um Yi-, Meng- oder Zang-Zeichen zu unterstützen, müssen Sie die Sortierung für die Rgsconfig-Datenbank ändern. Ändern Sie die Sortierung der Spalte **Name** in den folgenden Tabellen der einzelnen Rgsconfig-Datenbanken:</span><span class="sxs-lookup"><span data-stu-id="a4287-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="a4287-203">dbo.AgentGroups</span><span class="sxs-lookup"><span data-stu-id="a4287-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="a4287-204">dbo.BusinessHours</span><span class="sxs-lookup"><span data-stu-id="a4287-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="a4287-205">dbo.HolidaySets</span><span class="sxs-lookup"><span data-stu-id="a4287-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="a4287-206">dbo.Queues</span><span class="sxs-lookup"><span data-stu-id="a4287-206">dbo.Queues</span></span>

  - <span data-ttu-id="a4287-207">dbo.Workflows</span><span class="sxs-lookup"><span data-stu-id="a4287-207">dbo.Workflows</span></span>

<span data-ttu-id="a4287-208">Verwenden Sie für SQL Server 2008 R2 und SQL Server 2012 die Sortierung\_Latin\_General 100 (Akzent sensitiv).</span><span class="sxs-lookup"><span data-stu-id="a4287-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="a4287-209">Bei Verwendung dieser Sortierung wird die Groß-/Kleinschreibung bei Objektnamen nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="a4287-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="a4287-210">Die Sortierung kann über Microsoft SQL Server Management Studio geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a4287-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="a4287-211">Ausführliche Informationen zur Verwendung dieses Tools finden Sie unter "Verwenden von SQL Server Management Studio [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)" unter.</span><span class="sxs-lookup"><span data-stu-id="a4287-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="a4287-212">Führen Sie die folgenden Schritte aus, um die Sortierung zu ändern:</span><span class="sxs-lookup"><span data-stu-id="a4287-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="a4287-213">Stellen Sie sicher, dass SQL Server Management Studio zum Zulassen von Änderungen konfiguriert ist, für die Tabellen neu erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a4287-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="a4287-214">Ausführliche Informationen finden Sie unter "speichern (nicht zulässig)" im Dialog [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)Feld unter.</span><span class="sxs-lookup"><span data-stu-id="a4287-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="a4287-215">Details zum Festlegen einer Spaltensortierung finden Sie unter "so wird es gemacht: Festlegen der Spaltensortierung (Visual Database Tools [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185))" unter.</span><span class="sxs-lookup"><span data-stu-id="a4287-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="a4287-216">Stellen Sie unter Verwendung von Microsoft SQL Server Management Studio eine Verbindung mit der Rgsconfig-Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="a4287-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="a4287-217">Wechseln Sie in der Rgsconfig-Datenbank zu der Tabelle, die geändert werden soll, klicken Sie mit der rechten Maustaste auf die Tabelle und klicken Sie auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="a4287-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="a4287-218">Ändern Sie die Sortierung der Spalte **Name** und speichern Sie die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a4287-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

