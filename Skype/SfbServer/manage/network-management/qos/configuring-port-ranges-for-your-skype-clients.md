---
title: Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Portbereiche für Clients, die auf Windows-10 für Ihre Clients und Konfigurieren von Quality of Service-Richtlinien in Skype für Business Server konfigurieren.
ms.openlocfilehash: 2e5328406634302a1b076eec8466e7f7b9245150
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881521"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="5d13d-103">Konfigurieren von Portbereichen und einer Richtlinie Quality of Service für Clients in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="5d13d-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="5d13d-104">In diesem Artikel wird beschrieben, wie Portbereiche für Clients, die auf Windows-10 für Ihre Clients und Konfigurieren von Quality of Service-Richtlinien in Skype für Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5d13d-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="5d13d-105">Konfigurieren von Portbereichen</span><span class="sxs-lookup"><span data-stu-id="5d13d-105">Configure port ranges</span></span>

<span data-ttu-id="5d13d-106">In der Standardeinstellung Skype Business-Clientanwendungen können einen beliebigen Port zwischen verwenden ports 1024 und 65535, wenn in einer kommunikationssitzung; beteiligt Dies ist, da bestimmte Portbereiche für Clients nicht automatisch aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="5d13d-107">Um die Quality of Service verwenden, jedoch müssen Sie die verschiedenen Typen von Datenverkehr (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) neu zuordnen zu einer Reihe von eindeutigen Portbereiche.</span><span class="sxs-lookup"><span data-stu-id="5d13d-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="5d13d-108">Dies kann mithilfe des Cmdlets Set-CsConferencingConfiguration erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="5d13d-109">Endbenutzer können nicht diese Änderungen selbst vornehmen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="5d13d-110">Port kann nur durch Administratoren mit dem Cmdlet Set-CsConferencingConfiguration geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="5d13d-111">Sie können bestimmen, welche Portbereiche derzeit für kommunikationssitzungen verwendet werden, durch den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="5d13d-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="5d13d-112">Unter der Annahme, dass Sie seit der Installation von Skype für Business Server keine Änderungen an den konferenzeinstellungen vorgenommen haben, sollten Sie ähnliche Informationen erhalten, die diese Eigenschaftswerte enthalten:</span><span class="sxs-lookup"><span data-stu-id="5d13d-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="5d13d-113">Wenn Sie die vorherigen Ausgabe genau betrachten, sehen Sie zwei Aspekte von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="5d13d-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="5d13d-114">Zunächst wird die Parameter ClientMediaPortRangeEnabled-Eigenschaft auf False festgelegt:</span><span class="sxs-lookup"><span data-stu-id="5d13d-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="5d13d-115">Das ist wichtig, da, wenn diese Eigenschaft auf False festgelegt ist, Skype für Business Clients zwischen jeden anderen verfügbaren Port verwenden, 1024 ports und 65535, wenn in einer kommunikationssitzung; beteiligt Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="5d13d-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="5d13d-116">Wenn Sie einen angegebenen Satz von Ports Verwendung einschränken möchten (und dies Was möchten Sie tun ist, wenn Sie, zum Implementieren der Quality planen of Service), müssen Sie zuerst Client Media Portbereiche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5d13d-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="5d13d-117">Dies kann mithilfe des folgenden Windows PowerShell-Befehls:</span><span class="sxs-lookup"><span data-stu-id="5d13d-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="5d13d-118">Mit dem vorstehende Befehl ermöglicht Client Media Portbereiche für die globale Auflistung der konferenzkonfigurationseinstellungen. Diese Einstellungen können jedoch auch auf Standortebene und/oder die auf Dienstebene (nur für den Konferenzserver Dienst) angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="5d13d-119">Geben Sie die Identität dieser Website oder Server aktivieren, um clientmediendaten Bereiche für einen bestimmten Standort oder Server, port, beim Aufruf von Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="5d13d-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="5d13d-120">Alternativ können Sie diesen Befehl verwenden, um Portbereiche für alle konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="5d13d-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="5d13d-121">Zweitens von Bedeutung, den Sie bemerken ist, dass die Beispielausgabe sehen, dass standardmäßig die Medien Bereiche legen für jeden Typ von Netzwerkdatenverkehr port identisch sind:</span><span class="sxs-lookup"><span data-stu-id="5d13d-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="5d13d-122">Um QoS zu implementieren, müssen alle diese Portbereiche eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5d13d-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="5d13d-123">Beispielsweise können Sie die Portbereiche wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5d13d-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d13d-124">Typ des Clientdatenverkehrs</span><span class="sxs-lookup"><span data-stu-id="5d13d-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="5d13d-125">Anfang des Portbereichs</span><span class="sxs-lookup"><span data-stu-id="5d13d-125">Port Start</span></span></th>
<th><span data-ttu-id="5d13d-126">Portbereich</span><span class="sxs-lookup"><span data-stu-id="5d13d-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d13d-127">Audio</span><span class="sxs-lookup"><span data-stu-id="5d13d-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="5d13d-128">50020</span><span class="sxs-lookup"><span data-stu-id="5d13d-128">50020</span></span></p></td>
<td><p><span data-ttu-id="5d13d-129">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d13d-130">Video</span><span class="sxs-lookup"><span data-stu-id="5d13d-130">Video</span></span></p></td>
<td><p><span data-ttu-id="5d13d-131">58000</span><span class="sxs-lookup"><span data-stu-id="5d13d-131">58000</span></span></p></td>
<td><p><span data-ttu-id="5d13d-132">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d13d-133">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="5d13d-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="5d13d-134">42000</span><span class="sxs-lookup"><span data-stu-id="5d13d-134">42000</span></span></p></td>
<td><p><span data-ttu-id="5d13d-135">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d13d-136">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="5d13d-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="5d13d-137">42020</span><span class="sxs-lookup"><span data-stu-id="5d13d-137">42020</span></span></p></td>
<td><p><span data-ttu-id="5d13d-138">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5d13d-139">In der obigen Tabelle darstellen clientportbereiche eine Teilmenge der die Portbereiche für Ihre Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5d13d-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="5d13d-140">Beispielsweise wurde auf den Servern, die Anwendungsfreigabe so konfiguriert, dass Ports 40803 bis 49151 verwenden; auf den Clientcomputern ist die Anwendungsfreigabe konfiguriert 42000 über 42019 Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="5d13d-141">Hierzu auch erfolgt hauptsächlich zum Vereinfachen der Verwaltung von QoS: Clientports müssen nicht unbedingt eine Teilmenge der auf dem Server verwendeten Ports darstellen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="5d13d-142">(Beispielsweise konnte auf den Clientcomputern Sie konfigurieren, beispielsweise Ports 10000 über 10019 zu verwenden, um die Anwendungsfreigabe.) Es wird jedoch empfohlen, dass Sie Ihre Client herstellen Port ranges eine Teilmenge der serverportbereiche.</span><span class="sxs-lookup"><span data-stu-id="5d13d-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="5d13d-143">Darüber hinaus Sie möglicherweise bemerkt, dass 8348 Ports für die Anwendungsfreigabe auf den Servern stillgelegte wurden, aber nur 20 Ports für die Anwendungsfreigabe auf den Clients stillgelegte wurden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="5d13d-144">Dies zu, wird empfohlen, aber es ist keine Codestrukturen Regel.</span><span class="sxs-lookup"><span data-stu-id="5d13d-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="5d13d-145">Im Allgemeinen können Sie jeden verfügbaren Port zur Darstellung einer einzelnen kommunikationssitzung berücksichtigen: bei 100 Ports in einem Portbereich zur Verfügung, die bedeutet, dass der betreffende Computer teilnehmen konnten, maximal 100 kommunikationssitzungen an jedem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="5d13d-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="5d13d-146">Da Server wahrscheinlich als Clients viele weitere Unterhaltungen teilnimmt, ist es sinnvoll, viele weitere Ports auf den Servern als auf Clients zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="5d13d-147">Einstellung Aside 20 Ports für die Anwendungsfreigabe auf einem Client bedeutet, dass ein Benutzer in 20 anwendungsfreigabesitzungen auf dem angegebenen Gerät und alle gleichzeitig teilnehmen konnten.</span><span class="sxs-lookup"><span data-stu-id="5d13d-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="5d13d-148">Die sollte für den Großteil Ihrer Benutzer ausreichend nachweisen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="5d13d-149">Um die obigen Portbereiche Ihrer globalen Auflistung der konferenzkonfigurationseinstellungen zuzuweisen, können Sie die folgenden Skype für Business Server Management Shell-Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="5d13d-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="5d13d-150">Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle konferenzkonfigurationseinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="5d13d-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="5d13d-151">Einzelne Benutzer müssen Abmelden von Skype für Unternehmen und dann erneut anmelden, bevor diese Änderungen tatsächlich in Kraft treten.</span><span class="sxs-lookup"><span data-stu-id="5d13d-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="5d13d-152">Sie können auch die Medien clientportbereiche aktivieren, und weisen Sie diese Portbereiche mit einem einzigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="5d13d-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="5d13d-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d13d-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="5d13d-154">Konfigurieren von Quality of Service-Richtlinien für Clients, die auf Windows-10</span><span class="sxs-lookup"><span data-stu-id="5d13d-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="5d13d-155">Zusätzlich zur Portbereiche für die Verwendung durch Ihre Skype für Business Clients angeben, müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d13d-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="5d13d-156">(Die Quality of Service-Richtlinien für Konferenz-, Anwendungs- und Mediation Server erstellt sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für die Skype für Business-Client und Windows-10-Computern.</span><span class="sxs-lookup"><span data-stu-id="5d13d-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="5d13d-157">Im folgenden Beispiel wird mit dieser Gruppe von Portbereiche auf um eine Audio- und eine videorichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="5d13d-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d13d-158">Typ des Clientdatenverkehrs</span><span class="sxs-lookup"><span data-stu-id="5d13d-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="5d13d-159">Anfang des Portbereichs</span><span class="sxs-lookup"><span data-stu-id="5d13d-159">Port Start</span></span></th>
<th><span data-ttu-id="5d13d-160">Portbereich</span><span class="sxs-lookup"><span data-stu-id="5d13d-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d13d-161">Audio</span><span class="sxs-lookup"><span data-stu-id="5d13d-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="5d13d-162">50020</span><span class="sxs-lookup"><span data-stu-id="5d13d-162">50020</span></span></p></td>
<td><p><span data-ttu-id="5d13d-163">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d13d-164">Video</span><span class="sxs-lookup"><span data-stu-id="5d13d-164">Video</span></span></p></td>
<td><p><span data-ttu-id="5d13d-165">58000</span><span class="sxs-lookup"><span data-stu-id="5d13d-165">58000</span></span></p></td>
<td><p><span data-ttu-id="5d13d-166">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d13d-167">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="5d13d-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="5d13d-168">42000</span><span class="sxs-lookup"><span data-stu-id="5d13d-168">42000</span></span></p></td>
<td><p><span data-ttu-id="5d13d-169">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d13d-170">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="5d13d-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="5d13d-171">42020</span><span class="sxs-lookup"><span data-stu-id="5d13d-171">42020</span></span></p></td>
<td><p><span data-ttu-id="5d13d-172">20</span><span class="sxs-lookup"><span data-stu-id="5d13d-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5d13d-173">Zum Erstellen einer audio Quality of Service-Richtlinie für Windows 10 Computer zuerst melden Sie sich an einem Computer, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d13d-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="5d13d-174">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Die Gruppenrichtlinien-Verwaltungskonsole**), und führen Sie dann die folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5d13d-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="5d13d-175">Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d13d-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="5d13d-176">Beispielsweise sollte alle Client-Computer in einer Organisationseinheit mit dem Namen Clients befinden, die neue Richtlinie in der Organisationseinheit Client erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="5d13d-177">Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="5d13d-178">Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** Geben Sie im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="5d13d-179">Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="5d13d-180">In den Gruppenrichtlinienverwaltungs-Editor, erweitern Sie **Computerkonfiguration**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="5d13d-181">Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="5d13d-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="5d13d-182">Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="5d13d-183">Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="5d13d-184">Klicken Sie auf der nächsten Seite stellen Sie sicher, dass **Alle Anwendungen** aktiviert ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="5d13d-185">Diese Einstellung weist das Netzwerk zum Nachschlagen für alle Pakete mit einem DSCP-Markierung der 46, nicht nur Pakete, die von einer bestimmten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="5d13d-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="5d13d-186">Stellen Sie auf der dritten Seite sicher, dass **alle Quell-IP-Adresse** und **einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="5d13d-187">Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="5d13d-188">Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** .</span><span class="sxs-lookup"><span data-stu-id="5d13d-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="5d13d-189">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die zwei Netzwerkprotokolle von Skype für Business Server und seine Clientanwendungen am häufigsten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d13d-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="5d13d-190">Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer** **aus dieser Quellport oder der Bereich**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="5d13d-191">Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="5d13d-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="5d13d-192">Angenommen, wenn Sie Ports 50020 über reserviert ports 50039 audio Datenverkehr Geben Sie den Portbereich, der mit diesem Format: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="5d13d-193">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-193">Click **Finish**.</span></span>

