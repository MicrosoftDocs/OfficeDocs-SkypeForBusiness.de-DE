---
title: 'Lync Server 2013: Erteilen von Berechtigungen für Organisationseinheiten'
description: 'Lync Server 2013: Erteilen von Berechtigungen für Organisationseinheiten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554511"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="94595-103">Erteilen von Berechtigungen für Organisationseinheiten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94595-103">Granting organizational unit permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94595-104">_**Letztes Änderungsstand des Themas:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="94595-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="94595-105">Mithilfe des Cmdlets **Grant-CsOuPermission** können Sie auch Objekten in bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="94595-105">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="94595-106">Bei den Berechtigungen, die Sie der angegebenen Organisationseinheit hinzufügen, handelt es sich um die gleichen Berechtigungen, die das Cmdlet **Enable-CsAdDomain** während der Domänenvorbereitung den Containern für Computer und Benutzer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="94595-106">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="94595-107">Verwenden Sie das Cmdlet **Test-CsOuPermission** zum Überprüfen der Berechtigungen, die Sie mit dem Cmdlet **Grant-CsOuPermission** gewähren.</span><span class="sxs-lookup"><span data-stu-id="94595-107">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="94595-108">Mit dem Cmdlet **Revoke-CsOuPermission** können Sie Berechtigungen entfernen, die Sie mit dem Cmdlet **Grant-CsOuPermission** zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="94595-108">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="94595-109">So gewähren Sie Organisationseinheitenberechtigungen</span><span class="sxs-lookup"><span data-stu-id="94595-109">To grant OU permissions</span></span>

1.  <span data-ttu-id="94595-110">Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Organisationseinheiten Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="94595-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="94595-111">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="94595-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="94595-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="94595-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="94595-113">Ausführen</span><span class="sxs-lookup"><span data-stu-id="94595-113">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="94595-114">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="94595-114">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="94595-115">So überprüfen Sie Organisationseinheitenberechtigungen</span><span class="sxs-lookup"><span data-stu-id="94595-115">To verify OU permissions</span></span>

1.  <span data-ttu-id="94595-116">Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsOuPermission** gewährten ou-Berechtigungen überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="94595-116">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="94595-117">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="94595-117">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="94595-118">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="94595-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="94595-119">Ausführen</span><span class="sxs-lookup"><span data-stu-id="94595-119">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="94595-120">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="94595-120">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="94595-121">So entziehen Sie Organisationseinheitenberechtigungen</span><span class="sxs-lookup"><span data-stu-id="94595-121">To revoke OU permissions</span></span>

1.  <span data-ttu-id="94595-122">Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Organisationseinheiten Berechtigungen widerrufen möchten, die vom Cmdlet **Grant-CsOuPermission** erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="94595-122">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="94595-123">Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="94595-123">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="94595-124">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="94595-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="94595-125">Ausführen</span><span class="sxs-lookup"><span data-stu-id="94595-125">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="94595-126">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="94595-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

