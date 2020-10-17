---
title: 'Lync Server 2013: Überprüfen der Kommunikation mit einem lync Online-Kunden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518662"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="9ee08-102">Überprüfen der Kommunikation mit einem lync Online Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ee08-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ee08-103">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="9ee08-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="9ee08-104">Damit lync-Benutzer in Ihrer Organisation mit Benutzern eines Microsoft lync Online 2010-Kunden kommunizieren können, müssen Sie die folgenden Schritte ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="9ee08-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="9ee08-105">Erfüllt alle Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="9ee08-105">Met all prerequisites.</span></span> <span data-ttu-id="9ee08-106">Dies umfasst die Bereitstellung Ihrer internen und Edgeserver, die Aktivierung der Verbundunterstützung für Ihre Organisation und das Einrichten von Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="9ee08-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="9ee08-107">Ausführliche Informationen finden Sie unter [Voraussetzungen für die Partnerverbund mit einem lync Online Kunden in lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="9ee08-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="9ee08-108">Konfigurierte Domänenzugriffs Unterstützung in ihrer internen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="9ee08-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="9ee08-109">Dies umfasst das Erstellen eines Eintrags eines Host Anbieters und das Konfigurieren Ihrer Bereitstellung, um den Zugriff aus der Domäne des lync Online Kunden zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="9ee08-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="9ee08-110">Ausführliche Informationen finden Sie unter [Konfigurieren der Verbundunterstützung für eine lync Online Domäne in lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="9ee08-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="9ee08-111">Konfigurieren Sie Ihre Benutzerkonten für die Unterstützung des Verbunds.</span><span class="sxs-lookup"><span data-stu-id="9ee08-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="9ee08-112">Ausführliche Informationen finden Sie unter [Konfigurieren des Benutzerzugriffs für einen Partnerverbund mit einem lync Online-Kunden in lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="9ee08-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="9ee08-113">Nachdem Sie alle diese Schritte ausgeführt haben und der Administrator des lync Online 2010-Kunden die gesamte Konfiguration seiner Online Dienste vervollständigt, um den Verbund mit Ihrer Organisation zu unterstützen, überprüfen Sie die Kommunikation durch Testen der Kommunikation zwischen einem internen Benutzer in Ihrer Organisation und einem Benutzer des lync Online Kunden.</span><span class="sxs-lookup"><span data-stu-id="9ee08-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="9ee08-114">Wenn die Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungs Tool aus dem Edgeserver, um Protokoll-und Ablaufverfolgungsdateien aufzuzeichnen, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="9ee08-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="9ee08-115">Ausführliche Informationen zur Verwendung des Protokollierungstools finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9ee08-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="9ee08-116">Ausführliche Informationen zum Protokollierungstool finden Sie in der Dokumentation zum lync Server 2010 Protokollierungstool in der TechNet-Bibliothek unter [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .</span><span class="sxs-lookup"><span data-stu-id="9ee08-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

