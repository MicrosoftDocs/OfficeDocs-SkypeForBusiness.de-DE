---
title: 'Lync Server 2013: Vorbereiten von Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b3af3ce7940b8d0fb58a74b4a8f7bb0a21c5e2d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506992"
---
# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="12d09-102">Vorbereiten Active Directory-Domänendienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d09-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12d09-103">_**Letztes Änderungsstand des Themas:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="12d09-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="12d09-104">In lync Server 2013 können Sie den lync Server-Bereitstellungs-Assistenten verwenden, um Active Directory-Domänendienste vorzubereiten, oder Sie können lync Server-Verwaltungsshell-Cmdlets direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="12d09-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="12d09-105">Darüber hinaus können Sie das Befehlszeilentool "ldifde.exe" direkt für Ihre Domänencontroller ausführen, wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12d09-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="12d09-106">Der Assistent für die lync Server-Bereitstellung führt Sie durch jede Active Directory Vorbereitungs Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="12d09-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="12d09-107">Der Bereitstellungs-Assistent führt lync Server-Verwaltungsshell-Cmdlets aus.</span><span class="sxs-lookup"><span data-stu-id="12d09-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="12d09-108">Dieses Tool eignet sich für Umgebungen mit einer einzelnen Domäne und einer Topologie mit einer einzelnen Gesamtstruktur oder einer ähnlichen Topologie.</span><span class="sxs-lookup"><span data-stu-id="12d09-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12d09-109">Sie können lync Server in einer Gesamtstruktur oder Domäne bereitstellen, in der Domänencontroller 32-Bit-Versionen einiger Betriebssysteme ausführen (Ausführliche Informationen finden Sie unter <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure Requirements for lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="12d09-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="12d09-110">Sie können jedoch nicht den lync Server-Bereitstellungs-Assistenten verwenden, um Schema-, Gesamtstruktur-und Domänenvorbereitung in diesen Umgebungen auszuführen, da der Bereitstellungs-Assistent und die unterstützenden Dateien nur 64-Bit sind.</span><span class="sxs-lookup"><span data-stu-id="12d09-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="12d09-111">Stattdessen können Sie auf einem 32-Bit-Domänencontroller "ldifde.exe" und die zugehörigen IDF-Dateien verwenden, um das Schema, die Gesamtstruktur und die Domäne vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="12d09-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="12d09-112">Weitere Informationen finden Sie im Abschnitt "Verwenden von Cmdlets und 'Ldifde.exe'" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="12d09-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="12d09-113">Sie können lync Server-Verwaltungsshell-Cmdlets verwenden, um Aufgaben Remote oder für komplexere Umgebungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12d09-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="12d09-114">Voraussetzungen für die Active Directory-Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="12d09-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="12d09-115">Sie müssen Active Directory Vorbereitungsschritte auf einem Computer ausführen, auf dem Windows Server 2012, Windows Server 2012 R2 oder Windows Server 2008 R2 mit SP1 (64-Bit) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12d09-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="12d09-116">Für Active Directory Vorbereitung sind lync Server-Verwaltungsshell und OCSCore erforderlich.</span><span class="sxs-lookup"><span data-stu-id="12d09-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="12d09-117">Zur Ausführung der Active Directory-Vorbereitungsaufgaben sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="12d09-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="12d09-118">Lync Server Kernkomponenten (OCScore.msi)</span><span class="sxs-lookup"><span data-stu-id="12d09-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12d09-119">Wenn Sie lync Server-Verwaltungsshell für die Active Directory Vorbereitung verwenden möchten, müssen Sie zuerst den lync Server-Bereitstellungs-Assistenten ausführen, um Hauptkomponenten zu installieren.</span><span class="sxs-lookup"><span data-stu-id="12d09-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="12d09-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="12d09-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12d09-121">Für Windows Server 2012 und Windows Server 2012 R2 installieren und aktivieren Sie .NET Framework 4.5 mit dem Server-Manager.</span><span class="sxs-lookup"><span data-stu-id="12d09-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="12d09-122">Ausführliche Informationen finden Sie unter "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">zusätzlichen Softwareanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="12d09-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="12d09-123">Laden Sie für Windows Server &nbsp; 2008 &nbsp; R2 <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> von der Microsoft-Website herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="12d09-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="https://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="12d09-124">Remoteserver-Verwaltungstools (RSAT)</span><span class="sxs-lookup"><span data-stu-id="12d09-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12d09-125">Wenn Sie die Schritte zur Active Directory-Vorbereitung nicht auf einem Domänencontroller, sondern auf einem Mitgliedsserver ausführen, werden einige Remoteserver-Verwaltungstools benötigt.</span><span class="sxs-lookup"><span data-stu-id="12d09-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="12d09-126">Installieren Sie die AD DS-Snap-Ins und Befehlszeilentools sowie das Active Directory-Modul für Windows PowerShell aus dem Knoten AD DS und AD LDS-Tools im Server-Manager.</span><span class="sxs-lookup"><span data-stu-id="12d09-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="12d09-127">Microsoft Visual C++ 11 Redistributable</span><span class="sxs-lookup"><span data-stu-id="12d09-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12d09-p107">Wenn diese erforderliche Komponente noch nicht auf dem Computer installiert ist, werden Sie beim Ausführen von Setup zur Installation aufgefordert. Das Paket wird Ihnen zur Verfügung gestellt, sodass Sie es nicht separat erwerben müssen.</span><span class="sxs-lookup"><span data-stu-id="12d09-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="12d09-130">Windows PowerShell 3,0 (64-Bit)</span><span class="sxs-lookup"><span data-stu-id="12d09-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="12d09-131">Für Windows Server 2012 und Windows Server 2012 R2 sollte Windows PowerShell 3,0 in ihrer lync Server 2013 Installation enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="12d09-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="12d09-132">Für Windows Server 2008 R2 müssen Sie Windows PowerShell 3,0 installieren oder ein Upgrade darauf durchführen.</span><span class="sxs-lookup"><span data-stu-id="12d09-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="12d09-133">Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="12d09-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="12d09-134">Administratorrechte und -rollen</span><span class="sxs-lookup"><span data-stu-id="12d09-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="12d09-135">In der folgenden Tabelle sind die Administratorrechte und -rollen aufgeführt, die für die einzelnen Aufgaben zur Active Directory-Vorbereitung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="12d09-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="12d09-136">Erforderliche Benutzerrechte für die Vorbereitung von Active Directory</span><span class="sxs-lookup"><span data-stu-id="12d09-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12d09-137">Verfahren</span><span class="sxs-lookup"><span data-stu-id="12d09-137">Procedure</span></span></th>
<th><span data-ttu-id="12d09-138">Rechte oder Rollen</span><span class="sxs-lookup"><span data-stu-id="12d09-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12d09-139">Schemavorbereitung</span><span class="sxs-lookup"><span data-stu-id="12d09-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="12d09-140">Mitglied der Gruppe "Schema-Admins" für die Stammdomäne einer Gesamtstruktur und Administratorrechte für den Schemamaster</span><span class="sxs-lookup"><span data-stu-id="12d09-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12d09-141">Gesamtstrukturvorbereitung</span><span class="sxs-lookup"><span data-stu-id="12d09-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="12d09-142">Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="12d09-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12d09-143">Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="12d09-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="12d09-144">Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die angegebene Domäne</span><span class="sxs-lookup"><span data-stu-id="12d09-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="12d09-145">Cmdlets für die Active Directory-Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="12d09-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="12d09-146">In der folgenden Tabelle werden die lync Server-Verwaltungsshell-Cmdlets verglichen, mit denen AD DS auf die LcsCmd-Befehle zum Vorbereiten von AD DS in Microsoft Office Communications Server 2007 R2 vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="12d09-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="12d09-147">Cmdlets im Vergleich zu "LcsCmd"</span><span class="sxs-lookup"><span data-stu-id="12d09-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12d09-148">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="12d09-148">Cmdlets</span></span></th>
<th><span data-ttu-id="12d09-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="12d09-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12d09-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="12d09-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="12d09-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="12d09-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12d09-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="12d09-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="12d09-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="12d09-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12d09-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="12d09-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="12d09-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="12d09-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12d09-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="12d09-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="12d09-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="12d09-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12d09-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="12d09-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="12d09-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="12d09-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12d09-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="12d09-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="12d09-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="12d09-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12d09-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="12d09-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="12d09-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="12d09-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12d09-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="12d09-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="12d09-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="12d09-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="12d09-166">Anforderungen für gesperrtes Active Directory</span><span class="sxs-lookup"><span data-stu-id="12d09-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="12d09-167">Wenn die Berechtigungsvererbung deaktiviert wurde oder Berechtigungen für authentifizierte Benutzer in der Organisation deaktiviert werden müssen, sind während der Domänenvorbereitung zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="12d09-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="12d09-168">Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="12d09-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="12d09-169">Berechtigungen für benutzerdefinierte Container</span><span class="sxs-lookup"><span data-stu-id="12d09-169">Custom Container Permissions</span></span>

