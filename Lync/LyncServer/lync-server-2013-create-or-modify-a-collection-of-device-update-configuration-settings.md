---
title: Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Geräte Updates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="34b17-102">Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Geräte Updates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b17-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34b17-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="34b17-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="34b17-104">Konfigurationseinstellungen für Geräte Updates können (nur im Website Bereich) mithilfe von Windows PowerShell und dem Cmdlet **New-CsDeviceUpdateConfiguration** erstellt und mithilfe des Cmdlets " **Satz-CsDeviceUpdateConfiguration** " geändert werden.</span><span class="sxs-lookup"><span data-stu-id="34b17-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="34b17-105">Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34b17-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="34b17-106">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="34b17-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="34b17-107">So erstellen Sie Konfigurationseinstellungen für Geräte Updates, die die Standardwerte verwenden</span><span class="sxs-lookup"><span data-stu-id="34b17-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="34b17-108">Mit diesem Befehl wird ein neuer Satz von Geräteupdate-Konfigurationseinstellungen für die Website "Redmond" erstellt:</span><span class="sxs-lookup"><span data-stu-id="34b17-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="34b17-109">Da im vorhergehenden Befehl keine anderen Parameter als der Parameter für die obligatorische Identität angegeben wurden, werden in der neuen Sammlung der Konfigurationseinstellungen die Standardwerte für alle zugehörigen Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="34b17-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="34b17-110">So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen von Geräteupdate-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="34b17-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="34b17-111">Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein.</span><span class="sxs-lookup"><span data-stu-id="34b17-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="34b17-112">Wenn Sie beispielsweise eine Sammlung von Konfigurationseinstellungen für Geräte Updates erstellen möchten, die standardmäßig alle 21 Tage alte Protokolldateien löscht, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="34b17-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="34b17-113">So ändern Sie beim Erstellen von Geräteupdate-Konfigurationseinstellungen mehrere Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="34b17-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="34b17-114">Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="34b17-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="34b17-115">Mit diesem Befehl wird beispielsweise das Protokoll Bereinigungsintervall auf 21 Tage und das Protokoll leer Intervall auf 30 Minuten festgelegt:</span><span class="sxs-lookup"><span data-stu-id="34b17-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="34b17-116">Details zum Ändern vorhandener Geräte Konfigurationseinstellungen finden Sie im Hilfethema zum Cmdlet " [setCsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) ".</span><span class="sxs-lookup"><span data-stu-id="34b17-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="34b17-117">Details zum Erstellen von Sammlungen von Konfigurationseinstellungen finden Sie im Hilfethema zum Cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="34b17-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

