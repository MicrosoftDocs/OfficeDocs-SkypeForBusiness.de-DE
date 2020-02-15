---
title: Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Dienst Qualitätsrichtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 betrieben werden.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045888"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="e8383-103">Konfigurieren von Portbereichen und einer Dienst Qualitätsrichtlinie für Ihre Clients in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8383-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="e8383-104">In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Dienst Qualitätsrichtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 betrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="e8383-105">Konfigurieren von Portbereichen</span><span class="sxs-lookup"><span data-stu-id="e8383-105">Configure port ranges</span></span>

<span data-ttu-id="e8383-106">Skype for Business Clientanwendungen können standardmäßig einen beliebigen Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="e8383-107">Um die Dienstqualität zu verwenden, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe eindeutiger Portbereiche neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e8383-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="e8383-108">Dies kann mithilfe des Cmdlets "CsConferencingConfiguration" geschehen.</span><span class="sxs-lookup"><span data-stu-id="e8383-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="e8383-109">Endbenutzer können diese Änderungen nicht selbst vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e8383-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="e8383-110">Port Änderungen können nur von Administratoren mithilfe des Cmdlets "CsConferencingConfiguration" vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="e8383-111">Sie können bestimmen, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="e8383-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="e8383-112">Unter der Annahme, dass Sie seit der Installation von Skype for Business Server keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:</span><span class="sxs-lookup"><span data-stu-id="e8383-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="e8383-113">Wenn Sie sich die vorherige Ausgabe genauer ansehen, werden Sie zwei wichtige Aspekte feststellen.</span><span class="sxs-lookup"><span data-stu-id="e8383-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="e8383-114">Zunächst ist die Eigenschaft ClientMediaPortRangeEnabled auf False gesetzt:</span><span class="sxs-lookup"><span data-stu-id="e8383-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="e8383-115">Das ist wichtig, da, wenn diese Eigenschaft auf "false" festgelegt ist, Skype for Business Clients einen beliebigen verfügbaren Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="e8383-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="e8383-116">Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies möchten Sie tun, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client-Medien Portbereiche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e8383-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="e8383-117">Dies kann mithilfe des folgenden Windows PowerShell Befehls erfolgen:</span><span class="sxs-lookup"><span data-stu-id="e8383-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="e8383-p105">Mit dem obigen Befehl werden die Client-Medienportbereiche für die globale Auflistung der Konferenzkonfigurationseinstellungen aktiviert. Diese Einstellungen können jedoch auch auf Standortebene und/oder Dienstebene (nur für den Konferenzserverdienst) angewendet werden. Um die Client-Medienportbereiche für einen bestimmten Standort oder Server zu aktivieren, geben Sie beim Aufruf von Set-CsConferencingConfiguration die Identität des Standorts oder Servers an:</span><span class="sxs-lookup"><span data-stu-id="e8383-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="e8383-120">Alternativ können Sie diesen Befehl verwenden, um Portbereiche für die gesamten Konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="e8383-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="e8383-121">Der zweite wichtige Aspekt ist, dass für jeden Typ von Netzwerkdatenverkehr standardmäßig dieselben Medienportbereiche festgelegt werden, wie Sie in der Beispielausgabe sehen können:</span><span class="sxs-lookup"><span data-stu-id="e8383-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="e8383-p106">Zur Implementierung des Quality of Service (QoS) muss jeder dieser Portbereiche identisch sein. Sie können diese Portbereiche z. B. wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e8383-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8383-124">Client-Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="e8383-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="e8383-125">Anfang des Portbereichs</span><span class="sxs-lookup"><span data-stu-id="e8383-125">Port Start</span></span></th>
<th><span data-ttu-id="e8383-126">Portbereich</span><span class="sxs-lookup"><span data-stu-id="e8383-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8383-127">Audio</span><span class="sxs-lookup"><span data-stu-id="e8383-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="e8383-128">50020</span><span class="sxs-lookup"><span data-stu-id="e8383-128">50020</span></span></p></td>
<td><p><span data-ttu-id="e8383-129">20</span><span class="sxs-lookup"><span data-stu-id="e8383-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8383-130">Video</span><span class="sxs-lookup"><span data-stu-id="e8383-130">Video</span></span></p></td>
<td><p><span data-ttu-id="e8383-131">58000</span><span class="sxs-lookup"><span data-stu-id="e8383-131">58000</span></span></p></td>
<td><p><span data-ttu-id="e8383-132">20</span><span class="sxs-lookup"><span data-stu-id="e8383-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8383-133">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="e8383-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="e8383-134">42000</span><span class="sxs-lookup"><span data-stu-id="e8383-134">42000</span></span></p></td>
<td><p><span data-ttu-id="e8383-135">20</span><span class="sxs-lookup"><span data-stu-id="e8383-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8383-136">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="e8383-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="e8383-137">42020</span><span class="sxs-lookup"><span data-stu-id="e8383-137">42020</span></span></p></td>
<td><p><span data-ttu-id="e8383-138">20</span><span class="sxs-lookup"><span data-stu-id="e8383-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e8383-139">In der obigen Tabelle stellen Client Portbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e8383-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="e8383-140">Auf den Servern wurde die Anwendungsfreigabe beispielsweise für die Verwendung von Ports 40803 bis 49151 konfiguriert; auf den Clientcomputern ist die Anwendungsfreigabe für die Verwendung von Ports 42000 bis 42019 konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e8383-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="e8383-141">Auch dies geschieht in erster Linie, um die Verwaltung von QoS zu vereinfachen: Client-Ports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen.</span><span class="sxs-lookup"><span data-stu-id="e8383-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="e8383-142">(Beispielsweise können Sie auf den Clientcomputern die Anwendungsfreigabe so konfigurieren, dass die Ports 10000 bis 10019 verwendet werden.) Es wird jedoch empfohlen, dass Sie Ihre Client Portbereiche als Teilmenge ihrer Server Portbereiche festlegen.</span><span class="sxs-lookup"><span data-stu-id="e8383-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="e8383-143">Zudem haben Sie vielleicht festgestellt, dass auf den Servern 8348 Ports für die Anwendungsfreigabe reserviert wurden, auf den Clients jedoch lediglich 20 Ports.</span><span class="sxs-lookup"><span data-stu-id="e8383-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="e8383-144">Auch dies wird empfohlen, ist aber keine harte und schnelle Regel.</span><span class="sxs-lookup"><span data-stu-id="e8383-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="e8383-145">Im Allgemeinen können Sie jeden verfügbaren Port in Betracht ziehen, eine einzelne Kommunikationssitzung darzustellen: Wenn Sie 100 Ports in einem Portbereich verfügbar haben, bedeutet dies, dass der fragliche Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="e8383-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="e8383-146">Da Server wahrscheinlich an weitaus mehr Unterhaltungen als Clients beteiligt sind, ist es sinnvoll, auf den Servern viel mehr Ports als auf den Clients zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e8383-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="e8383-147">Wenn Sie auf einem Client 20 Ports für die Anwendungsfreigabe reservieren, bedeutet dies, dass ein Benutzer auf dem angegebenen Gerät an 20 Anwendungssitzungen gleichzeitig teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="e8383-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="e8383-148">Dies sollte für die allermeisten Benutzer ausreichend sein.</span><span class="sxs-lookup"><span data-stu-id="e8383-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="e8383-149">Um die vorherigen Portbereiche ihrer globalen Sammlung von Konferenz Konfigurationseinstellungen zuzuweisen, können Sie den folgenden Skype for Business Server-Verwaltungsshell-Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="e8383-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="e8383-150">Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="e8383-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="e8383-151">Einzelne Benutzer müssen sich von Skype for Business abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="e8383-152">Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e8383-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="e8383-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8383-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="e8383-154">Konfigurieren von Quality of Service Policies für Clients, die unter Windows 10 betrieben werden</span><span class="sxs-lookup"><span data-stu-id="e8383-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="e8383-155">Zusätzlich zur Angabe von Portbereichen für die Verwendung durch Ihre Skype for Business Clients müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputern angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="e8383-156">(Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputern angewendet werden.) Diese Informationen gelten nur für Computer mit dem Skype for Business-Client und Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e8383-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="e8383-157">Im folgenden Beispiel werden diese Sätze von Portbereichen zum Erstellen einer audiorichtlinie und einer Video Richtlinie verwendet:</span><span class="sxs-lookup"><span data-stu-id="e8383-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8383-158">Client-Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="e8383-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="e8383-159">Anfang des Portbereichs</span><span class="sxs-lookup"><span data-stu-id="e8383-159">Port Start</span></span></th>
<th><span data-ttu-id="e8383-160">Portbereich</span><span class="sxs-lookup"><span data-stu-id="e8383-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8383-161">Audio</span><span class="sxs-lookup"><span data-stu-id="e8383-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="e8383-162">50020</span><span class="sxs-lookup"><span data-stu-id="e8383-162">50020</span></span></p></td>
<td><p><span data-ttu-id="e8383-163">20</span><span class="sxs-lookup"><span data-stu-id="e8383-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8383-164">Video</span><span class="sxs-lookup"><span data-stu-id="e8383-164">Video</span></span></p></td>
<td><p><span data-ttu-id="e8383-165">58000</span><span class="sxs-lookup"><span data-stu-id="e8383-165">58000</span></span></p></td>
<td><p><span data-ttu-id="e8383-166">20</span><span class="sxs-lookup"><span data-stu-id="e8383-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8383-167">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="e8383-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="e8383-168">42000</span><span class="sxs-lookup"><span data-stu-id="e8383-168">42000</span></span></p></td>
<td><p><span data-ttu-id="e8383-169">20</span><span class="sxs-lookup"><span data-stu-id="e8383-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8383-170">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="e8383-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="e8383-171">42020</span><span class="sxs-lookup"><span data-stu-id="e8383-171">42020</span></span></p></td>
<td><p><span data-ttu-id="e8383-172">20</span><span class="sxs-lookup"><span data-stu-id="e8383-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e8383-173">Um eine Quality of Service-audiorichtlinie für Windows 10-Computer zu erstellen, melden Sie sich zunächst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e8383-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="e8383-174">Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie im **Startmenü**auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="e8383-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="e8383-175">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8383-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="e8383-176">Wenn sich beispielsweise alle Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Organisationseinheit "Client" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="e8383-177">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **GPO in dieser Domäne erstellen, und verknüpfen Sie Sie hier**.</span><span class="sxs-lookup"><span data-stu-id="e8383-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="e8383-178">Geben Sie im Dialogfeld **neues GPO** in das Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8383-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="e8383-179">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e8383-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="e8383-180">Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor den Knoten **Computer Konfiguration**, dann **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e8383-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="e8383-181">Geben Sie im Dialogfeld **richtlinienbasierter QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="e8383-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="e8383-182">Klicken Sie auf \*\* 	DSCP-Wert angeben\*\* und legen Sie den Wert auf **46** fest.</span><span class="sxs-lookup"><span data-stu-id="e8383-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="e8383-183">Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e8383-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="e8383-184">Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem ausführbaren Namen**aus, geben Sie **lync. exe** als Namen ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e8383-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="e8383-185">Mit dieser Einstellung wird die Richtlinie angewiesen, nur übereinstimmenden Datenverkehr vom Skype for Business Client zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="e8383-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="e8383-186">Stellen Sie auf der dritten Seite sicher, dass **jede Quell-IP-Adresse** und **jede Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e8383-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="e8383-187">Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="e8383-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="e8383-188">Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus.</span><span class="sxs-lookup"><span data-stu-id="e8383-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="e8383-189">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="e8383-190">Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer**an, **aus diesem Quell Port oder-Bereich aus**.</span><span class="sxs-lookup"><span data-stu-id="e8383-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="e8383-191">Geben Sie im dazugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8383-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="e8383-192">Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den audiodatenverkehr reserviert haben, geben Sie den Portbereich unter Verwendung dieses Formats ein: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="e8383-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="e8383-193">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e8383-193">Click **Finish**.</span></span>