<span data-ttu-id="5d13d-194">Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie klicken Sie dann eine zweite Richtlinie für Video erstellen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="5d13d-195">Führen Sie zum Erstellen einer Richtlinie für Video dieselbe grundlegende Prozedur, die Sie beim Erstellen der Richtlinie audio befolgt, wodurch dieser Platzhalter ein:</span><span class="sxs-lookup"><span data-stu-id="5d13d-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="5d13d-196">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen an.</span><span class="sxs-lookup"><span data-stu-id="5d13d-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="5d13d-197">Legen Sie den DSCP-Wert auf **34** anstelle von 46.</span><span class="sxs-lookup"><span data-stu-id="5d13d-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="5d13d-198">(Wie bereits erwähnt, müssen Sie nicht den DSCP-Wert 34 verwenden; Sie können einen anderen DSCP-Wert als der für die Audiodaten verwendeten einfach müssen zuweisen.)</span><span class="sxs-lookup"><span data-stu-id="5d13d-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="5d13d-199">Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="5d13d-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="5d13d-200">Beispielsweise wenn Sie Ports 58000 über 58019 für Video reserviert haben, setzen Sie den Portbereich hinzu: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="5d13d-201">Wenn Sie eine Richtlinie zur Verwaltung der Anwendungsfreigabe Anwendungsdatenverkehr erstellen möchten, stellen Sie dieser Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="5d13d-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="5d13d-202">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server die Anwendungsfreigabe**).</span><span class="sxs-lookup"><span data-stu-id="5d13d-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="5d13d-203">Legen Sie den DSCP-Wert, auf **24** anstelle von 46.</span><span class="sxs-lookup"><span data-stu-id="5d13d-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="5d13d-204">(Erneut, dieser Wert muss nicht unbedingt 24 sein; es einfach identisch sein als die DSCP-Werte für Audio und Video verwendet.)</span><span class="sxs-lookup"><span data-stu-id="5d13d-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="5d13d-205">Verwenden Sie den zuvor konfigurierten Portbereich für video-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="5d13d-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="5d13d-206">Beispielsweise wenn Sie Ports 42000 über 42019 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich hinzu: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="5d13d-207">Für eine dateiübertragungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="5d13d-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="5d13d-208">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **Skype für Business Server Dateiübertragungen**).</span><span class="sxs-lookup"><span data-stu-id="5d13d-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="5d13d-209">Legen Sie den DSCP-Wert auf **14**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="5d13d-210">(In diesem Fall dieser Wert muss nicht 14 sein; einfach das Ereignis muss einen eindeutigen DSCP-Code.)</span><span class="sxs-lookup"><span data-stu-id="5d13d-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="5d13d-211">Verwenden Sie den zuvor konfigurierten Portbereich für Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5d13d-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="5d13d-212">Beispielsweise wenn Sie Ports 42020 über 42039 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich hinzu: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="5d13d-213">Die neuen Richtlinien erstellten werden nicht erst wirksam Gruppenrichtlinien auf den Clientcomputern aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d13d-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="5d13d-214">Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="5d13d-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="5d13d-215">Diesen Befehl können Sie über ein beliebiges Befehlsfenster ausführen, das mit Administratoranmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5d13d-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="5d13d-216">Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="5d13d-217">Überwachungsfunktionen Sie benötigen, beachten Sie, dass diese Richtlinien auf Ihren Clientcomputern ausgerichtet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="5d13d-218">Sie sollten nicht auf Servern mit Skype für Business Server angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="5d13d-219">Um sicherzustellen, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert markiert sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren abschließen:</span><span class="sxs-lookup"><span data-stu-id="5d13d-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="5d13d-220">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="5d13d-221">Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5d13d-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="5d13d-222">Erweitern Sie im Registrierungs-Editor, **HKEY\_lokale\_Computer**, erweitern Sie **SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="5d13d-223">Mit der rechten Maustaste **Tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="5d13d-224">Nach dem Erstellen des neuen Registrierungsschlüssels Geben Sie **QoS**, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="5d13d-225">Mit der rechten Maustaste **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="5d13d-226">Nach dem Erstellen des neuen Registrierungswerts Geben Sie die **Authentifizierung auf Netzwerkebene nicht verwenden**, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="5d13d-227">Doppelklicken Sie auf die **Authentifizierung auf Netzwerkebene nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="5d13d-228">Klicken Sie im Dialogfeld **Zeichenfolge bearbeiten** Geben Sie in das Feld **Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="5d13d-229">Schließen Sie den Registrierungs-Editor und Eboot Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="5d13d-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="5d13d-230">Konfigurieren von Quality of Service auf Computern mit mehreren Netzwerkadaptern</span><span class="sxs-lookup"><span data-stu-id="5d13d-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="5d13d-231">Wenn Sie einen Computer, der mehrere Netzwerkadapter verfügt verfügen, können Sie gelegentlich ausführen zu Problemen, an die DSCP-Werte als 0 x 00 angezeigt werden, anstatt den konfigurierten Wert.</span><span class="sxs-lookup"><span data-stu-id="5d13d-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="5d13d-232">Dies tritt in der Regel auf Computern, auf dem eine oder mehrere der Netzwerkadapter nicht auf Ihrer Active Directory-Domäne zugreifen sind (z. B., wenn diese Adapter für ein privates Netzwerk verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="5d13d-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="5d13d-233">In solchen Fällen, werden DSCP-Werte für den Adapter gekennzeichnet, die auf die Domäne zugreifen können, aber nicht für Adapter, die Zugriff auf die Domäne können nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="5d13d-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="5d13d-234">Wenn Sie Tag DSCP-Werte für alle Netzwerkadapter in einem Computer, einschließlich Adapter, die an Ihre Domäne keinen Zugriff haben möchten müssen Sie zum Hinzufügen und konfigurieren einen Wert in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="5d13d-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="5d13d-235">Können Sie das folgende Verfahren abschließen erfolgen:</span><span class="sxs-lookup"><span data-stu-id="5d13d-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="5d13d-236">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="5d13d-237">Geben Sie im Dialogfeld **Ausführen** **regedit ein**, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5d13d-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="5d13d-238">Erweitern Sie im Registrierungs-Editor, **HKEY\_lokale\_Computer**, erweitern Sie **SYSTEM**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="5d13d-239">Wenn Sie einen Registrierungsschlüssel mit der Bezeichnung **QoS** dann **Tcpip**mit der rechten Maustaste nicht angezeigt werden, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="5d13d-240">Nachdem der neue Schlüssel erstellt wurde, geben Sie **QoS**, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="5d13d-241">Mit der rechten Maustaste **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="5d13d-242">Nach dem Erstellen des neuen Registrierungswerts Geben Sie die **Authentifizierung auf Netzwerkebene nicht verwenden**, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="5d13d-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="5d13d-243">Doppelklicken Sie auf die **Authentifizierung auf Netzwerkebene nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="5d13d-244">Klicken Sie im Dialogfeld **Zeichenfolge bearbeiten** Geben Sie in das Feld **Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d13d-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="5d13d-245">Nach dem Erstellen und konfigurieren den neuen Registrierungswert, müssen Sie zum Neustart des Computers, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="5d13d-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d13d-246">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d13d-246">See also</span></span>

[<span data-ttu-id="5d13d-247">Erstellen eines Gruppenrichtlinienobjekts in Windows 10</span><span class="sxs-lookup"><span data-stu-id="5d13d-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
