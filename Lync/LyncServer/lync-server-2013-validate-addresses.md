---
title: 'Lync Server 2013: Adressen überprüfen'
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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="0b8df-102">Überprüfen von Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b8df-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b8df-103">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="0b8df-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="0b8df-104">Bevor Sie die Standortdatenbank veröffentlichen, müssen Sie neue Speicherorte für den Master Street Address Guide (MSAG) überprüfen, der von Ihrem SIP-Stamm oder dem öffentlichen Telefonnetz (PSTN) E9-1-1 Service Provider verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0b8df-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="0b8df-105">Ausführliche Informationen zu SIP Trunk E9-1-1 Serviceanbietern finden Sie unter [Auswählen eines E9-1-1-Dienstanbieters für lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0b8df-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="0b8df-106">Details zur Überprüfung von Adressen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b8df-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="0b8df-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="0b8df-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="0b8df-108">**Satz-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="0b8df-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="0b8df-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="0b8df-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="0b8df-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="0b8df-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="0b8df-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="0b8df-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="0b8df-112">So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit</span><span class="sxs-lookup"><span data-stu-id="0b8df-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="0b8df-113">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0b8df-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0b8df-114">Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.</span><span class="sxs-lookup"><span data-stu-id="0b8df-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="0b8df-115">Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="0b8df-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="0b8df-116">Einzelne Adressen können Sie auch mit dem Cmdlet **Test-CsLisCivicAddress** validieren.</span><span class="sxs-lookup"><span data-stu-id="0b8df-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

