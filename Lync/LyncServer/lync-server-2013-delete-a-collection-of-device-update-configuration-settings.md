---
title: 'Lync Server 2013: Löschen einer Auflistung von Konfigurationseinstellungen für Geräte Updates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17d9163985a05611b8c38eb314da9f489695366c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="454db-102">Löschen einer Auflistung von Konfigurationseinstellungen für Geräte Updates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="454db-102">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="454db-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="454db-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="454db-104">Konfigurationseinstellungen für Geräte Updates können auch mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsdeviceUpdateConfiguration** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="454db-104">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="454db-105">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="454db-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="454db-106">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="454db-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="454db-107">So entfernen Sie eine bestimmte Sammlung von Konfigurationseinstellungen für Geräte Updates</span><span class="sxs-lookup"><span data-stu-id="454db-107">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="454db-108">Mit diesem Befehl werden die Konfigurationseinstellungen für das Geräteupdate gelöscht, die auf den Standort "Redmond" angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="454db-108">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="454db-109">So entfernen Sie alle auf den Website Bereich angewendeten Konfigurationseinstellungen für Geräte Updates</span><span class="sxs-lookup"><span data-stu-id="454db-109">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="454db-110">Mit diesem Befehl werden alle Konfigurationseinstellungen für Geräte Updates gelöscht, die auf den Standortbereich angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="454db-110">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="454db-111">So entfernen Sie Konfigurationseinstellungen für Geräte Updates basierend auf dem Wert der LogCleanUpInterval-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="454db-111">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="454db-112">Mit dem folgenden Befehl werden alle Geräte Aktualisierungs Konfigurationseinstellungen gelöscht, bei denen das Intervall für die Protokoll Bereinigung größer als 10 Tage ist (10.00:00:00):</span><span class="sxs-lookup"><span data-stu-id="454db-112">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="454db-113">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="454db-113">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

