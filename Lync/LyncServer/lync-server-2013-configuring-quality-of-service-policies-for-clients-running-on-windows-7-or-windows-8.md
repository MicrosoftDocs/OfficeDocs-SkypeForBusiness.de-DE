---
title: 'Lync Server 2013: Konfigurieren der Dienst Qualitätsrichtlinien für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b36c16056ef378910dc0cd5c885dc7b5d896d860
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="9d2b0-102">Konfigurieren von Dienst Qualitätsrichtlinien in lync Server 2013 für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="9d2b0-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d2b0-103">_**Letztes Änderungsdatum des Themas:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="9d2b0-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="9d2b0-104">Zusätzlich zur Angabe von Portbereichen für die Verwendung durch ihre lync-Clients müssen Sie auch getrennte Dienst Qualitätsrichtlinien erstellen, die auf Clientcomputer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="9d2b0-105">(Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputer angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der lync 2013-Client und entweder Windows 7 oder Windows 8 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="9d2b0-106">Im folgenden Beispiel wird dieser Satz von Portbereichen zum Erstellen einer audiorichtlinie und einer Video Richtlinie verwendet:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d2b0-107">Client Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="9d2b0-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="9d2b0-108">Port Start</span><span class="sxs-lookup"><span data-stu-id="9d2b0-108">Port Start</span></span></th>
<th><span data-ttu-id="9d2b0-109">Port Bereich</span><span class="sxs-lookup"><span data-stu-id="9d2b0-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d2b0-110">Audio</span><span class="sxs-lookup"><span data-stu-id="9d2b0-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-111">50020</span><span class="sxs-lookup"><span data-stu-id="9d2b0-111">50020</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-112">20</span><span class="sxs-lookup"><span data-stu-id="9d2b0-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b0-113">Video</span><span class="sxs-lookup"><span data-stu-id="9d2b0-113">Video</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-114">58000</span><span class="sxs-lookup"><span data-stu-id="9d2b0-114">58000</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-115">20</span><span class="sxs-lookup"><span data-stu-id="9d2b0-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d2b0-116">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="9d2b0-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-117">42000</span><span class="sxs-lookup"><span data-stu-id="9d2b0-117">42000</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-118">20</span><span class="sxs-lookup"><span data-stu-id="9d2b0-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d2b0-119">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="9d2b0-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-120">42020</span><span class="sxs-lookup"><span data-stu-id="9d2b0-120">42020</span></span></p></td>
<td><p><span data-ttu-id="9d2b0-121">20</span><span class="sxs-lookup"><span data-stu-id="9d2b0-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9d2b0-122">Wenn Sie eine Quality of Service-audiorichtlinie für Windows 7-oder Windows 8-Computer erstellen möchten, melden Sie sich zuerst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="9d2b0-123">Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="9d2b0-124">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="9d2b0-125">Wenn sich beispielsweise alle Ihre Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Client Organisationseinheit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="9d2b0-126">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="9d2b0-127">Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync-Audio**), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="9d2b0-128">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="9d2b0-129">Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor **Computer Konfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="9d2b0-130">Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (beispielsweise **lync-Audio**) ein.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="9d2b0-131">Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="9d2b0-132">Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="9d2b0-133">Stellen Sie auf der nächsten Seite sicher, dass **alle Anwendungen** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-133">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="9d2b0-134">Mit dieser Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit einer DSCP-Kennzeichnung von 46 zu suchen, nicht nur von Paketen, die von einer bestimmten Anwendung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-134">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="9d2b0-135">Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-IP-Adresse** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="9d2b0-136">Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) diese Pakete gesendet werden und auf welchem Computer (IP-Adresse) diese Pakete empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="9d2b0-137">Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** .</span><span class="sxs-lookup"><span data-stu-id="9d2b0-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="9d2b0-138">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="9d2b0-139">Wählen Sie unter der Überschrift **die Quellportnummer**aus, und wählen Sie **aus diesem Quell Port oder-Bereich aus**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="9d2b0-140">Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="9d2b0-141">Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="9d2b0-142">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-142">Click **Finish**.</span></span>

