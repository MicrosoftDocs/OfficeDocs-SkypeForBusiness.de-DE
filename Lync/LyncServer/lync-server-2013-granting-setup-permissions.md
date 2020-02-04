---
title: 'Lync Server 2013: Gewähren von Setupberechtigungen'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="64dec-102">Gewähren von Setupberechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64dec-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64dec-103">_**Letztes Änderungsdatum des Themas:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="64dec-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="64dec-104">Sie können das Cmdlet **Grant-CsSetupPermission** verwenden, um der RTCUniversalServerAdmins-Gruppe für eine angegebene Active Directory-Organisationseinheit (OU) Lese-, Schreib-, ReadSPN-und WriteSPN-Berechtigungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="64dec-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="64dec-105">Anschließend können Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU Server mit lync Server 2013 in der angegebenen Domäne installieren, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.</span><span class="sxs-lookup"><span data-stu-id="64dec-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="64dec-106">Verwenden Sie das Cmdlet **Test-CsSetupPermission** , um die Berechtigungen zu überprüfen, die Sie mithilfe des Cmdlets **Grant-CsSetupPermission** eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="64dec-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="64dec-107">Sie können das Cmdlet **REVOKE-CsSetupPermission** verwenden, um Berechtigungen zu entfernen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** erteilt haben.</span><span class="sxs-lookup"><span data-stu-id="64dec-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="64dec-108">So erteilen Sie Setup Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="64dec-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="64dec-109">Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="64dec-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="64dec-110">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="64dec-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="64dec-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="64dec-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="64dec-112">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="64dec-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="64dec-113">Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben.</span><span class="sxs-lookup"><span data-stu-id="64dec-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="64dec-114">Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="64dec-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="64dec-115">In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="64dec-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="64dec-116">Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="64dec-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="64dec-117">So überprüfen Sie die Setup Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="64dec-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="64dec-118">Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsSetupPermission** gewährten Setup Berechtigungen überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="64dec-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="64dec-119">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="64dec-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="64dec-120">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="64dec-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="64dec-121">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="64dec-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="64dec-122">Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben.</span><span class="sxs-lookup"><span data-stu-id="64dec-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="64dec-123">Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="64dec-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="64dec-124">In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="64dec-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="64dec-125">Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="64dec-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="64dec-126">So widerrufen Sie die Setup Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="64dec-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="64dec-127">Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die vom Cmdlet **Grant-CsSetupPermission** gewährten Setup Berechtigungen widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="64dec-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="64dec-128">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="64dec-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="64dec-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="64dec-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="64dec-130">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="64dec-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="64dec-131">Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben.</span><span class="sxs-lookup"><span data-stu-id="64dec-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="64dec-132">Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="64dec-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="64dec-133">In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="64dec-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="64dec-134">Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="64dec-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

