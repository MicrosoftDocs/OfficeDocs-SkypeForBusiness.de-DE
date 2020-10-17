---
title: 'Lync Server 2013: Veröffentlichen der Standortdatenbank'
description: 'Lync Server 2013: Veröffentlichen der Standortdatenbank.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26892429c7bf5fd9cbfebd0d7ac62482767a541e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565441"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="28207-103">Veröffentlichen der Standortdatenbank aus lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28207-103">Publish the location database from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28207-104">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="28207-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="28207-105">Die neuen Standorte, die Sie der Standortdatenbank hinzugefügt haben, stehen dem Client erst nach der Veröffentlichung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="28207-105">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="28207-106">Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation für das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="28207-106">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="28207-107">**Veröffentlichen-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="28207-107">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="28207-108">Wenn Sie ELIN-Gateways (Emergency Location Identification Number) verwenden, müssen Sie auch die die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hochladen.</span><span class="sxs-lookup"><span data-stu-id="28207-108">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="28207-109">Ihr PSTN-Betreiber verlangt möglicherweise, dass Sie ein bestimmtes Format für die ELIN-Einträge verwenden.</span><span class="sxs-lookup"><span data-stu-id="28207-109">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="28207-110">Weitere Informationen erhalten Sie von Ihrem PSTN-Betreiber.</span><span class="sxs-lookup"><span data-stu-id="28207-110">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="28207-111">Sie können die Datensätze aus der Standortinformationsdienst Datenbank exportieren und nach Bedarf formatieren.</span><span class="sxs-lookup"><span data-stu-id="28207-111">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="28207-112">So veröffentlichen Sie die Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="28207-112">To publish the location database</span></span>

  - <span data-ttu-id="28207-113">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="28207-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="28207-114">Führen Sie das folgende Cmdlet aus, um die Standortdatenbank zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="28207-114">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

