---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients'
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
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="b4a43-102">Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a43-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a43-103">_**Letztes Änderungsdatum des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="b4a43-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="b4a43-104">Standardmäßig können lync-Clientanwendungen einen beliebigen Port zwischen den Anschlüssen 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b4a43-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="b4a43-105">Um die Dienstqualität zu nutzen, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe von eindeutigen Portbereichen neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="b4a43-106">Dies kann mithilfe des Cmdlets "CsConferencingConfiguration" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4a43-107">Endbenutzer können diese Änderungen nicht selbst vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="b4a43-108">Port Änderungen können nur von Administratoren mit dem Cmdlet "Satz-CsConferencingConfiguration" vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="b4a43-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="b4a43-109">Sie können ermitteln, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Microsoft lync Server 2013-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="b4a43-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="b4a43-110">Vorausgesetzt, dass Sie seit der Installation von lync Server 2013 keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:</span><span class="sxs-lookup"><span data-stu-id="b4a43-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="b4a43-111">Wenn Sie die vorhergehende Ausgabe genau betrachten, sehen Sie zwei wichtige Dinge.</span><span class="sxs-lookup"><span data-stu-id="b4a43-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="b4a43-112">Zuerst ist die ClientMediaPortRangeEnabled-Eigenschaft auf false festgelegt:</span><span class="sxs-lookup"><span data-stu-id="b4a43-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="b4a43-113">Das ist wichtig, da lync-Clients, wenn diese Eigenschaft auf "false" festgelegt ist, einen beliebigen verfügbaren Port zwischen den Anschlüssen 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="b4a43-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="b4a43-114">Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies ist etwas, was Sie tun möchten, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client Medien-Portbereiche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4a43-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="b4a43-115">Dies kann mithilfe des folgenden Windows PowerShell-Befehls erfolgen:</span><span class="sxs-lookup"><span data-stu-id="b4a43-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="b4a43-116">Der obige Befehl aktiviert Client Medien-Portbereiche für die globale Sammlung von Konferenz Konfigurationseinstellungen; Diese Einstellungen können jedoch auch auf den Website Bereich und/oder den Dienstbereich angewendet werden (nur für den Conferencing Server-Dienst).</span><span class="sxs-lookup"><span data-stu-id="b4a43-116">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="b4a43-117">Wenn Sie die Client Medien-Portbereiche für eine bestimmte Website oder einen bestimmten Server aktivieren möchten, geben Sie die Identität dieser Website oder des Servers beim Aufrufen von CsConferencingConfiguration an:</span><span class="sxs-lookup"><span data-stu-id="b4a43-117">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="b4a43-118">Sie können diesen Befehl auch verwenden, um Portbereiche für alle Ihre Konferenz Konfigurationseinstellungen gleichzeitig zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="b4a43-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="b4a43-119">Wichtig ist, dass die Beispielausgabe zeigt, dass standardmäßig die für die einzelnen Netzwerkdatenverkehr-Typen festgelegten Medien Portbereiche identisch sind:</span><span class="sxs-lookup"><span data-stu-id="b4a43-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="b4a43-120">Um QoS zu implementieren, müssen alle diese Portbereiche eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b4a43-120">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="b4a43-121">So können Sie beispielsweise die Portbereiche wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="b4a43-121">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4a43-122">Client Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="b4a43-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="b4a43-123">Port Start</span><span class="sxs-lookup"><span data-stu-id="b4a43-123">Port Start</span></span></th>
<th><span data-ttu-id="b4a43-124">Port Bereich</span><span class="sxs-lookup"><span data-stu-id="b4a43-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4a43-125">Audio</span><span class="sxs-lookup"><span data-stu-id="b4a43-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="b4a43-126">50020</span><span class="sxs-lookup"><span data-stu-id="b4a43-126">50020</span></span></p></td>
<td><p><span data-ttu-id="b4a43-127">20</span><span class="sxs-lookup"><span data-stu-id="b4a43-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a43-128">Video</span><span class="sxs-lookup"><span data-stu-id="b4a43-128">Video</span></span></p></td>
<td><p><span data-ttu-id="b4a43-129">58000</span><span class="sxs-lookup"><span data-stu-id="b4a43-129">58000</span></span></p></td>
<td><p><span data-ttu-id="b4a43-130">20</span><span class="sxs-lookup"><span data-stu-id="b4a43-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a43-131">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="b4a43-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="b4a43-132">42000</span><span class="sxs-lookup"><span data-stu-id="b4a43-132">42000</span></span></p></td>
<td><p><span data-ttu-id="b4a43-133">20</span><span class="sxs-lookup"><span data-stu-id="b4a43-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a43-134">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="b4a43-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="b4a43-135">42020</span><span class="sxs-lookup"><span data-stu-id="b4a43-135">42020</span></span></p></td>
<td><p><span data-ttu-id="b4a43-136">20</span><span class="sxs-lookup"><span data-stu-id="b4a43-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b4a43-137">In der obigen Tabelle stellen Client-Portbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b4a43-137">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="b4a43-138">Auf den Servern wurde die Anwendungsfreigabe beispielsweise so konfiguriert, dass die Ports 40803 bis 49151 verwendet werden. auf den Clientcomputern ist die Anwendungsfreigabe so konfiguriert, dass die Ports 42000 bis 42019 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4a43-138">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="b4a43-139">Dies erfolgt in erster Linie, um die Verwaltung von QoS zu vereinfachen: Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-139">This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="b4a43-140">(Beispielsweise können Sie auf den Clientcomputern die Anwendungsfreigabe so konfigurieren, dass die Verwendung von Ports 10000 bis 10019 verwendet wird.) Es wird jedoch empfohlen, dass Sie die Client Portbereiche zu einer Teilmenge der Server Portbereiche machen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-140">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="b4a43-141">Darüber hinaus haben Sie möglicherweise festgestellt, dass 8348-Ports für die Anwendungsfreigabe auf den Servern reserviert wurden, aber nur 20 Ports für die Anwendungsfreigabe auf den Clients reserviert wurden.</span><span class="sxs-lookup"><span data-stu-id="b4a43-141">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="b4a43-142">Auch dies wird empfohlen, ist aber keine harte und schnelle Regel.</span><span class="sxs-lookup"><span data-stu-id="b4a43-142">This, too is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="b4a43-143">Im Allgemeinen können Sie jeden verfügbaren Port in Betracht ziehen, um eine einzelne Kommunikationssitzung darzustellen: Wenn Sie 100-Ports in einem Portbereich zur Verfügung haben, bedeutet dies, dass der fragliche Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="b4a43-143">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="b4a43-144">Da Server wahrscheinlich an vielen weiteren Unterhaltungen als Clients teilnehmen, ist es sinnvoll, viel mehr Ports auf Servern als auf Clients zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-144">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="b4a43-145">Wenn Sie 20 Ports für die Anwendungsfreigabe auf einem Client beiseite legen, bedeutet dies, dass ein Benutzer an 20 Anwendungsfreigabesitzungen auf dem angegebenen Gerät und alle zur gleichen Zeit teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="b4a43-145">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="b4a43-146">Dies sollte für die meisten Benutzer ausreichend sein.</span><span class="sxs-lookup"><span data-stu-id="b4a43-146">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="b4a43-147">Wenn Sie der globalen Sammlung von Konferenz Konfigurationseinstellungen die vorherigen Portbereiche zuweisen möchten, können Sie den folgenden Befehl der lync Server-Verwaltungsshell verwenden:</span><span class="sxs-lookup"><span data-stu-id="b4a43-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="b4a43-148">Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenz Konfigurationseinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="b4a43-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="b4a43-149">Einzelne Benutzer müssen sich von lync abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="b4a43-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4a43-150">Sie können auch Client Medien-Portbereiche aktivieren und dann mithilfe eines einzigen Befehls Diese Portbereiche zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b4a43-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="b4a43-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b4a43-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

