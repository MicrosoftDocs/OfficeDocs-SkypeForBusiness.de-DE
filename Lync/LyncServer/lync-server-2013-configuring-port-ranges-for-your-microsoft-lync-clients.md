---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients'
description: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7fcabf81f8e0110010b1a4fb8e697fb0da986c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569991"
---
# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="c8c87-103">Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c87-103">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8c87-104">_**Letztes Änderungsstand des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c8c87-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c8c87-105">Lync-Clientanwendungen können standardmäßig einen beliebigen Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c8c87-105">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="c8c87-106">Um die Dienstqualität zu verwenden, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe eindeutiger Portbereiche neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c8c87-106">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="c8c87-107">Dies kann mithilfe des Set-CsConferencingConfiguration-Cmdlets erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c8c87-107">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8c87-108">Endbenutzer können diese Änderungen nicht selbst vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c8c87-108">End users cannot make these changes themselves.</span></span> <span data-ttu-id="c8c87-109">Port Änderungen können nur von Administratoren mithilfe des Set-CsConferencingConfiguration-Cmdlets vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c8c87-109">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="c8c87-110">Sie können bestimmen, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Microsoft lync Server 2013 Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="c8c87-110">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="c8c87-111">Unter der Annahme, dass Sie seit der Installation von lync Server 2013 keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:</span><span class="sxs-lookup"><span data-stu-id="c8c87-111">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="c8c87-112">Wenn Sie sich die vorherige Ausgabe genauer ansehen, werden Sie zwei wichtige Aspekte feststellen.</span><span class="sxs-lookup"><span data-stu-id="c8c87-112">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="c8c87-113">Zunächst ist die Eigenschaft ClientMediaPortRangeEnabled auf False gesetzt:</span><span class="sxs-lookup"><span data-stu-id="c8c87-113">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="c8c87-114">Dies ist wichtig, da lync-Clients, wenn diese Eigenschaft auf "false" festgelegt ist, einen beliebigen verfügbaren Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="c8c87-114">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="c8c87-115">Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies möchten Sie tun, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client-Medien Portbereiche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8c87-115">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="c8c87-116">Dies kann mithilfe des folgenden Windows PowerShell Befehls erfolgen:</span><span class="sxs-lookup"><span data-stu-id="c8c87-116">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c8c87-p105">Mit dem obigen Befehl werden die Client-Medienportbereiche für die globale Auflistung der Konferenzkonfigurationseinstellungen aktiviert. Diese Einstellungen können jedoch auch auf Standortebene und/oder Dienstebene (nur für den Konferenzserverdienst) angewendet werden. Um die Client-Medienportbereiche für einen bestimmten Standort oder Server zu aktivieren, geben Sie beim Aufruf von Set-CsConferencingConfiguration die Identität des Standorts oder Servers an:</span><span class="sxs-lookup"><span data-stu-id="c8c87-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c8c87-119">Alternativ können Sie diesen Befehl verwenden, um Portbereiche für die gesamten Konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c8c87-119">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c8c87-120">Der zweite wichtige Aspekt ist, dass für jeden Typ von Netzwerkdatenverkehr standardmäßig dieselben Medienportbereiche festgelegt werden, wie Sie in der Beispielausgabe sehen können:</span><span class="sxs-lookup"><span data-stu-id="c8c87-120">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="c8c87-p106">Zur Implementierung des Quality of Service (QoS) muss jeder dieser Portbereiche identisch sein. Sie können diese Portbereiche z. B. wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c8c87-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8c87-123">Client-Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="c8c87-123">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c8c87-124">Anfang des Portbereichs</span><span class="sxs-lookup"><span data-stu-id="c8c87-124">Port Start</span></span></th>
<th><span data-ttu-id="c8c87-125">Portbereich</span><span class="sxs-lookup"><span data-stu-id="c8c87-125">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8c87-126">Audio</span><span class="sxs-lookup"><span data-stu-id="c8c87-126">Audio</span></span></p></td>
<td><p><span data-ttu-id="c8c87-127">50020</span><span class="sxs-lookup"><span data-stu-id="c8c87-127">50020</span></span></p></td>
<td><p><span data-ttu-id="c8c87-128">20</span><span class="sxs-lookup"><span data-stu-id="c8c87-128">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c87-129">Video</span><span class="sxs-lookup"><span data-stu-id="c8c87-129">Video</span></span></p></td>
<td><p><span data-ttu-id="c8c87-130">58000</span><span class="sxs-lookup"><span data-stu-id="c8c87-130">58000</span></span></p></td>
<td><p><span data-ttu-id="c8c87-131">20</span><span class="sxs-lookup"><span data-stu-id="c8c87-131">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8c87-132">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="c8c87-132">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c8c87-133">42000</span><span class="sxs-lookup"><span data-stu-id="c8c87-133">42000</span></span></p></td>
<td><p><span data-ttu-id="c8c87-134">20</span><span class="sxs-lookup"><span data-stu-id="c8c87-134">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8c87-135">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="c8c87-135">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c8c87-136">42020</span><span class="sxs-lookup"><span data-stu-id="c8c87-136">42020</span></span></p></td>
<td><p><span data-ttu-id="c8c87-137">20</span><span class="sxs-lookup"><span data-stu-id="c8c87-137">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8c87-p107">In der obigen Tabelle stellen Clientportbereiche eine Teilmenge der für die Server konfigurierten Portbereiche dar. Beispielsweise ist auf den Servern konfiguriert, dass die Ports 40803 bis 49151 für die Anwendungsfreigabe verwendet werden. Auf den Clientcomputern ist konfiguriert, dass die Ports 42000 bis 42019 für die Anwendungsfreigabe verwendet werden. Dies dient hauptsächlich dem Zweck, die QoS-Verwaltung zu vereinfachen: Die Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen. (Sie können auf Clientcomputern auch konfigurieren, dass die Ports 10000 bis 10019 für die Anwendungsfreigabe verwendet werden.) Es wird jedoch empfohlen, für Clients eine Teilmenge der Serverportbereiche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8c87-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="c8c87-p108">Zudem haben Sie vielleicht festgestellt, dass auf den Servern 8348 Ports für die Anwendungsfreigabe reserviert wurden, auf den Clients jedoch lediglich 20 Ports. Dies ist auch nur eine Empfehlung und keine verbindliche Regel. Im Allgemeinen können Sie einplanen, dass jeder verfügbare Port eine einzelne Kommunikationssitzung darstellt: Wenn in einem Portbereich 100 Ports verfügbar sind, bedeutet dies, dass der fragliche Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann. Da Server wahrscheinlich an weitaus mehr Unterhaltungen als Clients beteiligt sind, ist es sinnvoll, auf den Servern viel mehr Ports als auf den Clients zu öffnen. Wenn Sie auf einem Client 20 Ports für die Anwendungsfreigabe reservieren, bedeutet dies, dass ein Benutzer auf dem angegebenen Gerät an 20 Anwendungssitzungen gleichzeitig teilnehmen kann. Dies sollte für die allermeisten Benutzer ausreichend sein.</span><span class="sxs-lookup"><span data-stu-id="c8c87-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="c8c87-148">Sie können den folgenden lync Server-Verwaltungsshell Befehl verwenden, um die vorhergehenden Portbereiche ihrer globalen Sammlung von Konferenz Konfigurationseinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="c8c87-148">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c8c87-149">Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="c8c87-149">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c8c87-150">Einzelne Benutzer müssen sich von lync abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c8c87-150">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8c87-151">Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c8c87-151">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="c8c87-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8c87-152">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