<span data-ttu-id="12d09-170">Wenn in Ihrer Organisation statt der drei integrierten Container (Benutzer, Computer und Domänencontroller) benutzerdefinierte Container verwendet werden, muss die Gruppe der authentifizierten Benutzer über Lesezugriff für die benutzerdefinierten Container verfügen.</span><span class="sxs-lookup"><span data-stu-id="12d09-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="12d09-171">Der Lesezugriff auf die Container ist für die Domänenvorbereitung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="12d09-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="12d09-172">Ausführliche Informationen finden Sie unter [Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="12d09-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="12d09-173">Verwenden von Cmdlets und "Ldifde.exe"</span><span class="sxs-lookup"><span data-stu-id="12d09-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="12d09-174">Der Schritt **Schema vorbereiten** im lync Server-Bereitstellungs-Assistenten und das Cmdlet **install-CsAdServerSchema** erweitern das Active Directory Schema auf Domänencontrollern mit einem 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="12d09-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="12d09-175">Wenn Sie das Active Directory Schema auf einem Domänencontroller erweitern müssen, auf dem ein 32-Bit-Betriebssystem ausgeführt wird, können Sie das Cmdlet **install-CsAdServerSchema** Remote von einem Mitgliedsserver aus ausführen (empfohlener Ansatz).</span><span class="sxs-lookup"><span data-stu-id="12d09-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="12d09-176">Wenn Sie die Schemavorbereitung direkt auf dem Domänencontroller ausführen müssen, können Sie das Ldifde.exe-Tool verwenden, um die Schemadateien zu importieren.</span><span class="sxs-lookup"><span data-stu-id="12d09-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="12d09-177">Das Ldifde.exe-Tool umfasst die meisten Versionen des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="12d09-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="12d09-p112">Bei Verwendung von "Ldifde.exe" zum Importieren der Schemadateien, müssen Sie unabhängig davon, ob Sie eine Migration von einer vorherigen Version oder eine Neuinstallation ausführen, alle vier Dateien importieren. Die Dateien müssen mit der folgenden Reihenfolge importiert werden:</span><span class="sxs-lookup"><span data-stu-id="12d09-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="12d09-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="12d09-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="12d09-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="12d09-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="12d09-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="12d09-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="12d09-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="12d09-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12d09-184">Die vier IDF-Dateien befinden sich im Verzeichnis "\Support\Schema" des Installationsmediums oder Downloads.</span><span class="sxs-lookup"><span data-stu-id="12d09-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="12d09-185">Verwenden Sie das folgende Format, um "Ldifde.exe" zum Importieren der vier Schemadateien auf einem Domänencontroller zu verwenden, bei dem es sich um den Schemamaster handelt:</span><span class="sxs-lookup"><span data-stu-id="12d09-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="12d09-186">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="12d09-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="12d09-p113">Verwenden Sie den Parameter "b" nur, wenn Sie als ein anderer Benutzer angemeldet sind. Ausführliche Informationen zu den erforderlichen Benutzerrechten finden Sie im Abschnitt "Administratorrechte und -rollen" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="12d09-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="12d09-189">Verwenden Sie das folgende Format, um "Ldifde.exe" zum Importieren der vier Schemadateien auf einem Domänencontroller zu verwenden, bei dem es sich nicht um den Schemamaster handelt:</span><span class="sxs-lookup"><span data-stu-id="12d09-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="12d09-190">Ausführliche Informationen zur Verwendung von LDIFDE finden Sie im Microsoft Knowledge Base-Artikel 237677, "Verwenden von LDIFDE zum Importieren und Exportieren von Verzeichnisobjekten in Active Directory" unter [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204) .</span><span class="sxs-lookup"><span data-stu-id="12d09-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12d09-191">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="12d09-191">In This Section</span></span>

  - [<span data-ttu-id="12d09-192">Vorbereiten des Active Directory Schemas in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d09-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="12d09-193">Vorbereiten der Gesamtstruktur auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d09-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="12d09-194">Vorbereiten von Domänen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d09-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

