---
title: 'Lync Server 2013: Vorbereiten der Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="090ac-102">Vorbereiten der Active Directory-Domänendienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090ac-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="090ac-103">_**Letztes Änderungsdatum des Themas:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="090ac-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="090ac-104">In lync Server 2013 können Sie den lync Server-Bereitstellungs-Assistenten verwenden, um Active Directory-Domänendienste vorzubereiten, oder Sie können Cmdlets für die lync Server-Verwaltungsshell direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="090ac-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="090ac-105">Sie können das Befehlszeilentool Ldifde. exe auch direkt auf Ihren Domänencontrollern verwenden, wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="090ac-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="090ac-106">Der lync Server-Bereitstellungs-Assistent führt Sie durch die einzelnen Active Directory-Vorbereitungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="090ac-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="090ac-107">Der Bereitstellungs-Assistent führt Cmdlets der lync Server-Verwaltungsshell aus.</span><span class="sxs-lookup"><span data-stu-id="090ac-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="090ac-108">Dieses Tool eignet sich für Umgebungen mit einer einzelnen Domäne und einer einzelnen Gesamtstrukturtopologie oder einer anderen ähnlichen Topologie.</span><span class="sxs-lookup"><span data-stu-id="090ac-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="090ac-109">Sie können lync Server in einer Gesamtstruktur oder Domäne bereitstellen, auf der Domänencontroller 32-Bit-Versionen einiger Betriebssysteme ausführen (Einzelheiten finden Sie unter <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory-Infrastrukturanforderungen für lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="090ac-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="090ac-110">Sie können den lync Server-Bereitstellungs-Assistenten jedoch nicht verwenden, um Schema-, Gesamtstruktur-und Domänenvorbereitung in diesen Umgebungen auszuführen, da der Bereitstellungs-Assistent und die unterstützenden Dateien nur 64-Bit sind.</span><span class="sxs-lookup"><span data-stu-id="090ac-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="090ac-111">Stattdessen können Sie Ldifde. exe und die zugehörigen LDF-Dateien auf einem 32-Bit-Domänencontroller verwenden, um das Schema, die Gesamtstruktur und die Domäne vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="090ac-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="090ac-112">Weitere Informationen finden Sie im Abschnitt "Verwenden von Cmdlets und Ldifde. exe" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="090ac-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="090ac-113">Sie können Cmdlets der lync Server-Verwaltungsshell verwenden, um Aufgaben Remote oder für komplexere Umgebungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="090ac-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="090ac-114">Voraussetzungen für die Active Directory-Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="090ac-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="090ac-115">Sie müssen Active Directory-Vorbereitungsschritte auf einem Computer ausführen, auf dem Windows Server 2012, Windows Server 2012 R2 oder Windows Server 2008 R2 mit SP1 (64-Bit) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="090ac-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="090ac-116">Für die Active Directory-Vorbereitung ist die lync Server-Verwaltungsshell und OCSCore erforderlich.</span><span class="sxs-lookup"><span data-stu-id="090ac-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="090ac-117">Zum Ausführen von Active Directory-Vorbereitungsaufgaben sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="090ac-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="090ac-118">Lync Server Core Components (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="090ac-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="090ac-119">Wenn Sie beabsichtigen, die lync Server-Verwaltungsshell für die Active Directory-Vorbereitung zu verwenden, müssen Sie zuerst den lync Server-Bereitstellungs-Assistenten ausführen, um Kernkomponenten zu installieren.</span><span class="sxs-lookup"><span data-stu-id="090ac-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="090ac-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="090ac-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="090ac-121">Für Windows Server 2012 und Windows Server 2012 R2 installieren und aktivieren Sie .NET Framework 4,5 mithilfe des Server-Managers.</span><span class="sxs-lookup"><span data-stu-id="090ac-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="090ac-122">Ausführliche Informationen finden Sie unter "Microsoft .NET Framework 4,5" unter <A href="lync-server-2013-additional-software-requirements.md">zusätzliche Softwareanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="090ac-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="090ac-123">Für Windows Server&nbsp;2008&nbsp;R2 laden Sie <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> von der Microsoft-Website herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="090ac-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="090ac-124">Remote Server-Verwaltungs Tools (Remote Server)</span><span class="sxs-lookup"><span data-stu-id="090ac-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="090ac-125">Einige Tools für Remotetools sind erforderlich, wenn Sie Active Directory-Vorbereitungsschritte auf einem Mitgliedsserver statt auf einem Domänencontroller ausführen.</span><span class="sxs-lookup"><span data-stu-id="090ac-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="090ac-126">Installieren Sie die AD DS-Snap-Ins und-Befehlszeilentools sowie das Active Directory-Modul für Windows PowerShell über den Knoten AD DS und AD LDS-Tools im Server-Manager.</span><span class="sxs-lookup"><span data-stu-id="090ac-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="090ac-127">Microsoft Visual C++ 11 Redistributable</span><span class="sxs-lookup"><span data-stu-id="090ac-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="090ac-128">Setup fordert Sie auf, diese Voraussetzungen zu installieren, wenn Sie noch nicht auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="090ac-128">Setup prompts you to install this prerequisite if it is not already installed on the computer.</span></span> <span data-ttu-id="090ac-129">Das Paket wird für Sie bereitgestellt, und Sie müssen es nicht separat erwerben.</span><span class="sxs-lookup"><span data-stu-id="090ac-129">The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="090ac-130">Windows PowerShell 3,0 (64-Bit)</span><span class="sxs-lookup"><span data-stu-id="090ac-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="090ac-131">Für Windows Server 2012 und Windows Server 2012 R2 sollte Windows PowerShell 3,0 in ihrer lync Server 2013-Installation enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="090ac-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="090ac-132">Für Windows Server 2008 R2 müssen Sie Windows PowerShell 3,0 installieren oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="090ac-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="090ac-133">Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="090ac-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="090ac-134">Administrator Rechte und-Rollen</span><span class="sxs-lookup"><span data-stu-id="090ac-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="090ac-135">In der folgenden Tabelle sind die Administratorrechte und-Rollen aufgeführt, die für die einzelnen Active Directory-Vorbereitungsaufgaben erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="090ac-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="090ac-136">Für die Active Directory-Vorbereitung erforderliche Benutzerrechte</span><span class="sxs-lookup"><span data-stu-id="090ac-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="090ac-137">Verfahren</span><span class="sxs-lookup"><span data-stu-id="090ac-137">Procedure</span></span></th>
<th><span data-ttu-id="090ac-138">Rechte oder Rollen</span><span class="sxs-lookup"><span data-stu-id="090ac-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="090ac-139">Schema Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="090ac-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="090ac-140">Mitglied der Gruppe "Schemaadministratoren" für die Gesamtstruktur-Stammdomäne und Administratorrechte für den Schemamaster</span><span class="sxs-lookup"><span data-stu-id="090ac-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="090ac-141">Gesamtstrukturvorbereitung</span><span class="sxs-lookup"><span data-stu-id="090ac-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="090ac-142">Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="090ac-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="090ac-143">Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="090ac-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="090ac-144">Mitglied der Gruppe "Unternehmensadministratoren" oder "Domänen-Admins" für die angegebene Domäne</span><span class="sxs-lookup"><span data-stu-id="090ac-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="090ac-145">Cmdlets für die Active Directory-Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="090ac-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="090ac-146">In der folgenden Tabelle werden die Cmdlets der lync Server-Verwaltungsshell verglichen, die zum Vorbereiten von AD DS auf die LcsCmd-Befehle zum Vorbereiten von AD DS in Microsoft Office Communications Server 2007 R2 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="090ac-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="090ac-147">Cmdlets im Vergleich zu LcsCmd</span><span class="sxs-lookup"><span data-stu-id="090ac-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="090ac-148">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="090ac-148">Cmdlets</span></span></th>
<th><span data-ttu-id="090ac-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="090ac-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="090ac-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="090ac-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="090ac-151">LcsCmd/Forest/Action: SchemaPrep/SchemaType: Server</span><span class="sxs-lookup"><span data-stu-id="090ac-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="090ac-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="090ac-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="090ac-153">LcsCmd/Forest/Action: CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="090ac-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="090ac-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="090ac-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="090ac-155">LcsCmd/Forest/Action: ForestPrep</span><span class="sxs-lookup"><span data-stu-id="090ac-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="090ac-156">Deaktivieren-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="090ac-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="090ac-157">LcsCmd/Forest/Action: ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="090ac-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="090ac-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="090ac-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="090ac-159">LcsCmd/Forest/Action: CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="090ac-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="090ac-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="090ac-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="090ac-161">LcsCmd/Domain/Action: DomainPrep</span><span class="sxs-lookup"><span data-stu-id="090ac-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="090ac-162">Deaktivieren-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="090ac-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="090ac-163">LcsCmd/Domain/Action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="090ac-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="090ac-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="090ac-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="090ac-165">LcsCmd/Domain/Action: CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="090ac-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="090ac-166">Active Directory-Anforderungen gesperrt</span><span class="sxs-lookup"><span data-stu-id="090ac-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="090ac-167">Wenn die Vererbung von Berechtigungen deaktiviert ist oder die Berechtigungen für authentifizierte Benutzer in Ihrer Organisation deaktiviert werden müssen, müssen Sie während der Domänenvorbereitung weitere Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="090ac-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="090ac-168">Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="090ac-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="090ac-169">Benutzerdefinierte Container Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="090ac-169">Custom Container Permissions</span></span>

