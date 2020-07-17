---
title: Implementieren von Quality of Service (QoS) in Microsoft Teams-Clients
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Erfahren Sie, wie QoS (Quality of Service) zur Optimierung des Netzwerkverkehrs für den Microsoft Teams-Desktop Client verwendet wird.
ms.custom: seo-marvel-mar2020
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80b9257abbbb873b30367f9d430e9a8d155cda09
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085531"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="c795c-103">Implementieren von Quality of Service (QoS) in Microsoft Teams-Clients</span><span class="sxs-lookup"><span data-stu-id="c795c-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="c795c-104">Sie können die richtlinienbasierte QoS (Quality of Service) in Gruppenrichtlinien verwenden, um den Quellportbereich für den vordefinierten DSCP-Wert im Teams-Client festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c795c-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="c795c-105">Die in der folgenden Tabelle angegebenen Portbereiche stellen einen Ausgangspunkt zum Erstellen einer Richtlinie für jede Arbeitsauslastung dar.</span><span class="sxs-lookup"><span data-stu-id="c795c-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="c795c-106">*Tabelle 1 Empfohlene anfängliche Portbereiche*</span><span class="sxs-lookup"><span data-stu-id="c795c-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="c795c-107">Typ des Mediendatenverkehrs</span><span class="sxs-lookup"><span data-stu-id="c795c-107">Media traffic type</span></span>| <span data-ttu-id="c795c-108">Client-Quellportbereich </span><span class="sxs-lookup"><span data-stu-id="c795c-108">Client source port range</span></span> |<span data-ttu-id="c795c-109">Protokoll</span><span class="sxs-lookup"><span data-stu-id="c795c-109">Protocol</span></span>|<span data-ttu-id="c795c-110">DSCP-Wert</span><span class="sxs-lookup"><span data-stu-id="c795c-110">DSCP value</span></span>|<span data-ttu-id="c795c-111">DSCP-Klasse</span><span class="sxs-lookup"><span data-stu-id="c795c-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="c795c-112">Audio</span><span class="sxs-lookup"><span data-stu-id="c795c-112">Audio</span></span>| <span data-ttu-id="c795c-113">50.000–50.019</span><span class="sxs-lookup"><span data-stu-id="c795c-113">50,000–50,019</span></span>|<span data-ttu-id="c795c-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c795c-114">TCP/UDP</span></span>|<span data-ttu-id="c795c-115">46</span><span class="sxs-lookup"><span data-stu-id="c795c-115">46</span></span>|<span data-ttu-id="c795c-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="c795c-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="c795c-117">Video</span><span class="sxs-lookup"><span data-stu-id="c795c-117">Video</span></span>| <span data-ttu-id="c795c-118">50.020–50.039</span><span class="sxs-lookup"><span data-stu-id="c795c-118">50,020–50,039</span></span>|<span data-ttu-id="c795c-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c795c-119">TCP/UDP</span></span>|<span data-ttu-id="c795c-120">34</span><span class="sxs-lookup"><span data-stu-id="c795c-120">34</span></span>|<span data-ttu-id="c795c-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="c795c-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="c795c-122">Anwendung/Bildschirmfreigabe</span><span class="sxs-lookup"><span data-stu-id="c795c-122">Application/Screen Sharing</span></span>| <span data-ttu-id="c795c-123">50.040–50.059</span><span class="sxs-lookup"><span data-stu-id="c795c-123">50,040–50,059</span></span>|<span data-ttu-id="c795c-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c795c-124">TCP/UDP</span></span>|<span data-ttu-id="c795c-125">18</span><span class="sxs-lookup"><span data-stu-id="c795c-125">18</span></span>|<span data-ttu-id="c795c-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="c795c-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="c795c-127">Konfigurieren Sie, wenn möglich, richtlinienbasierte QoS-Einstellungen in einem Gruppenrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="c795c-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="c795c-128">Die folgenden Schritte ähneln dem [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), die einige zusätzliche Details enthält, die möglicherweise nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c795c-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="c795c-129">Wenn Sie eine QoS-audiorichtlinie für mit der Domäne verbundene Windows 10-Computer erstellen möchten, melden Sie sich zuerst bei einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c795c-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="c795c-130">Öffnen Sie die Gruppenrichtlinienverwaltung (Klicken Sie auf Start, zeigen Sie auf Verwaltung, und klicken Sie dann auf Gruppenrichtlinienverwaltung), und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c795c-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="c795c-131">Suchen Sie in der Gruppenrichtlinienverwaltung nach dem Container, in dem die neue Richtlinie erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c795c-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="c795c-132">Wenn sich beispielsweise alle Ihre Clientcomputer in einer Organisationseinheit mit dem Namen " **Clients**" befinden, sollte die neue Richtlinie in der Organisationseinheit "Clients" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c795c-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="c795c-133">Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Gruppenrichtlinienobjekt in dieser Domäne erstellen, und verknüpfen Sie es hier**.</span><span class="sxs-lookup"><span data-stu-id="c795c-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="c795c-134">Geben Sie im Dialogfeld **neues GPO** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c795c-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="c795c-135">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c795c-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="c795c-136">Erweitern Sie im Gruppenrichtlinien-Verwaltungs-Editor **Computer Konfiguration**, erweitern Sie **Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c795c-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="c795c-137">Geben Sie im Dialogfeld **richtlinienbasierte QoS** auf der Seite öffnen im Feld **Name** einen Namen für die neue Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="c795c-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="c795c-138">Wählen Sie **DSCP-Wert angeben** aus, und legen Sie den Wert auf **46**fest.</span><span class="sxs-lookup"><span data-stu-id="c795c-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="c795c-139">Geben Sie die **ausgehende Drosselungs Rate** nicht ausgewählt ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c795c-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="c795c-140">Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem ausführbaren Namen** aus, geben Sie den Namen **Teams.exe**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c795c-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="c795c-141">Mit dieser Einstellung wird die Richtlinie angewiesen, nur den übereinstimmenden Datenverkehr vom Team-Client zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="c795c-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="c795c-142">Stellen Sie auf der dritten Seite sicher, dass sowohl **eine Quell-** als auch **eine beliebige Ziel-IP-Adresse** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="c795c-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="c795c-143">Durch diese beiden Einstellungen wird sichergestellt, dass Pakete unabhängig davon verwaltet werden, auf welchem Computer (IP-Adresse) die Pakete gesendet werden und auf welchem Computer (IP-Adresse) die Pakete empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="c795c-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="c795c-144">Wählen Sie auf Seite 4 **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll aus, auf das diese QoS-Richtlinie angewendet werden soll** .</span><span class="sxs-lookup"><span data-stu-id="c795c-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="c795c-145">TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden am häufigsten verwendeten Netzwerkprotokolle.</span><span class="sxs-lookup"><span data-stu-id="c795c-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="c795c-146">Wählen Sie unter der Überschrift **die Quellportnummer**aus, und wählen Sie **aus diesem Quell Port oder-Bereich aus**.</span><span class="sxs-lookup"><span data-stu-id="c795c-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="c795c-147">Geben Sie im Feld Begleittext den Portbereich ein, der für Audioübertragungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="c795c-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="c795c-148">Wenn Sie beispielsweise Ports 50000 über Ports 50019 für den Audioverkehr reserviert haben, geben Sie den Portbereich mit folgendem Format ein: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="c795c-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="c795c-149">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c795c-149">Click **Finish**.</span></span>

