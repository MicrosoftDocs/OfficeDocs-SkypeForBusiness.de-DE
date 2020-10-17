---
title: 'Lync Server 2013: Konfigurieren von Quality of Service Policies für Clients, die auf Windows 7 oder Windows 8'
description: 'Lync Server 2013: Konfigurieren von Quality of Service Policies für Clients, die auf Windows 7 oder Windows 8.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faba5fc54ef73bfc738f94ee7209fc46a7cdc208
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564971"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="c617c-103">Konfigurieren von Quality of Service Policies in lync Server 2013 für Clients, die auf Windows 7 oder Windows 8</span><span class="sxs-lookup"><span data-stu-id="c617c-103">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c617c-104">_**Letztes Änderungsstand des Themas:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="c617c-104">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="c617c-105">Zusätzlich zur Angabe von Portbereichen für die Verwendung durch ihre lync-Clients müssen Sie auch separate Quality of Service-Richtlinien erstellen, die auf Clientcomputern angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c617c-105">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="c617c-106">(Die Dienst Qualitätsrichtlinien, die für Konferenz-, Anwendungs-und Vermittlungsserver erstellt wurden, sollten nicht auf Clientcomputern angewendet werden.) Diese Informationen gelten nur für Computer, auf denen der lync 2013-Client und entweder Windows 7 oder Windows 8.</span><span class="sxs-lookup"><span data-stu-id="c617c-106">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="c617c-107">Im folgenden Beispiel werden diese Sätze von Portbereichen zum Erstellen einer audiorichtlinie und einer Video Richtlinie verwendet:</span><span class="sxs-lookup"><span data-stu-id="c617c-107">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c617c-108">Client-Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="c617c-108">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c617c-109">Anfang des Portbereichs</span><span class="sxs-lookup"><span data-stu-id="c617c-109">Port Start</span></span></th>
<th><span data-ttu-id="c617c-110">Portbereich</span><span class="sxs-lookup"><span data-stu-id="c617c-110">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c617c-111">Audio</span><span class="sxs-lookup"><span data-stu-id="c617c-111">Audio</span></span></p></td>
<td><p><span data-ttu-id="c617c-112">50020</span><span class="sxs-lookup"><span data-stu-id="c617c-112">50020</span></span></p></td>
<td><p><span data-ttu-id="c617c-113">20</span><span class="sxs-lookup"><span data-stu-id="c617c-113">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c617c-114">Video</span><span class="sxs-lookup"><span data-stu-id="c617c-114">Video</span></span></p></td>
<td><p><span data-ttu-id="c617c-115">58000</span><span class="sxs-lookup"><span data-stu-id="c617c-115">58000</span></span></p></td>
<td><p><span data-ttu-id="c617c-116">20</span><span class="sxs-lookup"><span data-stu-id="c617c-116">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c617c-117">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="c617c-117">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c617c-118">42000</span><span class="sxs-lookup"><span data-stu-id="c617c-118">42000</span></span></p></td>
<td><p><span data-ttu-id="c617c-119">20</span><span class="sxs-lookup"><span data-stu-id="c617c-119">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c617c-120">Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="c617c-120">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c617c-121">42020</span><span class="sxs-lookup"><span data-stu-id="c617c-121">42020</span></span></p></td>
<td><p><span data-ttu-id="c617c-122">20</span><span class="sxs-lookup"><span data-stu-id="c617c-122">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c617c-123">Um eine Quality of Service-audiorichtlinie für Windows 7 oder Windows 8 Computer zu erstellen, melden Sie sich zunächst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c617c-123">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="c617c-124">Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie im **Startmenü**auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**), und führen Sie dann das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="c617c-124">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="c617c-125">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c617c-125">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="c617c-126">Wenn sich beispielsweise alle Clientcomputer in einer Organisationseinheit mit dem Namen "Clients" befinden, sollte die neue Richtlinie in der Organisationseinheit "Client" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c617c-126">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="c617c-127">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen**.</span><span class="sxs-lookup"><span data-stu-id="c617c-127">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="c617c-128">Geben Sie im Dialogfeld **neues GPO** in das Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (beispielsweise **lync Audio**), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c617c-128">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="c617c-129">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c617c-129">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="c617c-130">Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor **Computerkonfiguration**, erweitern Sie **Richtlinien**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c617c-130">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="c617c-131">Geben Sie im Dialogfeld **richtlinienbasierter QoS** auf der Seite öffnen in das Feld **Name** einen Namen für die neue Richtlinie (z. b. **lync-Audio**) ein.</span><span class="sxs-lookup"><span data-stu-id="c617c-131">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="c617c-132">Klicken Sie auf \*\* 	DSCP-Wert angeben\*\* und legen Sie den Wert auf **46** fest.</span><span class="sxs-lookup"><span data-stu-id="c617c-132">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="c617c-133">Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c617c-133">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="c617c-134">Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem ausführbaren Namen** aus, und geben Sie den Namen **Lync.exe**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c617c-134">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="c617c-135">Mit dieser Einstellung wird die Richtlinie angewiesen, nur übereinstimmenden Datenverkehr vom lync-Client zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="c617c-135">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="c617c-p106">Vergewissern Sie sich auf der dritten Seite, dass **Beliebige Quell-IP-Adresse** und **Beliebige Ziel-IP-Adresse** aktiviert sind, und klicken Sie dann auf **Weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="c617c-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="c617c-138">Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus.</span><span class="sxs-lookup"><span data-stu-id="c617c-138">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="c617c-139">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c617c-139">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="c617c-140">Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer**an, **aus diesem Quell Port oder-Bereich aus**.</span><span class="sxs-lookup"><span data-stu-id="c617c-140">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="c617c-141">Geben Sie im dazugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="c617c-141">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="c617c-142">Wenn Sie beispielsweise Ports 50020 über Ports 50039 für den audiodatenverkehr reserviert haben, geben Sie den Portbereich unter Verwendung dieses Formats ein: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="c617c-142">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="c617c-143">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c617c-143">Click **Finish**.</span></span>

