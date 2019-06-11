---
title: 'Lync Server 2013: Konfigurieren der Einstellungen für den Medienportbereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="369b0-102">Konfigurieren von Einstellungen für den Medienportbereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="369b0-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="369b0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="369b0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="369b0-104">Einstellungen für den Medienportbereich können die Clientleistung erheblich beeinträchtigen und sollten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="369b0-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="369b0-105">Sie können diese Einstellungen mithilfe der lync Server-Verwaltungsshell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="369b0-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="369b0-106">Einstellungen für den Medien Port Bereich</span><span class="sxs-lookup"><span data-stu-id="369b0-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="369b0-107">Einstellung</span><span class="sxs-lookup"><span data-stu-id="369b0-107">Setting</span></span></th>
<th><span data-ttu-id="369b0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="369b0-108">Description</span></span></th>
<th><span data-ttu-id="369b0-109">Cmdlet "lync Server-Verwaltungsshell"</span><span class="sxs-lookup"><span data-stu-id="369b0-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="369b0-110">Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="369b0-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="369b0-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="369b0-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="369b0-112">Gibt an, ob der vom Server gesendete Portbereich vom Client für Medien und Signalisierungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="369b0-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="369b0-113">Wird in Verbindung mit den unter Werten MinMediaPort und MaxMediaPort verwendet.</span><span class="sxs-lookup"><span data-stu-id="369b0-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="369b0-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="369b0-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="369b0-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="369b0-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="369b0-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="369b0-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="369b0-117">Gibt die für Medien zu verwendende anfangs Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="369b0-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="369b0-118">Kombiniert mit MaxMediaPort, um den Portbereich anzugeben.</span><span class="sxs-lookup"><span data-stu-id="369b0-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="369b0-119">Der empfohlene Mindestbereich ist 40-Anschlüsse.</span><span class="sxs-lookup"><span data-stu-id="369b0-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="369b0-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="369b0-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="369b0-121">ClientMediaPort (stellt die Anfangs Portnummer dar, die für Client Medien verwendet werden soll)</span><span class="sxs-lookup"><span data-stu-id="369b0-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="369b0-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="369b0-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="369b0-123">Gibt die höchste Portnummer an, die für Medien verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="369b0-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="369b0-124">Kombiniert mit MinMediaPort, um den Portbereich anzugeben.</span><span class="sxs-lookup"><span data-stu-id="369b0-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="369b0-125">Der empfohlene Mindestbereich ist 40-Anschlüsse.</span><span class="sxs-lookup"><span data-stu-id="369b0-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="369b0-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="369b0-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="369b0-127">ClientMediaPortRange (zeigt die Gesamtanzahl der für Client Medien verfügbaren Ports an; Standard ist 40)</span><span class="sxs-lookup"><span data-stu-id="369b0-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="369b0-128">So konfigurieren Sie die Einstellungen für den Medien Port Bereich</span><span class="sxs-lookup"><span data-stu-id="369b0-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="369b0-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="369b0-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="369b0-130">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="369b0-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="369b0-131">Dieses Cmdlet gibt die Konfigurationseinstellungen für Konferenzen zurück.</span><span class="sxs-lookup"><span data-stu-id="369b0-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="369b0-132">Führen Sie das folgende Cmdlet mit den Parametern und Werten aus, die Sie ändern möchten (Einzelheiten zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell):</span><span class="sxs-lookup"><span data-stu-id="369b0-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="369b0-133">Sie können zusätzliche Gruppen von Konferenz Konfigurationseinstellungen für bestimmte Websites erstellen.</span><span class="sxs-lookup"><span data-stu-id="369b0-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="369b0-134">Verwenden Sie das Cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> mit einer Websiteidentität.</span><span class="sxs-lookup"><span data-stu-id="369b0-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="369b0-135">Wenn Sie neue Konferenz Konfigurationseinstellungen für Websites erstellen, haben die Websiteeinstellungen Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="369b0-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="369b0-136">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="369b0-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

