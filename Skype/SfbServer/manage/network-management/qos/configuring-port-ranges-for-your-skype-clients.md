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
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Dienst Qualitätsrichtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 ausgeführt werden.
ms.openlocfilehash: 2eaf7eb6b10f2aba2665704f973a4dfcddbd4885
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279424"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="c9225-103">Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9225-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="c9225-104">In diesem Artikel wird beschrieben, wie Sie Portbereiche für Ihre Clients konfigurieren und Dienst Qualitätsrichtlinien in Skype for Business Server für Clients konfigurieren, die unter Windows 10 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="c9225-105">Konfigurieren von Portbereichen</span><span class="sxs-lookup"><span data-stu-id="c9225-105">Configure port ranges</span></span>

<span data-ttu-id="c9225-106">Skype for Business-Clientanwendungen können standardmäßig einen beliebigen Port zwischen den Anschlüssen 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="c9225-107">Um die Dienstqualität zu nutzen, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe von eindeutigen Portbereichen neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9225-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="c9225-108">Dies kann mithilfe des Cmdlets "CsConferencingConfiguration" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c9225-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="c9225-109">Endbenutzer können diese Änderungen nicht selbst vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c9225-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="c9225-110">Port Änderungen können nur von Administratoren mit dem Cmdlet "Satz-CsConferencingConfiguration" vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="c9225-111">Sie können bestimmen, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9225-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="c9225-112">Vorausgesetzt, dass Sie seit der Installation von Skype for Business Server keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:</span><span class="sxs-lookup"><span data-stu-id="c9225-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="c9225-113">Wenn Sie die vorhergehende Ausgabe genau betrachten, sehen Sie zwei wichtige Dinge.</span><span class="sxs-lookup"><span data-stu-id="c9225-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="c9225-114">Zuerst ist die ClientMediaPortRangeEnabled-Eigenschaft auf false festgelegt:</span><span class="sxs-lookup"><span data-stu-id="c9225-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="c9225-115">Das ist wichtig, da Skype for Business-Clients, wenn diese Eigenschaft auf "false" festgelegt ist, einen beliebigen verfügbaren Port zwischen den Anschlüssen 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="c9225-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="c9225-116">Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies ist etwas, was Sie tun möchten, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client Medien-Portbereiche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9225-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="c9225-117">Dies kann mithilfe des folgenden Windows PowerShell-Befehls erfolgen:</span><span class="sxs-lookup"><span data-stu-id="c9225-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c9225-118">Der obige Befehl aktiviert Client Medien-Portbereiche für die globale Sammlung von Konferenz Konfigurationseinstellungen; Diese Einstellungen können jedoch auch auf den Website Bereich und/oder den Dienstbereich angewendet werden (nur für den Conferencing Server-Dienst).</span><span class="sxs-lookup"><span data-stu-id="c9225-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="c9225-119">Wenn Sie die Client Medien-Portbereiche für eine bestimmte Website oder einen bestimmten Server aktivieren möchten, geben Sie die Identität dieser Website oder des Servers beim Aufrufen von CsConferencingConfiguration an:</span><span class="sxs-lookup"><span data-stu-id="c9225-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c9225-120">Sie können diesen Befehl auch verwenden, um Portbereiche für alle Ihre Konferenz Konfigurationseinstellungen gleichzeitig zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c9225-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c9225-121">Wichtig ist, dass die Beispielausgabe zeigt, dass standardmäßig die für die einzelnen Netzwerkdatenverkehr-Typen festgelegten Medien Portbereiche identisch sind:</span><span class="sxs-lookup"><span data-stu-id="c9225-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="c9225-122">Um QoS zu implementieren, müssen alle diese Portbereiche eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="c9225-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="c9225-123">So können Sie beispielsweise die Portbereiche wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c9225-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9225-124">Client Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="c9225-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c9225-125">Port Start</span><span class="sxs-lookup"><span data-stu-id="c9225-125">Port Start</span></span></th>
<th><span data-ttu-id="c9225-126">Port Bereich</span><span class="sxs-lookup"><span data-stu-id="c9225-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9225-127">Audio</span><span class="sxs-lookup"><span data-stu-id="c9225-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="c9225-128">50020</span><span class="sxs-lookup"><span data-stu-id="c9225-128">50020</span></span></p></td>
<td><p><span data-ttu-id="c9225-129">20</span><span class="sxs-lookup"><span data-stu-id="c9225-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9225-130">Video</span><span class="sxs-lookup"><span data-stu-id="c9225-130">Video</span></span></p></td>
<td><p><span data-ttu-id="c9225-131">58000</span><span class="sxs-lookup"><span data-stu-id="c9225-131">58000</span></span></p></td>
<td><p><span data-ttu-id="c9225-132">20</span><span class="sxs-lookup"><span data-stu-id="c9225-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9225-133">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="c9225-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c9225-134">42000</span><span class="sxs-lookup"><span data-stu-id="c9225-134">42000</span></span></p></td>
<td><p><span data-ttu-id="c9225-135">20</span><span class="sxs-lookup"><span data-stu-id="c9225-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9225-136">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="c9225-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c9225-137">42020</span><span class="sxs-lookup"><span data-stu-id="c9225-137">42020</span></span></p></td>
<td><p><span data-ttu-id="c9225-138">20</span><span class="sxs-lookup"><span data-stu-id="c9225-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9225-139">In der obigen Tabelle stellen Client-Portbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c9225-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="c9225-140">Auf den Servern wurde die Anwendungsfreigabe beispielsweise so konfiguriert, dass die Ports 40803 bis 49151 verwendet werden. auf den Clientcomputern ist die Anwendungsfreigabe so konfiguriert, dass die Ports 42000 bis 42019 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="c9225-141">Auch dies geschieht in erster Linie, um die Verwaltung von QoS zu vereinfachen: Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen.</span><span class="sxs-lookup"><span data-stu-id="c9225-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="c9225-142">(Beispielsweise können Sie auf den Clientcomputern die Anwendungsfreigabe so konfigurieren, dass die Verwendung von Ports 10000 bis 10019 verwendet wird.) Es wird jedoch empfohlen, dass Sie die Client Portbereiche zu einer Teilmenge der Server Portbereiche machen.</span><span class="sxs-lookup"><span data-stu-id="c9225-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="c9225-143">Darüber hinaus haben Sie möglicherweise festgestellt, dass 8348-Ports für die Anwendungsfreigabe auf den Servern reserviert wurden, aber nur 20 Ports für die Anwendungsfreigabe auf den Clients reserviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c9225-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="c9225-144">Auch dies wird empfohlen, ist aber keine harte und schnelle Regel.</span><span class="sxs-lookup"><span data-stu-id="c9225-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="c9225-145">Im Allgemeinen können Sie jeden verfügbaren Port in Betracht ziehen, um eine einzelne Kommunikationssitzung darzustellen: Wenn Sie 100-Ports in einem Portbereich zur Verfügung haben, bedeutet dies, dass der betreffende Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="c9225-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="c9225-146">Da Server wahrscheinlich an vielen weiteren Unterhaltungen als Clients teilnehmen, ist es sinnvoll, viel mehr Ports auf Servern als auf Clients zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c9225-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="c9225-147">Wenn Sie 20 Ports für die Anwendungsfreigabe auf einem Client beiseite legen, bedeutet dies, dass ein Benutzer an 20 Anwendungsfreigabesitzungen auf dem angegebenen Gerät und alle zur gleichen Zeit teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="c9225-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="c9225-148">Dies sollte für die meisten Benutzer ausreichend sein.</span><span class="sxs-lookup"><span data-stu-id="c9225-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="c9225-149">Wenn Sie der globalen Sammlung von Konferenz Konfigurationseinstellungen die vorhergehenden Portbereiche zuweisen möchten, können Sie den folgenden Befehl der Skype for Business Server-Verwaltungsshell verwenden:</span><span class="sxs-lookup"><span data-stu-id="c9225-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c9225-150">Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenz Konfigurationseinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="c9225-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c9225-151">Einzelne Benutzer müssen sich von Skype for Business abmelden und sich dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="c9225-152">Sie können auch Client Medien-Portbereiche aktivieren und dann mithilfe eines einzigen Befehls Diese Portbereiche zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9225-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="c9225-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9225-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="c9225-154">Konfigurieren von Dienst Qualitätsrichtlinien für Clients, die unter Windows 10 ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="c9225-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="c9225-155">Zusätzlich zur Angabe von Portbereichen für die Verwendung durch Ihre Skype for Business-Clients müssen Sie auch getrennte Dienst Qualitätsrichtlinien erstellen, die auf Clientcomputer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="c9225-156">(Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der Skype for Business-Client und Windows 10 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9225-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="c9225-157">Im folgenden Beispiel wird dieser Satz von Portbereichen zum Erstellen einer audiorichtlinie und einer Video Richtlinie verwendet:</span><span class="sxs-lookup"><span data-stu-id="c9225-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9225-158">Client Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="c9225-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c9225-159">Port Start</span><span class="sxs-lookup"><span data-stu-id="c9225-159">Port Start</span></span></th>
<th><span data-ttu-id="c9225-160">Port Bereich</span><span class="sxs-lookup"><span data-stu-id="c9225-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9225-161">Audio</span><span class="sxs-lookup"><span data-stu-id="c9225-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="c9225-162">50020</span><span class="sxs-lookup"><span data-stu-id="c9225-162">50020</span></span></p></td>
<td><p><span data-ttu-id="c9225-163">20</span><span class="sxs-lookup"><span data-stu-id="c9225-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9225-164">Video</span><span class="sxs-lookup"><span data-stu-id="c9225-164">Video</span></span></p></td>
<td><p><span data-ttu-id="c9225-165">58000</span><span class="sxs-lookup"><span data-stu-id="c9225-165">58000</span></span></p></td>
<td><p><span data-ttu-id="c9225-166">20</span><span class="sxs-lookup"><span data-stu-id="c9225-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9225-167">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="c9225-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c9225-168">42000</span><span class="sxs-lookup"><span data-stu-id="c9225-168">42000</span></span></p></td>
<td><p><span data-ttu-id="c9225-169">20</span><span class="sxs-lookup"><span data-stu-id="c9225-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9225-170">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="c9225-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c9225-171">42020</span><span class="sxs-lookup"><span data-stu-id="c9225-171">42020</span></span></p></td>
<td><p><span data-ttu-id="c9225-172">20</span><span class="sxs-lookup"><span data-stu-id="c9225-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c9225-173">Wenn Sie eine Quality of Service-audiorichtlinie für Windows 10-Computer erstellen möchten, melden Sie sich zuerst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c9225-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="c9225-174">Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c9225-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="c9225-175">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9225-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="c9225-176">Wenn sich beispielsweise alle Ihre Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Client Organisationseinheit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="c9225-177">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.</span><span class="sxs-lookup"><span data-stu-id="c9225-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="c9225-178">Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9225-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="c9225-179">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c9225-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="c9225-180">Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor **Computer Konfiguration**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c9225-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="c9225-181">Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen im Feld **Name** einen Namen für die neue Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="c9225-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="c9225-182">Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest.</span><span class="sxs-lookup"><span data-stu-id="c9225-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="c9225-183">Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c9225-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="c9225-184">Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c9225-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="c9225-185">Mit dieser Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit einer DSCP-Kennzeichnung von 46 zu suchen, nicht nur von Paketen, die von einer bestimmten Anwendung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c9225-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="c9225-186">Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c9225-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="c9225-187">Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="c9225-188">Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** .</span><span class="sxs-lookup"><span data-stu-id="c9225-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="c9225-189">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von Skype for Business Server und seinen Clientanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="c9225-190">Wählen Sie unter der Überschrift **die Quellportnummer**aus, und wählen Sie **aus diesem Quell Port oder-Bereich aus**.</span><span class="sxs-lookup"><span data-stu-id="c9225-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="c9225-191">Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="c9225-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="c9225-192">Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="c9225-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="c9225-193">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c9225-193">Click **Finish**.</span></span>

<span data-ttu-id="c9225-194">Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9225-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="c9225-195">Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="c9225-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="c9225-196">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen.</span><span class="sxs-lookup"><span data-stu-id="c9225-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="c9225-197">Setzen Sie den DSCP-Wert auf **34** statt auf 46.</span><span class="sxs-lookup"><span data-stu-id="c9225-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="c9225-198">(Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen, als den für Audio verwendeten.)</span><span class="sxs-lookup"><span data-stu-id="c9225-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="c9225-199">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="c9225-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="c9225-200">Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="c9225-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="c9225-201">Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Datenverkehrs zu erstellen, nehmen Sie diese Substitutionen vor:</span><span class="sxs-lookup"><span data-stu-id="c9225-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="c9225-202">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **Freigabe von Skype for Business Server-Anwendungen**).</span><span class="sxs-lookup"><span data-stu-id="c9225-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="c9225-203">Setzen Sie den DSCP-Wert auf **24** anstatt auf 46.</span><span class="sxs-lookup"><span data-stu-id="c9225-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="c9225-204">(Wiederum muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="c9225-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="c9225-205">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="c9225-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="c9225-206">Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="c9225-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="c9225-207">Für eine Datei Übertragungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="c9225-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="c9225-208">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **Dateiübertragungen von Skype for Business Server**).</span><span class="sxs-lookup"><span data-stu-id="c9225-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="c9225-209">Stellen Sie den DSCP-Wert auf **14**ein.</span><span class="sxs-lookup"><span data-stu-id="c9225-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="c9225-210">(Dieser Wert muss wiederum nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)</span><span class="sxs-lookup"><span data-stu-id="c9225-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="c9225-211">Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c9225-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="c9225-212">Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="c9225-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="c9225-213">Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Clientcomputern aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c9225-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="c9225-214">Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9225-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="c9225-215">Diesen Befehl können Sie über ein beliebiges Befehlsfenster ausführen, das mit Administratoranmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9225-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="c9225-216">Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c9225-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="c9225-217">Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten.</span><span class="sxs-lookup"><span data-stu-id="c9225-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="c9225-218">Sie sollten nicht auf Server angewendet werden, auf denen Skype for Business Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9225-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="c9225-219">Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9225-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="c9225-220">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c9225-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c9225-221">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="c9225-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="c9225-222">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="c9225-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c9225-223">Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="c9225-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c9225-224">Geben Sie nach dem Erstellen des neuen Registrierungsschlüssels **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c9225-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c9225-225">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="c9225-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="c9225-226">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c9225-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c9225-227">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="c9225-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="c9225-228">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9225-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="c9225-229">Schließen Sie den Registrierungs-Editor, und Eboot Sie Ihren Computer.</span><span class="sxs-lookup"><span data-stu-id="c9225-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="c9225-230">Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern</span><span class="sxs-lookup"><span data-stu-id="c9225-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="c9225-231">Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, treten möglicherweise gelegentlich Probleme auf, bei denen DSCP-Werte als "$ 00" anstelle des konfigurierten Werts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="c9225-232">Dies erfolgt in der Regel auf Computern, auf denen mindestens einer der Netzwerkadapter nicht auf die Active Directory-Domäne zugreifen kann (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="c9225-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="c9225-233">In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, werden aber nicht für Adapter gekennzeichnet, die nicht auf die Domäne zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c9225-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="c9225-234">Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer markieren möchten, einschließlich Adapter, die keinen Zugriff auf Ihre Domäne haben, müssen Sie der Registrierung einen Wert hinzufügen und diesen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9225-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="c9225-235">Dazu können Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9225-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="c9225-236">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c9225-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c9225-237">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="c9225-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="c9225-238">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="c9225-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c9225-239">Wenn ein Registrierungsschlüssel mit der Bezeichnung **QoS** nicht angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="c9225-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c9225-240">Geben Sie nach dem Erstellen des neuen Schlüssels **QoS**ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c9225-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c9225-241">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="c9225-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="c9225-242">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c9225-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c9225-243">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="c9225-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="c9225-244">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9225-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="c9225-245">Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c9225-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9225-246">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9225-246">See also</span></span>

[<span data-ttu-id="c9225-247">Erstellen eines Gruppenrichtlinienobjekts in Windows 10</span><span class="sxs-lookup"><span data-stu-id="c9225-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