<span data-ttu-id="e8383-194">Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8383-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="e8383-195">Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e8383-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="e8383-196">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen.</span><span class="sxs-lookup"><span data-stu-id="e8383-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="e8383-197">Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest.</span><span class="sxs-lookup"><span data-stu-id="e8383-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="e8383-198">(Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen als den für Audio verwendeten.)</span><span class="sxs-lookup"><span data-stu-id="e8383-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="e8383-199">Verwenden Sie den zuvor konfigurierten Portbereich für den Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="e8383-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="e8383-200">Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, legen Sie den Portbereich auf den folgenden Wert fest: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="e8383-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="e8383-201">Wenn Sie sich dafür entscheiden, eine Richtlinie zum Verwalten des Datenverkehrs für die Anwendungsfreigabe zu erstellen, müssen Sie diese Substitutionen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="e8383-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="e8383-202">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype for Business Server Anwendungsfreigabe**).</span><span class="sxs-lookup"><span data-stu-id="e8383-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="e8383-203">Legen Sie den DSCP-Wert auf **24** statt auf 46 fest.</span><span class="sxs-lookup"><span data-stu-id="e8383-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="e8383-204">(Auch hier muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="e8383-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="e8383-205">Verwenden Sie den zuvor konfigurierten Portbereich für den Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="e8383-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="e8383-206">Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf den folgenden Wert fest: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="e8383-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="e8383-207">Für eine Datei Übertragungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="e8383-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="e8383-208">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype for Business Server Dateiübertragungen**).</span><span class="sxs-lookup"><span data-stu-id="e8383-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="e8383-209">Legen Sie den DSCP-Wert auf **14**fest.</span><span class="sxs-lookup"><span data-stu-id="e8383-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="e8383-210">(Wieder muss dieser Wert nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)</span><span class="sxs-lookup"><span data-stu-id="e8383-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="e8383-211">Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e8383-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="e8383-212">Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf den folgenden Wert fest: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="e8383-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="e8383-213">Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Clientcomputern aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e8383-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="e8383-214">Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="e8383-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="e8383-215">Dieser Befehl kann in jedem Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8383-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="e8383-216">Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e8383-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="e8383-217">Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten.</span><span class="sxs-lookup"><span data-stu-id="e8383-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="e8383-218">Sie sollten nicht auf Server angewendet werden, auf denen Skype for Business Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8383-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="e8383-219">Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="e8383-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="e8383-220">Klicken Sie auf **Start**, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e8383-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="e8383-221">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="e8383-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="e8383-222">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="e8383-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="e8383-223">Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="e8383-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="e8383-224">Nachdem Sie den neuen Registrierungsschlüssel erstellt haben, geben Sie **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="e8383-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="e8383-225">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="e8383-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="e8383-226">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="e8383-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="e8383-227">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="e8383-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="e8383-228">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8383-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="e8383-229">Schließen Sie den Registrierungs-Editor, und Eboot Sie Ihren Computer.</span><span class="sxs-lookup"><span data-stu-id="e8383-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="e8383-230">Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern</span><span class="sxs-lookup"><span data-stu-id="e8383-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="e8383-231">Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, können gelegentlich Probleme auftreten, bei denen DSCP-Werte als "$ 00" und nicht als konfigurierter Wert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="e8383-232">Dies tritt in der Regel auf Computern auf, auf denen einer oder mehrere Netzwerkadapter nicht auf Ihre Active Directory Domäne zugreifen können (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="e8383-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="e8383-233">In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, Sie werden jedoch nicht für Adapter markiert, die nicht auf die Domäne zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e8383-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="e8383-234">Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer markieren möchten, einschließlich Adapter, die keinen Zugriff auf Ihre Domäne haben, müssen Sie einen Wert für die Registrierung hinzufügen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e8383-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="e8383-235">Führen Sie dafür die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e8383-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="e8383-236">Klicken Sie auf **Start**, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e8383-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="e8383-237">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="e8383-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="e8383-238">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="e8383-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="e8383-239">Wenn kein Registrierungsschlüssel mit dem Namen **QoS** angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="e8383-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="e8383-240">Geben Sie nach dem Erstellen des neuen Schlüssels **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="e8383-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="e8383-241">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="e8383-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="e8383-242">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="e8383-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="e8383-243">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="e8383-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="e8383-244">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten den Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8383-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="e8383-245">Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="e8383-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8383-246">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8383-246">See also</span></span>

[<span data-ttu-id="e8383-247">Erstellen eines Gruppenrichtlinienobjekts in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8383-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
