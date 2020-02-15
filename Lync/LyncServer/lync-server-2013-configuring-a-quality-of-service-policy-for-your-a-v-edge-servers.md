---
title: Konfigurieren einer Dienst Qualitätsrichtlinie für Ihre a/V-Edgeserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e55947fa80e2772bbc53b47f5c6f906761f1bb3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="da764-102">Konfigurieren einer Dienst Qualitätsrichtlinie für Ihre a/V-Edgeserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da764-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da764-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="da764-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="da764-p101">Neben den QoS-Richtlinien für Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen Sie auch Audio- und Videorichtlinien für die interne Seite Ihrer A/V-Edgeserver erstellen. Die auf Ihren Edgeservern verwendeten Richtlinien unterscheiden sich jedoch von den auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern verwendeten Richtlinien. Für die Konferenz-, Anwendungs- und Vermittlungsserver haben Sie einen Quellportbereich angegeben; bei Edgeservern müssen Sie einen Zielportbereich angeben. Daher können Sie die QoS-Richtlinien für Konferenz-, Anwendungs- und Vermittlungsserver nicht auf Ihre Edgeserver anwenden, diese Richtlinien funktionieren dort nicht. Stattdessen müssen Sie neue Richtlinien erstellen und diese ausschließlich auf Ihre Edgeserver anwenden.</span><span class="sxs-lookup"><span data-stu-id="da764-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="da764-p102">Das folgende Verfahren beschreibt die Vorgehensweise beim Erstellen von Active Directory-Gruppenrichtlinienobjekten, die zum Verwalten der der Dienstqualität (Quality of Service, QoS) auf Edgeservern verwendet werden kann. Möglicherweise handelt es sich bei Ihren Edgeservern um Einzelserver ohne Active Directory-Konten. In diesem Fall können Sie die lokale Gruppenrichtlinie statt der Active Directory-Gruppenrichtlinie verwenden, mit dem Unterschied, dass Sie diese lokalen Richtlinien mit dem Editor für lokale Gruppenrichtlinien erstellen und auf jedem Edgeserver denselben Richtliniensatz einzeln erstellen müssen. Gehen Sie wie folgt vor, um auf einem Edgeserver den Editor für lokale Gruppenrichtlinien zu starten:</span><span class="sxs-lookup"><span data-stu-id="da764-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="da764-113">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da764-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="da764-114">Geben Sie im Dialogfeld **Ausführen** den Befehl **gpedit.msc** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="da764-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="da764-p103">Wenn Sie Active Directory-basierte Richtlinien erstellen, sollten Sie sich an einem Computer anmelden, auf dem die Gruppenrichtlinienverwaltung installiert ist (klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, klicken Sie auf **Gruppenrichtlinienverwaltung**), und führen Sie dann folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="da764-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="da764-p104">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll. Beispiel: Wenn sich all Ihre Lync Server-Computer in einer Organisationseinheit mit dem Namen "Lync Server" befinden, sollte die neue Richtlinie in der Organisationseinheit "Lync Server" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="da764-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="da764-119">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt hier erstellen und verknüpfen**.</span><span class="sxs-lookup"><span data-stu-id="da764-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="da764-120">Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein (z. B. **Lync Server Audio**), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da764-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="da764-121">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="da764-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="da764-122">Ab diesem Schritt sind die Vorgehensweisen beim Erstellen einer Active Directory-Richtlinie und einer lokalen Richtlinie identisch:</span><span class="sxs-lookup"><span data-stu-id="da764-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="da764-123">Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor oder im Editor für lokale Gruppenrichtlinien **Computerkonfiguration**, **Richtlinien** und **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **Richtlinienbasierter QoS**, und klicken Sie dann auf **Neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="da764-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="da764-p105">Geben Sie im Dialogfeld **Richtlinienbasierter QoS** auf der ersten Seite im Feld **Name** einen Namen für die neue Richtlinie ein (z. B. **Lync Server Audio**). Klicken Sie auf \*\* 	DSCP-Wert angeben\*\* und legen Sie den Wert auf **46** fest. Lassen Sie das Kontrollkästchen **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="da764-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="da764-p106">Vergewissern Sie sich auf der nächsten Seite, dass **Anwendungstyp** aktiviert ist, und klicken Sie dann auf **Weiter**. Durch diese Einstellung wird das Netzwerk angewiesen, nach allen Paketen mit der DSCP-Markierung 46 zu suchen, anstatt nur nach von einer bestimmten Anwendung erstellten Paketen.</span><span class="sxs-lookup"><span data-stu-id="da764-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="da764-p107">Vergewissern Sie sich auf der dritten Seite, dass **Beliebige Quell-IP-Adresse** und **Beliebige Ziel-IP-Adresse** aktiviert sind, und klicken Sie dann auf **Weiter**. Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, welcher Computer (IP-Adresse) diese Pakete gesendet hat und welcher Computer (IP-Adresse) sie empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="da764-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="da764-131">Wählen Sie auf der vierten Seite in der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet wird** die Option **TCP und UDP** aus.</span><span class="sxs-lookup"><span data-stu-id="da764-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="da764-132">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten von lync Server und seinen Clientanwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da764-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="da764-p109">Wählen Sie unter der Überschrift **Geben Sie die Zielportnummer an** die Option **An diese Zielportnummer bzw. diesen -bereich**. Geben Sie im dazugehörigen Textfeld den für Audioübertragungen reservierten Portbereich ein. Wenn Sie z. B. die Ports 49152 bis 57500 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **49152:57500**. Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="da764-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="da764-p110">Nachdem Sie die QoS-Richtlinie für Audiodatenverkehr erstellt haben, sollten Sie eine zweite Richtlinie für Videodatenverkehr erstellen. Zum Erstellen einer Richtlinie für Video wenden Sie dasselbe Grundverfahren wie beim Erstellen der Audiorichtlinie an und ändern dabei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da764-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="da764-139">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Video**).</span><span class="sxs-lookup"><span data-stu-id="da764-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="da764-p111">Legen Sie den DSCP-Wert auf **34** statt "46" fest. (Sie müssen nicht unbedingt den DSCP-Wert 34 verwenden, der DSCP-Wert für Video muss sich lediglich von dem für Audio verwendeten Wert unterscheiden.)</span><span class="sxs-lookup"><span data-stu-id="da764-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="da764-p112">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie z. B. die Ports 57501 bis 65535 für Video reserviert haben, legen Sie den Portbereich folgendermaßen fest: **57501:65535**. Auch dies sollte als Zielportbereich konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="da764-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="da764-146">Wenn Sie eine Richtlinie für das Verwalten des Datenverkehrs bei der Anwendungsfreigabe erstellen möchten, müssen Sie eine dritte Richtlinie mit folgenden Änderungen erstellen:</span><span class="sxs-lookup"><span data-stu-id="da764-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="da764-147">Verwenden Sie einen anderen (und eindeutigen) Richtliniennamen (z. B. **Lync Server Anwendungsfreigabe**).</span><span class="sxs-lookup"><span data-stu-id="da764-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="da764-p113">Legen Sie den DSCP-Wert auf **24** statt "46" fest. (Auch hier muss nicht unbedingt der DSCP-Wert 24 verwendet werden, der DSCP-Wert für Video muss sich lediglich von den für Audio und Video verwendeten Werten unterscheiden.)</span><span class="sxs-lookup"><span data-stu-id="da764-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="da764-p114">Verwenden Sie den zuvor konfigurierten Portbereich für Videodatenverkehr. Wenn Sie z. B. die Ports 40803 bis 49151 für Anwendungsfreigabe reserviert haben, legen Sie den Portbereich folgendermaßen fest: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="da764-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="da764-p115">Die neu erstellten Richtlinien werden erst wirksam, wenn auf Ihren Edgeservern die Gruppenrichtlinien aktualisiert wurden. Gruppenrichtlinien werden zwar regelmäßig automatisch aktualisiert, Sie können jedoch eine sofortige Aktualisierung erzwingen, indem Sie den folgenden Befehl auf jedem Computer ausführen, auf dem die Gruppenrichtlinien aktualisiert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="da764-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="da764-155">Dieser Befehl kann in der lync Server oder in einem beliebigen Befehlsfenster ausgeführt werden, das unter Administratoranmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="da764-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="da764-156">Zum Ausführen eines Befehlsfensters unter der Angabe von Administratoranmeldeinformationen klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da764-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="da764-157">Möglicherweise müssen Sie den Edgeserver auch nach der Ausführung von "Gpudate.exe" neu starten.</span><span class="sxs-lookup"><span data-stu-id="da764-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="da764-158">Um sicherzustellen, dass Netzwerkpakete mit dem richtigen DSCP-Wert markiert sind, sollten Sie auch auf jedem Computer einen neuen Registrierungseintrag erstellen, indem Sie folgendes Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="da764-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="da764-159">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da764-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="da764-160">Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="da764-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="da764-161">Erweitern Sie im Registrierungs-Editor **HKEY\_lokaler\_Computer**, erweitern Sie **System**, erweitern Sie **CurrentControlSet**, erweitern Sie **Dienste**, und erweitern Sie dann **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="da764-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="da764-p117">Klicken Sie mit der rechten Maustaste auf **Tcpip** zeigen Sie auf **Neu**, und klicken Sie dann auf **Schlüssel**. Nachdem der neue Registrierungsschlüssel erstellt wurde, geben Sie **QoS** ein und drücken dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="da764-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="da764-p118">Klicken Sie mit der rechten Maustaste auf **QoS**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Zeichenfolgenwert**. Nachdem der neue Registrierungswert erstellt wurde, geben Sie **NLA nicht verwenden**, und drücken dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="da764-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="da764-p119">Doppelklicken Sie auf **NLA nicht verwenden**. Geben Sie im Dialogfeld **Zeichenfolge bearbeiten** im Feld **Wertdaten** den Wert **1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da764-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="da764-168">Schließen Sie den Registrierungs-Editor, und starten Sie dann Ihren Computer neu.</span><span class="sxs-lookup"><span data-stu-id="da764-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

