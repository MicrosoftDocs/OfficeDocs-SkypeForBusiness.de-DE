---
title: 'Lync Server 2013: Konfigurieren der Verbundunterstützung für einen lync Online Kunden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb7421f204ded840dc627354b0d66627840c594
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517532"
---
# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="60650-102">Konfigurieren der Verbundunterstützung für einen lync Online Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60650-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60650-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="60650-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="60650-104">Sie können Benutzern in Ihrer Organisation auf die folgende Art Kommunikationsdienste bieten:</span><span class="sxs-lookup"><span data-stu-id="60650-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="60650-105">Bereitstellen von lync Server 2013 in Ihrer Organisation (als *Lokale Dienste*bezeichnet) und Einrichten von lync 2013 Benutzerkonten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="60650-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="60650-106">Einrichten eines Microsoft lync Online 2010 Kundenkontos bei einem Hostinganbieter und Einrichten von Benutzerkonten beim Hostinganbieter (auch bekannt als *Online Dienste*).</span><span class="sxs-lookup"><span data-stu-id="60650-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="60650-107">Wenn Sie lync 2013 in Ihrer Organisation bereitstellen, können Sie einen Verbund mit den Domänen eines oder mehrerer Microsoft lync Online 2010-Kunden durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="60650-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="60650-108">Um den Partnerverbund zwischen Benutzern Ihrer lokalen lync 2013-Bereitstellung und Benutzern eines lync Online 2010-Kunden zu aktivieren, müssen Sie die Unterstützung für die Domäne und die Benutzer des lync Online-Kunden konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="60650-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60650-109">In dieser Dokumentation werden nur die Verfahren zum Konfigurieren Ihrer Organisation zur Unterstützung des Verbunds mit einem lync Online 2010-Kunden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60650-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="60650-110">In dieser Dokumentation werden die Verfahren zum Konfigurieren des lync Online 2010-Kunden zur Unterstützung des Verbunds nicht beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60650-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="60650-111">Ausführliche Informationen zu lync Online Diensten finden Sie unter lync online unter <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A> .</span><span class="sxs-lookup"><span data-stu-id="60650-111">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60650-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="60650-112">In This Section</span></span>

  - [<span data-ttu-id="60650-113">Voraussetzungen für die verbundierung mit einem lync Online-Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60650-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="60650-114">Konfigurieren der Verbundunterstützung für eine lync Online Domäne in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60650-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="60650-115">Konfigurieren des Benutzerzugriffs für den Partnerverbund mit einem lync Online-Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60650-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="60650-116">Überprüfen der Kommunikation mit einem lync Online Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60650-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

