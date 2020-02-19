---
title: 'Lync Server 2013: Konfigurieren der Einstellungen für den Medienportbereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 207acda151acb02e73b5fb3d6192356e8cdd7b37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="f37b2-102">Konfigurieren von Einstellungen für den Medienportbereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f37b2-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f37b2-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f37b2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f37b2-104">Die Einstellungen für Medienportbereiche können sich erheblich auf die Clientleistung auswirken und sollten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f37b2-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="f37b2-105">Sie können diese Einstellungen mit lync Server-Verwaltungsshell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f37b2-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="f37b2-106">Einstellungen für den Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="f37b2-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f37b2-107">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f37b2-107">Setting</span></span></th>
<th><span data-ttu-id="f37b2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f37b2-108">Description</span></span></th>
<th><span data-ttu-id="f37b2-109">Lync Server-Verwaltungsshell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f37b2-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="f37b2-110">Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="f37b2-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f37b2-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="f37b2-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="f37b2-p102">Gibt an, ob die vom Server gesendeten Portbereiche vom Client für Medien- und Signaldatenverkehr verwendet werden sollen. Wird gemeinsam mit den Unterwerten "MinMediaPort" und "MaxMediaPort" verwendet.</span><span class="sxs-lookup"><span data-stu-id="f37b2-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="f37b2-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f37b2-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f37b2-115">Parameter clientmediaportrangeenabled</span><span class="sxs-lookup"><span data-stu-id="f37b2-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f37b2-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="f37b2-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="f37b2-p103">Gibt die erste Portnummer an, die für Mediendaten verwendet wird. Gibt in Kombination mit "MaxMediaPort" den Portbereich an. Der empfohlene Mindestbereich umfasst 40 Ports.</span><span class="sxs-lookup"><span data-stu-id="f37b2-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="f37b2-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f37b2-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f37b2-121">ClientMediaPort (repräsentiert die erste Portnummer, die für Clientmediendaten verwendet wird)</span><span class="sxs-lookup"><span data-stu-id="f37b2-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f37b2-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="f37b2-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="f37b2-p104">Gibt die höchste Portnummer an, die für Mediendaten verwendet wird. Gibt in Kombination mit "MinMediaPort" den Portbereich an. Der empfohlene Mindestbereich umfasst 40 Ports.</span><span class="sxs-lookup"><span data-stu-id="f37b2-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="f37b2-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f37b2-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f37b2-127">ClientMediaPortRange (gibt die Gesamtanzahl von Ports an, die für Clientmediendaten verfügbar sind; der Standardwert lautet 40)</span><span class="sxs-lookup"><span data-stu-id="f37b2-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="f37b2-128">So konfigurieren Sie die Einstellungen für den Medienportbereich</span><span class="sxs-lookup"><span data-stu-id="f37b2-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="f37b2-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f37b2-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f37b2-130">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f37b2-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="f37b2-131">Dieses Cmdlet gibt die Konfigurationseinstellungen für Konferenzen zurück.</span><span class="sxs-lookup"><span data-stu-id="f37b2-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="f37b2-132">Führen Sie das folgende Cmdlet mit den Parametern und Werten aus, die Sie ändern möchten (Ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation):</span><span class="sxs-lookup"><span data-stu-id="f37b2-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f37b2-133">Sie können zusätzliche Sätze mit Konfigurationseinstellungen für Konferenzen für bestimmte Standorte erstellen.</span><span class="sxs-lookup"><span data-stu-id="f37b2-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="f37b2-134">Verwenden Sie das Cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> mit einer Standortidentität.</span><span class="sxs-lookup"><span data-stu-id="f37b2-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="f37b2-135">Beim Erstellen neuer Konfigurationseinstellungen für Konferenzen für einen Standort haben die Standorteinstellungen Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f37b2-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="f37b2-136">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f37b2-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

