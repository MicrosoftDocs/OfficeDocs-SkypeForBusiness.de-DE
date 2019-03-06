---
title: Quality of Service in Microsoft Teams-Clients
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Quality of Service (QoS) für Microsoft-Teams, Clients zu implementieren.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1f80ede0432c3666a1974b1e0c8d7fa3dc2bbfc
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408267"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="b29e3-103">Set-QoS auf Windows-clients</span><span class="sxs-lookup"><span data-stu-id="b29e3-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="b29e3-104">Sie können Richtlinienbasierte QoS innerhalb der Gruppenrichtlinien verwenden, um den Quellportbereich für den vordefinierten DSCP-Wert in der Teams Client festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b29e3-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="b29e3-105">Die Portbereiche in der folgenden Tabelle angegeben sind, als Ausgangspunkt zum Erstellen einer Richtlinie für jeden Workload.</span><span class="sxs-lookup"><span data-stu-id="b29e3-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="b29e3-106">_Anfängliche Portbereiche empfohlen_</span><span class="sxs-lookup"><span data-stu-id="b29e3-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="b29e3-107">Media-Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="b29e3-107">Media traffic type</span></span>| <span data-ttu-id="b29e3-108">Client-Quellportbereich</span><span class="sxs-lookup"><span data-stu-id="b29e3-108">Client source port range</span></span> |<span data-ttu-id="b29e3-109">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b29e3-109">Protocol</span></span>|<span data-ttu-id="b29e3-110">DSCP-Wert</span><span class="sxs-lookup"><span data-stu-id="b29e3-110">DSCP value</span></span>|<span data-ttu-id="b29e3-111">DSCP-Klasse</span><span class="sxs-lookup"><span data-stu-id="b29e3-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="b29e3-112">Audio</span><span class="sxs-lookup"><span data-stu-id="b29e3-112">Audio</span></span>| <span data-ttu-id="b29e3-113">50.000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="b29e3-113">50,000–50,019</span></span>|<span data-ttu-id="b29e3-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b29e3-114">TCP/UDP</span></span>|<span data-ttu-id="b29e3-115">46</span><span class="sxs-lookup"><span data-stu-id="b29e3-115">46</span></span>|<span data-ttu-id="b29e3-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="b29e3-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="b29e3-117">Video</span><span class="sxs-lookup"><span data-stu-id="b29e3-117">Video</span></span>| <span data-ttu-id="b29e3-118">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="b29e3-118">50,020–50,039</span></span>|<span data-ttu-id="b29e3-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b29e3-119">TCP/UDP</span></span>|<span data-ttu-id="b29e3-120">34</span><span class="sxs-lookup"><span data-stu-id="b29e3-120">34</span></span>|<span data-ttu-id="b29e3-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="b29e3-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="b29e3-122">Anwendung/Bildschirmfreigabe</span><span class="sxs-lookup"><span data-stu-id="b29e3-122">Application/Screen Sharing</span></span>| <span data-ttu-id="b29e3-123">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="b29e3-123">50,040–50,059</span></span>|<span data-ttu-id="b29e3-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b29e3-124">TCP/UDP</span></span>|<span data-ttu-id="b29e3-125">18</span><span class="sxs-lookup"><span data-stu-id="b29e3-125">18</span></span>|<span data-ttu-id="b29e3-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="b29e3-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="b29e3-127">Konfigurieren Sie nach Möglichkeit, Richtlinienbasierte QoS-Einstellungen in ein Gruppenrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="b29e3-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="b29e3-128">Die folgenden Schritte sind sehr ähnlich [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für die Skype für Business Server-Clients](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), die über einige zusätzliche Details verfügt, die möglicherweise nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b29e3-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="b29e3-129">Zum Erstellen einer audio QoS-Richtlinie für Windows 10 Computer einstecken gehörenden zuerst melden Sie sich an einem Computer, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b29e3-129">To create a QoS audio policy for domian-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="b29e3-130">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf Start, zeigen Sie auf Verwaltung, und klicken Sie dann auf die Gruppenrichtlinien-Verwaltungskonsole), und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b29e3-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="b29e3-131">Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b29e3-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="b29e3-132">Beispielsweise sollte alle Client-Computer in einer Organisationseinheit mit dem Namen **Clients**befinden, die neue Richtlinie in der Organisationseinheit Client erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b29e3-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="b29e3-133">Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="b29e3-134">Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** Geben Sie im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="b29e3-135">Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="b29e3-136">In den Gruppenrichtlinienverwaltungs-Editor, erweitern Sie **Computerkonfiguration**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="b29e3-137">Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="b29e3-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="b29e3-138">Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="b29e3-139">Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="b29e3-140">Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem Namen ausführbare** und geben Sie den Namen **Teams.exe**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="b29e3-141">Diese Einstellung weist die Richtlinie nur übereinstimmenden Datenverkehr vom Client Teams priorisieren.</span><span class="sxs-lookup"><span data-stu-id="b29e3-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="b29e3-142">Stellen Sie auf der dritten Seite sicher, dass **alle Quell-IP-Adresse** und **einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="b29e3-143">Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.</span><span class="sxs-lookup"><span data-stu-id="b29e3-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="b29e3-144">Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** .</span><span class="sxs-lookup"><span data-stu-id="b29e3-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="b29e3-145">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die am häufigsten verwendeten zwei Netzwerkprotokollen.</span><span class="sxs-lookup"><span data-stu-id="b29e3-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="b29e3-146">Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer** **aus dieser Quellport oder der Bereich**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="b29e3-147">Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b29e3-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="b29e3-148">Angenommen, wenn Sie Ports 50000 über Ports 50019 für audio-Datenverkehr reserviert ist, geben Sie den Portbereich, der mit diesem Format: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="b29e3-149">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b29e3-149">Click **Finish**.</span></span>

