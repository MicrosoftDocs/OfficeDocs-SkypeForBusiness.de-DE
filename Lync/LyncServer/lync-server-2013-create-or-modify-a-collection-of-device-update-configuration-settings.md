---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräte Updates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1cba65da0e8c1e01c5cf5666b13b98cc2009baf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7ce8e-102">Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräte Updates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ce8e-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ce8e-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7ce8e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7ce8e-104">Konfigurationseinstellungen für Geräte Updates können (nur auf Standortebene) mithilfe von Windows PowerShell und dem Cmdlet **New-CsDeviceUpdateConfiguration** erstellt und mithilfe des Cmdlets " **CsDeviceUpdateConfiguration** " geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="7ce8e-105">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7ce8e-106">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="7ce8e-107">So erstellen Sie Konfigurationseinstellungen für Geräte Updates, die die Standardwerte verwenden</span><span class="sxs-lookup"><span data-stu-id="7ce8e-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="7ce8e-108">Mit diesem Befehl wird eine neue Gruppe von Konfigurationseinstellungen für das Geräteupdate für den Standort "Redmond" erstellt:</span><span class="sxs-lookup"><span data-stu-id="7ce8e-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="7ce8e-109">Da im vorherigen Befehl keine anderen Parameter als der obligatorische Identity-Parameter angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen die Standardwerte für alle Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="7ce8e-110">So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen von Geräte Aktualisierungs Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7ce8e-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="7ce8e-111">Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="7ce8e-112">Um beispielsweise eine Sammlung von Konfigurationseinstellungen für Geräte Updates zu erstellen, die standardmäßig alle 21 Tage alte Protokolldateien löschen, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="7ce8e-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="7ce8e-113">So ändern Sie beim Erstellen von Geräte Aktualisierungs Konfigurationseinstellungen mehrere Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="7ce8e-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="7ce8e-114">Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="7ce8e-115">Mit dem folgenden Befehl wird beispielsweise das Intervall für die Protokoll Bereinigung auf 21 Tage und das Protokoll leer Intervall auf 30 Minuten festgelegt:</span><span class="sxs-lookup"><span data-stu-id="7ce8e-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="7ce8e-116">Ausführliche Informationen zum Ändern vorhandener Geräte Konfigurationseinstellungen finden Sie im Hilfethema für das Cmdlet " [Sets-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) ".</span><span class="sxs-lookup"><span data-stu-id="7ce8e-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="7ce8e-117">Ausführliche Informationen zum Erstellen von Auflistungen von Konfigurationseinstellungen finden Sie im Hilfethema für das [New-CsDeviceUpdateConfiguration-](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ce8e-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