1. <span data-ttu-id="c795c-150">Wiederholen Sie die Schritte 5-10, um Richtlinien für die Video-und Anwendungs-und Desktop Freigabe zu erstellen und die entsprechenden Werte in den Schritten 6 und 10 zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c795c-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="c795c-151">Die neu erstellten Richtlinien werden erst wirksam, nachdem die Gruppenrichtlinien auf Ihren Clientcomputern aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c795c-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="c795c-152">Obwohl Gruppenrichtlinien regelmäßig für sich selbst aktualisiert werden, können Sie eine sofortige Aktualisierung erzwingen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c795c-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="c795c-153">Öffnen Sie auf jedem Computer, für den Sie die Gruppenrichtlinie aktualisieren möchten, eine Eingabeaufforderung als Administrator (*als Administrator ausführen*).</span><span class="sxs-lookup"><span data-stu-id="c795c-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="c795c-154">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c795c-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="c795c-155">Überprüfen von DSCP-Markierungen im Gruppenrichtlinienobjekt</span><span class="sxs-lookup"><span data-stu-id="c795c-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="c795c-156">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Werte aus dem Gruppenrichtlinienobjekt festgesetzt wurden:</span><span class="sxs-lookup"><span data-stu-id="c795c-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="c795c-157">Öffnen Sie eine Eingabeaufforderung als Administrator (*als Administrator ausführen*).</span><span class="sxs-lookup"><span data-stu-id="c795c-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="c795c-158">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c795c-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="c795c-159">Dadurch wird ein Bericht über angewendete GPOs generiert und an eine Textdatei mit dem Namen *gp.txt*gesendet.</span><span class="sxs-lookup"><span data-stu-id="c795c-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="c795c-160">Geben Sie den folgenden Befehl ein, um einen besser lesbaren HTML-Bericht mit dem Namen *gp.html*zu finden:</span><span class="sxs-lookup"><span data-stu-id="c795c-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="c795c-161">Suchen Sie in der generierten Datei nach der Überschrift **angewendete Gruppenrichtlinienobjekte** , und überprüfen Sie, ob die Namen der zuvor erstellten Gruppenrichtlinienobjekte in der Liste der angewendeten Richtlinien aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="c795c-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="c795c-162">Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu</span><span class="sxs-lookup"><span data-stu-id="c795c-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="c795c-163">HKEY \_ - \_ Software Richtlinien für lokale Computer \\ \\ \\ Microsoft \\ Windows- \\ QoS</span><span class="sxs-lookup"><span data-stu-id="c795c-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="c795c-164">Überprüfen Sie die Werte für die Registrierungseinträge, die in Tabelle 2 aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="c795c-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="c795c-165">*Tabelle 2. Werte für Windows-Registrierungseinträge für QoS*</span><span class="sxs-lookup"><span data-stu-id="c795c-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="c795c-166">Name</span><span class="sxs-lookup"><span data-stu-id="c795c-166">Name</span></span>          |  <span data-ttu-id="c795c-167">Typ</span><span class="sxs-lookup"><span data-stu-id="c795c-167">Type</span></span>  |    <span data-ttu-id="c795c-168">Daten</span><span class="sxs-lookup"><span data-stu-id="c795c-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="c795c-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="c795c-169">Application Name</span></span>    | <span data-ttu-id="c795c-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-170">REG_SZ</span></span> |  <span data-ttu-id="c795c-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="c795c-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="c795c-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="c795c-172">DSCP Value</span></span>       | <span data-ttu-id="c795c-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-173">REG_SZ</span></span> |     <span data-ttu-id="c795c-174">46</span><span class="sxs-lookup"><span data-stu-id="c795c-174">46</span></span>      |
   |        <span data-ttu-id="c795c-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="c795c-175">Local IP</span></span>        | <span data-ttu-id="c795c-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="c795c-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="c795c-177">Local IP Prefix Length</span></span> | <span data-ttu-id="c795c-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="c795c-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="c795c-179">Local Port</span></span>       | <span data-ttu-id="c795c-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-180">REG_SZ</span></span> | <span data-ttu-id="c795c-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="c795c-181">50000-50019</span></span> |
   |        <span data-ttu-id="c795c-182">Protokoll</span><span class="sxs-lookup"><span data-stu-id="c795c-182">Protocol</span></span>        | <span data-ttu-id="c795c-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="c795c-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="c795c-184">Remote IP</span></span>        | <span data-ttu-id="c795c-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="c795c-186">Remote-IP-Präfix</span><span class="sxs-lookup"><span data-stu-id="c795c-186">Remote IP Prefix</span></span>    | <span data-ttu-id="c795c-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="c795c-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="c795c-188">Remote Port</span></span>       | <span data-ttu-id="c795c-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="c795c-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="c795c-190">Throttle Rate</span></span>      | <span data-ttu-id="c795c-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c795c-191">REG_SZ</span></span> |     <span data-ttu-id="c795c-192">-1</span><span class="sxs-lookup"><span data-stu-id="c795c-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="c795c-193">Überprüfen Sie, ob der Wert für den Anwendungsnamen Eintrag für den verwendeten Client richtig ist, und überprüfen Sie, ob der DSCP-Wert und die lokalen Port Einträge die Einstellungen im Gruppenrichtlinienobjekt widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="c795c-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c795c-194">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c795c-194">Related topics</span></span>

[<span data-ttu-id="c795c-195">Implementieren von Quality of Service (QoS) in Teams</span><span class="sxs-lookup"><span data-stu-id="c795c-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)