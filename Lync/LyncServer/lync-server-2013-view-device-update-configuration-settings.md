---
title: 'Lync Server 2013: Anzeigen von Konfigurationseinstellungen für Geräte Updates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f7f3d6ae80aa83d7edcf6d64a13c4cbda90c9ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506452"
---
# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1269b-102">Anzeigen von Konfigurationseinstellungen für Geräte Updates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1269b-102">View Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1269b-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1269b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1269b-104">Sie können die Konfigurationseinstellungen für den Geräte Update Dienst mit lync Server-Verwaltungsshell und dem Cmdlet **Get-CsDeviceUpdateConfiguration** anzeigen, das Sie über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1269b-104">You can view the Device Update Service configuration settings by using Lync Server Management Shell and the **Get-CsDeviceUpdateConfiguration** cmdlet, which you can run from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1269b-105">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="1269b-105">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>


  - <span data-ttu-id="1269b-106">Wenn Sie Informationen zu allen VoIP-Routen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1269b-106">To view information about all your voice routes, type the following command in the Lync Server Management Shell and press Enter:</span></span>
    
        Get-CsDeviceUpdateConfiguration
    
    <span data-ttu-id="1269b-107">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1269b-107">This command returns information similar to the following:</span></span>
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

<span data-ttu-id="1269b-108">Ausführliche Informationen zu diesem Cmdlet finden Sie unter Hilfethema unter [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1269b-108">For details about this cmdlet, see Help topic at [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

