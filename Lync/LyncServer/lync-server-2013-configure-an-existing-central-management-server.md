---
title: 'Lync Server 2013: Konfigurieren eines vorhandenen zentralen Verwaltungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bfcd872f765e4a2ee69b09c4f1328125bc581d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523002"
---
# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="0cc76-102">Konfigurieren eines vorhandenen zentralen Verwaltungsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cc76-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cc76-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0cc76-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0cc76-104">Wenn Sie einen zentralen Verwaltungs Server aus einer vorhandenen lync Server 2013-Bereitstellung wieder verwenden, müssen Sie das unten beschriebene Verfahren ausführen, um sicherzustellen, dass lync Server-Systemsteuerung und Windows PowerShell ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="0cc76-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="0cc76-105">So konfigurieren Sie einen vorhandenen zentralen Verwaltungs Server</span><span class="sxs-lookup"><span data-stu-id="0cc76-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="0cc76-106">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0cc76-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0cc76-107">Verwenden Sie das Cmdlet **Update-CsAdminRole** , um die rollenbasierten zugriffssteuerungsrollen (Role-Based Access Control, RBAC) zu aktualisieren, die auf dem zentralen Verwaltungs Server gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0cc76-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0cc76-108">Es wird keine Ausgabe erwartet, außer es tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="0cc76-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

