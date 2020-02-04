---
title: 'Lync Server 2013: Konfigurieren eines sekundären Standort Informationsdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b7ee9383939e8df5466d615f6fda4a2af33c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="6325b-102">Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6325b-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6325b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6325b-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6325b-104">Lync Server 2013 stellt eine Webdienstschnittstelle bereit, die Sie verwenden können, um den standortinformationsdienst auf eine SLS-Datenbank (Secondary Location Source) zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6325b-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="6325b-105">Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss dem Location Information Service-WSDL entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6325b-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="6325b-106">Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der standortinformationsdienst zuerst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet die standortanforderung vom Client an die SLS-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6325b-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="6325b-107">Wenn der Standort im SLS vorhanden ist, sendet der standortinformationsdienst den Standort dann zurück an den Client.</span><span class="sxs-lookup"><span data-stu-id="6325b-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="6325b-108">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6325b-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="6325b-109">**Satz-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="6325b-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="6325b-110">So konfigurieren Sie die sekundäre Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="6325b-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="6325b-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6325b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6325b-112">Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6325b-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