<span data-ttu-id="c617c-144">Nachdem Sie die QoS-Richtlinie für Audio erstellt haben, sollten Sie eine zweite Richtlinie für Video erstellen.</span><span class="sxs-lookup"><span data-stu-id="c617c-144">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="c617c-145">Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c617c-145">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="c617c-146">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Video**).</span><span class="sxs-lookup"><span data-stu-id="c617c-146">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="c617c-147">Legen Sie den DSCP-Wert auf **34** anstatt auf 46 fest.</span><span class="sxs-lookup"><span data-stu-id="c617c-147">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="c617c-148">(Wie bereits erwähnt, müssen Sie den DSCP-Wert 34 nicht verwenden; Sie müssen einfach einen anderen DSCP-Wert zuweisen als den für Audio verwendeten.)</span><span class="sxs-lookup"><span data-stu-id="c617c-148">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="c617c-149">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="c617c-149">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="c617c-150">Wenn Sie beispielsweise Ports 58000 bis 58019 für Video reserviert haben, legen Sie den Portbereich auf folgenden Wert fest: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="c617c-150">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="c617c-151">Wenn Sie sich entscheiden, eine Richtlinie zum Verwalten des Anwendungsfreigabe-Datenverkehrs zu erstellen, machen Sie diese Substitution:</span><span class="sxs-lookup"><span data-stu-id="c617c-151">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="c617c-152">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Anwendungsfreigabe**).</span><span class="sxs-lookup"><span data-stu-id="c617c-152">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="c617c-153">Legen Sie den DSCP-Wert auf **24** statt auf 46 fest.</span><span class="sxs-lookup"><span data-stu-id="c617c-153">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="c617c-154">(Auch hier muss dieser Wert nicht 24 sein; er muss sich einfach von den DSCP-Werten unterscheiden, die für Audio und Video verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="c617c-154">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="c617c-155">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="c617c-155">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="c617c-156">Wenn Sie beispielsweise Ports 42000 bis 42019 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf folgenden Wert fest: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="c617c-156">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="c617c-157">Für eine Datei Übertragungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="c617c-157">For a file transfer policy:</span></span>

  - <span data-ttu-id="c617c-158">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (beispielsweise **lync Server Dateiübertragungen**).</span><span class="sxs-lookup"><span data-stu-id="c617c-158">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="c617c-159">Legen Sie den DSCP-Wert auf **14**fest.</span><span class="sxs-lookup"><span data-stu-id="c617c-159">Set the DSCP value to **14**.</span></span> <span data-ttu-id="c617c-160">(Wieder muss dieser Wert nicht 14 sein; es muss sich einfach um einen eindeutigen DSCP-Code handeln.)</span><span class="sxs-lookup"><span data-stu-id="c617c-160">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="c617c-161">Verwenden Sie den zuvor konfigurierten Portbereich für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c617c-161">Use the previously-configured port range for application.</span></span> <span data-ttu-id="c617c-162">Wenn Sie beispielsweise Ports 42020 bis 42039 für die Anwendungsfreigabe reserviert haben, legen Sie den Portbereich auf folgenden Wert fest: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="c617c-162">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="c617c-163">Die neuen Richtlinien, die Sie erstellt haben, werden erst wirksam, wenn die Gruppenrichtlinie auf Ihren Clientcomputern aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c617c-163">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="c617c-164">Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="c617c-164">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="c617c-165">Dieser Befehl kann in jedem Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c617c-165">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="c617c-166">Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c617c-166">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="c617c-167">Beachten Sie, dass diese Richtlinien auf Ihre Clientcomputer ausgerichtet sein sollten.</span><span class="sxs-lookup"><span data-stu-id="c617c-167">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="c617c-168">Sie sollten nicht auf Server angewendet werden, auf denen lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c617c-168">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="c617c-169">Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="c617c-169">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="c617c-170">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c617c-170">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c617c-171">Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="c617c-171">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="c617c-172">Erweitern Sie im Registrierungs-Editor **HKEY \_ lokaler \_ Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="c617c-172">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c617c-p119">Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein und drücken dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c617c-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c617c-p120">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c617c-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c617c-177">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="c617c-177">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="c617c-178">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c617c-178">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="c617c-179">Schließen Sie den Registrierungs-Editor, und starten Sie dann Ihren Computer neu.</span><span class="sxs-lookup"><span data-stu-id="c617c-179">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="c617c-180">Konfigurieren der Dienstqualität auf Computern mit mehreren Netzwerkadaptern</span><span class="sxs-lookup"><span data-stu-id="c617c-180">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="c617c-181">Wenn Sie über einen Computer mit mehreren Netzwerkadaptern verfügen, treten möglicherweise gelegentlich Probleme auf, bei denen DSCP-Werte als $00 statt als konfigurierter Wert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c617c-181">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="c617c-182">Dies tritt in der Regel auf Computern auf, auf denen einer oder mehrere Netzwerkadapter nicht auf Ihre Active Directory Domäne zugreifen können (beispielsweise, wenn diese Adapter für ein privates Netzwerk verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="c617c-182">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="c617c-183">In solchen Fällen werden DSCP-Werte für die Adapter markiert, die auf die Domäne zugreifen können, Sie werden jedoch nicht für Adapter markiert, die nicht auf die Domäne zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c617c-183">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="c617c-184">Wenn Sie DSCP-Werte für alle Netzwerkadapter auf einem Computer, einschließlich Adaptern, die keinen Zugriff auf Ihre Domäne haben, markieren möchten, müssen Sie einen Wert für die Registrierung hinzufügen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c617c-184">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="c617c-185">Führen Sie dafür die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c617c-185">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="c617c-186">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c617c-186">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c617c-187">Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="c617c-187">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="c617c-188">Erweitern Sie im Registrierungs-Editor **HKEY \_ lokaler \_ Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="c617c-188">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c617c-189">Wenn kein Registrierungsschlüssel mit dem Namen **QoS** angezeigt wird, klicken Sie mit der rechten Maustaste auf **tcpip**, zeigen Sie auf **neu**, und klicken Sie dann auf **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="c617c-189">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c617c-190">Nachdem der neue Schlüssel erstellt wurde, geben Sie **QoS** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c617c-190">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c617c-p125">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="c617c-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c617c-193">Doppelklicken Sie auf **NLA nicht verwenden**.</span><span class="sxs-lookup"><span data-stu-id="c617c-193">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="c617c-194">Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c617c-194">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="c617c-195">Nachdem Sie den neuen Registrierungswert erstellt und konfiguriert haben, müssen Sie den Computer neu starten, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c617c-195">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

