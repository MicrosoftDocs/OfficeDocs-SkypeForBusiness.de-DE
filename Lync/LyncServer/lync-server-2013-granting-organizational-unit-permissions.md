---
title: 'Lync Server 2013: Gewähren von Berechtigungen für die Organisationseinheit'
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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="41a70-102">Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a70-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a70-103">_**Letztes Änderungsdatum des Themas:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="41a70-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="41a70-104">Sie können das Cmdlet **Grant-CsOuPermission** verwenden, um den Objekten in bestimmten Organisationseinheiten (Organizational Units, OUs) Berechtigungen zu erteilen, damit Mitglieder der von Forest Preparation erstellten RTC-universellen Gruppen auf diese zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.</span><span class="sxs-lookup"><span data-stu-id="41a70-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="41a70-105">Die der angegebenen Organisationseinheit hinzugefügten Berechtigungen sind dieselben Berechtigungen, die das Cmdlet **enable-CsAdDomain** den Computern und Benutzer Containern während der Domänenvorbereitung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="41a70-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="41a70-106">Verwenden Sie das Cmdlet **Test-CsOuPermission** , um die Berechtigungen zu überprüfen, die Sie mithilfe des Cmdlets **Grant-CsOuPermission** eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="41a70-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="41a70-107">Sie können das Cmdlet **REVOKE-CsOuPermission** verwenden, um Berechtigungen zu entfernen, die Sie mit dem Cmdlet **Grant-CsOuPermission** erteilt haben.</span><span class="sxs-lookup"><span data-stu-id="41a70-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="41a70-108">So erteilen Sie ou-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41a70-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="41a70-109">Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie ou-Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="41a70-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="41a70-110">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="41a70-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="41a70-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="41a70-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="41a70-112">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41a70-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="41a70-113">Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="41a70-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="41a70-114">So überprüfen Sie die OU-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41a70-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="41a70-115">Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsOuPermission** gewährten ou-Berechtigungen überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="41a70-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="41a70-116">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="41a70-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="41a70-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="41a70-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="41a70-118">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41a70-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="41a70-119">Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="41a70-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="41a70-120">So widerrufen Sie ou-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41a70-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="41a70-121">Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die vom Cmdlet **Grant-CsOuPermission** gewährten ou-Berechtigungen widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="41a70-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="41a70-122">Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.</span><span class="sxs-lookup"><span data-stu-id="41a70-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="41a70-123">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="41a70-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="41a70-124">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41a70-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="41a70-125">Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="41a70-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

