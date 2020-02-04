---
title: 'Lync Server 2013: Sicherheits-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df13c5182d97534e32f0f4d383df73985907c8f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a><span data-ttu-id="5b1c9-102">Sicherheits-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b1c9-102">Security cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b1c9-103">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="5b1c9-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="5b1c9-104">Die Sicherheits-Cmdlets, die in Microsoft lync Server 2013 enthalten sind, werden in erster Linie zum Verwalten der Authentifizierung und von Benutzerrechten und-Berechtigungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b1c9-104">The security cmdlets included in Microsoft Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="5b1c9-105">Zum Verwalten der Authentifizierung stehen vielfältige Cmdlets zur Verfügung, darunter Cmdlets für die Zertifikat- und PIN-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b1c9-105">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="5b1c9-106">Darüber hinaus können Sie mithilfe einer Reihe von Cmdlets das neue Feature für die rollenbasierte Zugriffssteuerung verwenden, um die administrative Steuerung von lync Server zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="5b1c9-106">In addition, a number of cmdlets enable you to use the new role-based access control (RBAC) feature to delegate administrative control of Lync Server.</span></span>

<div>

## <a name="security-cmdlets"></a><span data-ttu-id="5b1c9-107">Sicherheits-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5b1c9-107">Security Cmdlets</span></span>

<span data-ttu-id="5b1c9-108">Viele Verwaltungsaufgaben, die für Sicherheitseinstellungen gelten, können über die lync Server-Systemsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b1c9-108">Many management tasks that apply to security settings can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="5b1c9-109">Eine der Haupt Ausnahmen sind die Cmdlets für Benutzerberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="5b1c9-109">One major exception is the user permission cmdlets.</span></span> <span data-ttu-id="5b1c9-110">Allerdings können alle Sicherheits Verwaltungsaufgaben mit Cmdlets aus der lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden. durch die Verwendung eines Skripts können Sie bestimmte Aufgaben automatisieren.</span><span class="sxs-lookup"><span data-stu-id="5b1c9-110">However, all security management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="5b1c9-111">Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung von Sicherheitseinstellungen beziehen:</span><span class="sxs-lookup"><span data-stu-id="5b1c9-111">The following is a list of cmdlets that relate directly to managing security settings:</span></span>

<span data-ttu-id="5b1c9-112">**[Zertifikat-und Authentifizierungs-Cmdlets in lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="5b1c9-112">**[Certificate and authentication cmdlets in Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-113">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-113">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-114">[Importieren-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-114">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-115">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-115">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-116">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-116">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-117">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-117">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-118">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-118">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-119">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-119">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-120">[REVOKE-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-120">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-121">[Sperren-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-121">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-122">[Satz-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-122">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-123">[Entsperren-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-123">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-124">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-124">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-125">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-125">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-132">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-132">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-133">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-133">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-134">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-134">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-135">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-135">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-136">[Satz-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-136">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-138">[Neu – CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-138">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-140">[Satz-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-140">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-141">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-141">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-142">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-142">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-143">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-143">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-144">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-144">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span></span>

<span data-ttu-id="5b1c9-145">**[Cmdlets für Benutzerrechte und Berechtigungen in lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="5b1c9-145">**[User rights and permissions cmdlets in Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-146">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-146">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-147">[Neu – CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-147">[New-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-148">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-148">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-149">[Satz-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-149">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-150">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-150">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-152">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-152">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-153">[REVOKE-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-153">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-154">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-154">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5b1c9-155">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-155">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-156">[REVOKE-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-156">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5b1c9-157">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-157">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span></span>

<span data-ttu-id="5b1c9-158">**[Interoperabilitäts-Cmdlets in lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="5b1c9-158">**[Interoperability cmdlets in Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**</span></span>

  - <span data-ttu-id="5b1c9-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="5b1c9-161">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-161">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-162">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-162">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-163">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-163">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-164">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-164">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="5b1c9-165">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-165">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-166">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-166">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="5b1c9-168">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5b1c9-168">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b1c9-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b1c9-169">See Also</span></span>


[<span data-ttu-id="5b1c9-170">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="5b1c9-170">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

