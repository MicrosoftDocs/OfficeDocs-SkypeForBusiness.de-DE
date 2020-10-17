---
title: 'Lync Server 2013: Überprüfen von Adressen'
description: 'Lync Server 2013: Adressen überprüfen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547271"
---
# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="01848-103">Überprüfen von Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01848-103">Validate addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01848-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="01848-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="01848-105">Vor der Veröffentlichung der Standortdatenbank müssen Sie neue Standorte im Abgleich mit der MSAG-Datenbank (Master Street Address Guide) validieren, die vom Dienstanbieter für SIP-Trunks oder Festnetzanschlüsse (Public Switched Telephone Network, PSTN) mit Notrufunterstützung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="01848-105">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="01848-106">Ausführliche Informationen zu SIP-Trunk-E9-1-1-Dienstanbietern finden Sie unter [Auswählen eines E9-1 -1-Dienstanbieters für lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="01848-106">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="01848-107">Ausführliche Informationen zum Überprüfen von Adressen finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="01848-107">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="01848-108">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="01848-108">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="01848-109">**Gruppe-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="01848-109">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="01848-110">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="01848-110">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="01848-111">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="01848-111">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="01848-112">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="01848-112">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="01848-113">So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit</span><span class="sxs-lookup"><span data-stu-id="01848-113">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="01848-114">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="01848-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="01848-115">Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.</span><span class="sxs-lookup"><span data-stu-id="01848-115">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="01848-116">Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="01848-116">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="01848-117">Mit dem Cmdlet **Test-CsLisCivicAddress** können Sie auch einzelne Adressen validieren.</span><span class="sxs-lookup"><span data-stu-id="01848-117">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

