---
title: 'Lync Server 2013: Gewähren von Setup Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61fb0f5eac11016cf21dd8691ed9fa5f97bc804f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="68f36-102">Erteilen von Setup Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f36-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f36-103">_**Letztes Änderungsstand des Themas:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="68f36-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="68f36-104">Mit dem Cmdlet **Grant-CsSetupPermission** können Sie der Gruppe "RTCUniversalServerAdmins" Lese-, Schreib-, ReadSPN- und WriteSPN-Berechtigungen für eine angegebene Organisationseinheit (Organizational Unit, OU) in Active Directory zuweisen.</span><span class="sxs-lookup"><span data-stu-id="68f36-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="68f36-105">Anschließend können Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser Organisationseinheit Server mit lync Server 2013 in der angegebenen Domäne installieren, ohne Mitglied der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="68f36-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="68f36-106">Verwenden Sie das Cmdlet **Test-CsSetupPermission** zum Überprüfen der Berechtigungen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** gewähren.</span><span class="sxs-lookup"><span data-stu-id="68f36-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="68f36-107">Mit dem Cmdlet **Revoke-CsSetupPermission** können Sie Berechtigungen entfernen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="68f36-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="68f36-108">So gewähren Sie Setupberechtigungen</span><span class="sxs-lookup"><span data-stu-id="68f36-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="68f36-109">Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="68f36-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="68f36-110">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="68f36-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="68f36-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="68f36-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68f36-112">Ausführen</span><span class="sxs-lookup"><span data-stu-id="68f36-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="68f36-p103">Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="68f36-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="68f36-116">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="68f36-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="68f36-117">So überprüfen Sie Setupberechtigungen</span><span class="sxs-lookup"><span data-stu-id="68f36-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="68f36-118">Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen überprüfen möchten, die Sie mit dem Cmdlet **Grant-CsSetupPermission** erteilt haben.</span><span class="sxs-lookup"><span data-stu-id="68f36-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="68f36-119">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="68f36-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="68f36-120">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="68f36-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68f36-121">Ausführen</span><span class="sxs-lookup"><span data-stu-id="68f36-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="68f36-p105">Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="68f36-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="68f36-125">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="68f36-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="68f36-126">So entziehen Sie Setupberechtigungen</span><span class="sxs-lookup"><span data-stu-id="68f36-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="68f36-127">Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen widerrufen möchten, die vom Cmdlet **Grant-CsSetupPermission** erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="68f36-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="68f36-128">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="68f36-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="68f36-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="68f36-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68f36-130">Ausführen</span><span class="sxs-lookup"><span data-stu-id="68f36-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="68f36-p107">Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="68f36-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="68f36-134">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="68f36-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

