---
title: 'Lync Server 2013: Wiederherstellen der Einstellungen für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c663441496d7a08a656095da4371376912fadc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="f1320-102">Wiederherstellen der Einstellungen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1320-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1320-103">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f1320-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f1320-104">Wenn Sie den Reaktionsgruppenanwendung bereitgestellt haben und einen Back-End-Server oder einen Standard Edition-Server wiederherstellen müssen, müssen Sie auch die Konfigurationseinstellungen der Reaktionsgruppe wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f1320-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="f1320-105">So stellen Sie Konfigurationseinstellungen für Reaktionsgruppen wieder her</span><span class="sxs-lookup"><span data-stu-id="f1320-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="f1320-106">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f1320-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="f1320-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1320-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