<span data-ttu-id="9d2b0-143">Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="9d2b0-144">Wenn Sie eine Richtlinie für Video erstellen möchten, führen Sie die gleichen grundlegenden Verfahren aus, die Sie beim Erstellen der audiorichtlinie befolgt haben, indem Sie diese Substitutionen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="9d2b0-145">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync-Video**).</span><span class="sxs-lookup"><span data-stu-id="9d2b0-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="9d2b0-146">Setzen Sie den DSCP-Wert auf **34** statt auf 46.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="9d2b0-147">(Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen, als den für Audio verwendeten.)</span><span class="sxs-lookup"><span data-stu-id="9d2b0-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="9d2b0-148">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="9d2b0-149">Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, setzen Sie den Portbereich auf Folgendes: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="9d2b0-150">Wenn Sie sich entscheiden, eine Richtlinie für die Verwaltung des Anwendungsfreigabe Verkehrs zu erstellen, führen Sie diese Substitutionen aus:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="9d2b0-151">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise die **lync Server-Anwendungsfreigabe**).</span><span class="sxs-lookup"><span data-stu-id="9d2b0-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="9d2b0-152">Setzen Sie den DSCP-Wert auf **24** anstatt auf 46.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="9d2b0-153">(Wiederum muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="9d2b0-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="9d2b0-154">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="9d2b0-155">Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="9d2b0-156">Für eine Datei Übertragungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="9d2b0-157">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server-Dateiübertragungen**).</span><span class="sxs-lookup"><span data-stu-id="9d2b0-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="9d2b0-158">Stellen Sie den DSCP-Wert auf **14**ein.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="9d2b0-159">(Dieser Wert muss wiederum nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)</span><span class="sxs-lookup"><span data-stu-id="9d2b0-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="9d2b0-160">Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="9d2b0-161">Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, setzen Sie den Portbereich auf this: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="9d2b0-162">Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Clientcomputern aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="9d2b0-163">Die Gruppenrichtlinien werden zwar automatisch regelmäßig aktualisiert, aber Sie können die sofortige Aktualisierung erzwingen. Dazu führen Sie auf allen Computern, auf denen die Gruppenrichtlinien aktualisiert werden sollen, den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="9d2b0-164">Diesen Befehl können Sie über ein beliebiges Befehlsfenster ausführen, das mit Administratoranmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="9d2b0-165">Um ein Befehlsfenster mit Administratoranmeldeinformationen auszuführen, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="9d2b0-166">Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="9d2b0-167">Sie sollten nicht auf Server angewendet werden, auf denen lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="9d2b0-168">Wenn Sie sicherstellen möchten, dass Netzwerkpakete mit dem entsprechenden DSCP-Wert gekennzeichnet sind, sollten Sie auch einen neuen Registrierungseintrag auf jedem Computer erstellen, indem Sie das folgende Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="9d2b0-169">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="9d2b0-170">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="9d2b0-171">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="9d2b0-172">Klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-172">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="9d2b0-173">Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-173">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="9d2b0-174">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-174">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="9d2b0-175">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-175">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="9d2b0-176">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="9d2b0-177">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="9d2b0-178">Schließen Sie den Registrierungs-Editor, und starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="9d2b0-179">Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern</span><span class="sxs-lookup"><span data-stu-id="9d2b0-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="9d2b0-180">Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, treten möglicherweise gelegentlich Probleme auf, bei denen DSCP-Werte als "$ 00" anstelle des konfigurierten Werts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="9d2b0-181">Dies erfolgt in der Regel auf Computern, auf denen mindestens einer der Netzwerkadapter nicht auf die Active Directory-Domäne zugreifen kann (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="9d2b0-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="9d2b0-182">In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, werden aber nicht für Adapter gekennzeichnet, die nicht auf die Domäne zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="9d2b0-183">Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer, einschließlich Adaptern, die keinen Zugriff auf Ihre Domäne haben, taggen möchten, müssen Sie der Registrierung einen Wert hinzufügen und diesen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="9d2b0-184">Dazu können Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="9d2b0-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="9d2b0-185">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="9d2b0-186">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="9d2b0-187">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="9d2b0-188">Wenn ein Registrierungsschlüssel mit der Bezeichnung **QoS** nicht angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="9d2b0-189">Geben Sie nach dem Erstellen des neuen Schlüssels **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="9d2b0-190">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **neu**, und klicken Sie dann auf **Zeichenfolgenwert**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-190">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="9d2b0-191">Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-191">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="9d2b0-192">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="9d2b0-193">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld Wertdaten den **Wert** **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="9d2b0-194">Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="9d2b0-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