<span data-ttu-id="090ac-170">Wenn in Ihrer Organisation benutzerdefinierte Container anstelle der drei integrierten Container (also Benutzer, Computer und Domänencontroller) verwendet werden, müssen Sie den benutzerdefinierten Containern Lesezugriff für die Gruppe Authentifizierte Benutzer erteilen.</span><span class="sxs-lookup"><span data-stu-id="090ac-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="090ac-171">Für die Domänenvorbereitung ist Lesezugriff auf die Container erforderlich.</span><span class="sxs-lookup"><span data-stu-id="090ac-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="090ac-172">Ausführliche Informationen finden Sie unter [Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="090ac-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="090ac-173">Verwenden von Cmdlets und Ldifde. exe</span><span class="sxs-lookup"><span data-stu-id="090ac-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="090ac-174">Der Schritt " **Schema vorbereiten** " im lync Server-Bereitstellungs-Assistenten und dem Cmdlet " **install-CsAdServerSchema** " erweitern das Active Directory-Schema auf Domänencontrollern, auf denen ein 64-Bit-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="090ac-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="090ac-175">Wenn Sie das Active Directory-Schema auf einem Domänencontroller erweitern müssen, auf dem ein 32-Bit-Betriebssystem ausgeführt wird, können Sie das Cmdlet " **Installieren-CsAdServerSchema** " Remote von einem Mitgliedsserver ausführen (empfohlener Ansatz).</span><span class="sxs-lookup"><span data-stu-id="090ac-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="090ac-176">Wenn Sie die Schemavorbereitung aber direkt auf dem Domänencontroller ausführen müssen, können Sie die Schemadateien mit dem Tool "Ldifde. exe" importieren.</span><span class="sxs-lookup"><span data-stu-id="090ac-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="090ac-177">Das Tool "Ldifde. exe" umfasst die meisten Versionen des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="090ac-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="090ac-178">Wenn Sie die Schemadateien mithilfe von Ldifde. exe importieren, müssen Sie alle vier Dateien importieren, unabhängig davon, ob Sie eine frühere Version migrieren oder eine Neuinstallation durchführen.</span><span class="sxs-lookup"><span data-stu-id="090ac-178">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation.</span></span> <span data-ttu-id="090ac-179">Sie müssen Sie in der folgenden Reihenfolge importieren:</span><span class="sxs-lookup"><span data-stu-id="090ac-179">You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="090ac-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="090ac-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="090ac-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="090ac-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="090ac-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="090ac-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="090ac-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="090ac-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="090ac-184">Die vier LDF-Dateien befinden sich im \Support\Schema-Verzeichnis Ihres Installationsmediums oder herunterladen.</span><span class="sxs-lookup"><span data-stu-id="090ac-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="090ac-185">Wenn Sie Ldifde. exe verwenden möchten, um die vier Schemadateien auf einem Domänencontroller zu importieren, bei dem es sich um den Schemamaster handelt, verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="090ac-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="090ac-186">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="090ac-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="090ac-187">Verwenden Sie den Parameter b nur, wenn Sie als anderer Benutzer angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="090ac-187">Use the b parameter only if you are logged in as a different user.</span></span> <span data-ttu-id="090ac-188">Details zu den erforderlichen Benutzerrechten finden Sie weiter oben in diesem Thema im Abschnitt "Administrator Rechte und-Rollen".</span><span class="sxs-lookup"><span data-stu-id="090ac-188">For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="090ac-189">Wenn Sie Ldifde. exe verwenden möchten, um die vier Schemadateien auf einem Domänencontroller zu importieren, bei dem es sich nicht um den Schemamaster handelt, verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="090ac-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="090ac-190">Ausführliche Informationen zur Verwendung von LDIFDE finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)Microsoft Knowledge Base-Artikel 237677, "Verwenden von LDIFDE zum Importieren und Exportieren von Verzeichnisobjekten in Active Directory" unter.</span><span class="sxs-lookup"><span data-stu-id="090ac-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="090ac-191">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="090ac-191">In This Section</span></span>

  - [<span data-ttu-id="090ac-192">Vorbereiten des Active Directory-Schemas in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090ac-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="090ac-193">Vorbereiten der Gesamtstruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090ac-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="090ac-194">Vorbereiten von Domänen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090ac-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