11. <span data-ttu-id="b29e3-150">Wiederholen Sie die Schritte 5 bis 10, um Richtlinien für Video und Anwendung/Desktop freigeben, ersetzen die entsprechenden Werte in Schritt 6 und 10 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b29e3-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="b29e3-151">Die neuen Richtlinien, die von die Ihnen erstellten werden nicht erst wirksam, Gruppenrichtlinien auf den Clientcomputern aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b29e3-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="b29e3-152">Obwohl Gruppenrichtlinien allein in regelmäßigen Abständen aktualisiert wurde, können Sie eine sofortige Aktualisierung erzwingen, durch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b29e3-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="b29e3-153">Öffnen Sie auf jedem Computer, für die Sie die Gruppenrichtlinie aktualisieren möchten eine Befehlskonsole.</span><span class="sxs-lookup"><span data-stu-id="b29e3-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="b29e3-154">Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="b29e3-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="b29e3-155">Geben Sie an der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b29e3-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="b29e3-156">Überprüfen Sie die DSCP-Auswahlmöglichkeiten in das Gruppenrichtlinienobjekt</span><span class="sxs-lookup"><span data-stu-id="b29e3-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="b29e3-157">Führen Sie die folgenden Schritte aus, um zu überprüfen, dass die Werte aus dem Gruppenrichtlinienobjekt festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="b29e3-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="b29e3-158">Öffnen Sie eine Befehlskonsole.</span><span class="sxs-lookup"><span data-stu-id="b29e3-158">Open a command console.</span></span> <span data-ttu-id="b29e3-159">Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="b29e3-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="b29e3-160">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b29e3-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="b29e3-161">Dies einen Bericht generiert und in eine Textdatei mit dem Namen gp.txt zu senden.</span><span class="sxs-lookup"><span data-stu-id="b29e3-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="b29e3-162">Alternativ können Sie den folgenden Befehl aus, um die gleichen Daten in einem besser lesbar HTML-Bericht mit dem Namen gp.html zu erzeugen eingeben:</span><span class="sxs-lookup"><span data-stu-id="b29e3-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="b29e3-163">![Screenshot des Konsolenfenster des Befehls Gpresult.] (media/Qos-in-Teams-Image3.png "Screenshot des Konsolenfenster des Befehls Gpresult.")</span><span class="sxs-lookup"><span data-stu-id="b29e3-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="b29e3-164">Suchen Sie in der generierten Datei nach der Überschrift **Gruppenrichtlinienobjekte angewendet** , und stellen Sie sicher, dass die Namen der zuvor erstellten Gruppenrichtlinienobjekte in der Liste der Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b29e3-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="b29e3-165">Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu:</span><span class="sxs-lookup"><span data-stu-id="b29e3-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="b29e3-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="b29e3-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="b29e3-167">Überprüfen Sie die Werte für die in Tabelle 4 aufgeführten Registrierungseinträge.</span><span class="sxs-lookup"><span data-stu-id="b29e3-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="b29e3-168">_In Tabelle 4. Werte für Windows-Registrierungseinträge für QoS_</span><span class="sxs-lookup"><span data-stu-id="b29e3-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="b29e3-169">Name</span><span class="sxs-lookup"><span data-stu-id="b29e3-169">Name</span></span>          |  <span data-ttu-id="b29e3-170">Typ</span><span class="sxs-lookup"><span data-stu-id="b29e3-170">Type</span></span>  |    <span data-ttu-id="b29e3-171">Daten</span><span class="sxs-lookup"><span data-stu-id="b29e3-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="b29e3-172">Application Name</span><span class="sxs-lookup"><span data-stu-id="b29e3-172">Application Name</span></span>    | <span data-ttu-id="b29e3-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-173">REG_SZ</span></span> |  <span data-ttu-id="b29e3-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="b29e3-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="b29e3-175">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="b29e3-175">DSCP Value</span></span>       | <span data-ttu-id="b29e3-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-176">REG_SZ</span></span> |     <span data-ttu-id="b29e3-177">46</span><span class="sxs-lookup"><span data-stu-id="b29e3-177">46</span></span>      |
   |        <span data-ttu-id="b29e3-178">Local IP</span><span class="sxs-lookup"><span data-stu-id="b29e3-178">Local IP</span></span>        | <span data-ttu-id="b29e3-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="b29e3-180">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="b29e3-180">Local IP Prefix Length</span></span> | <span data-ttu-id="b29e3-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="b29e3-182">Local Port</span><span class="sxs-lookup"><span data-stu-id="b29e3-182">Local Port</span></span>       | <span data-ttu-id="b29e3-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-183">REG_SZ</span></span> | <span data-ttu-id="b29e3-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="b29e3-184">50000-50019</span></span> |
   |        <span data-ttu-id="b29e3-185">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b29e3-185">Protocol</span></span>        | <span data-ttu-id="b29e3-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="b29e3-187">Remote IP</span><span class="sxs-lookup"><span data-stu-id="b29e3-187">Remote IP</span></span>        | <span data-ttu-id="b29e3-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="b29e3-189">Remote-IP-Präfix</span><span class="sxs-lookup"><span data-stu-id="b29e3-189">Remote IP Prefix</span></span>    | <span data-ttu-id="b29e3-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="b29e3-191">Remote Port</span><span class="sxs-lookup"><span data-stu-id="b29e3-191">Remote Port</span></span>       | <span data-ttu-id="b29e3-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="b29e3-193">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="b29e3-193">Throttle Rate</span></span>      | <span data-ttu-id="b29e3-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b29e3-194">REG_SZ</span></span> |     <span data-ttu-id="b29e3-195">-1</span><span class="sxs-lookup"><span data-stu-id="b29e3-195">-1</span></span>      |

5. <span data-ttu-id="b29e3-196">Stellen Sie sicher, dass der Wert für den Anwendungsnamen-Eintrag für den Client korrekt ist, den Sie verwenden, und stellen Sie sicher, dass sowohl die DSCP-Wert und der lokalen Port Einträge die Einstellungen in das Gruppenrichtlinienobjekt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b29e3-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
