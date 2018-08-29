---
title: Bearbeiten der Topologie in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite Globale Topologie einen Doppelklick auf den Standort, den Sie bearbeiten möchten.
ms.openlocfilehash: 65b23bf764f802da0f535dcc86cfb5170481161b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263816"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="f6578-104">Bearbeiten der Topologie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6578-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="f6578-p102">Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite **Globale Topologie** einen Doppelklick auf den Standort, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="f6578-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="f6578-107">Das Planungstool zeigt die Standorttopologie für den ausgewählten Standort.</span><span class="sxs-lookup"><span data-stu-id="f6578-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="f6578-108">Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f6578-108">At the bottom of the site page are four tabs:</span></span>

![Planungstool – Standorttopologie](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="f6578-110">Standorttopologie - die aktuell angezeigte Seite mit einer optischen Übersicht der empfohlenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="f6578-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="f6578-111">Edge-Netzwerkdiagramm - Edge-Netzwerkdiagramm Seite ist, in dem der Designer die meisten Aufgaben im Planungstool wird.</span><span class="sxs-lookup"><span data-stu-id="f6578-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="f6578-112">Das Diagramm zeigt die Netzwerkkonfiguration für einen empfohlenen Skype für Business Server 2015 Topologie, mit bearbeitbaren Einträge für IP-Adressen und FQDNs für Server, Pool, und sowohl Hardware und Domain Name System (DNS) Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="f6578-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="f6578-113">Edgeverwaltungsbericht – der Edgeverwaltungsbericht insgesamt vier Berichte enthält:</span><span class="sxs-lookup"><span data-stu-id="f6578-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Edgeverwaltungsbericht (Seite)](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="f6578-115">Zusammenfassungsbericht - Bericht für allgemeine Einstellungen für die Edge-Netzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6578-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="f6578-116">Wenn Sie auf der Seite **Edge-Netzwerkdiagramm** die TCP-IP- und FQDN-Werte der Topologie in die der tatsächlichen Bereitstellung ändern, werden diese Adressen und Namen hier dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f6578-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="f6578-117">Andernfalls wird hier der Standardtext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6578-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="f6578-118">Zertifikatbericht – der zertifikatbericht führt den Antragstellernamen und alternative Antragstellernamen für Zertifikate, die für die Topologie erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f6578-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="f6578-119">Firewallbericht - firewallbericht werden die notwendigen Informationen zum Konfigurieren von Firewalls Umkreisnetzwerk in der Infrastruktur aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f6578-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="f6578-120">Diese umfassen die IP-Adressen (entweder die Standardwerte oder die bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.</span><span class="sxs-lookup"><span data-stu-id="f6578-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="f6578-121">DNS-Bericht - DNS-Bericht listet relevanten Informationen für die DNS-Einträge, die Sie erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="f6578-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="f6578-122">Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.</span><span class="sxs-lookup"><span data-stu-id="f6578-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="f6578-123">Siteübersicht - der Siteübersicht liefert eine Übersicht über die Elemente, die Sie durch die anfänglichen Interview Fragen beantworten oder die Werte in den **Entwurf von Standorten**ausfüllen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="f6578-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="f6578-124">Es werden auch Kapazitätsinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6578-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6578-125">Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="f6578-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="f6578-126">Bearbeiten des Netzwerkkonfigurationsdiagramms</span><span class="sxs-lookup"><span data-stu-id="f6578-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="f6578-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="f6578-127"></span></span>

<span data-ttu-id="f6578-128">Die meisten Aufgaben, die ein Designer in der Skype für Business Server 2015 Planungstool umfasst das definieren die Einträge für die IP-Adressen und den vollqualifizierten Domänennamen (FQDNs) für die Einträge im Netzplandiagramm.</span><span class="sxs-lookup"><span data-stu-id="f6578-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="f6578-129">In den Berichten und andere Informationen in das Planungstool übertragenen Informationen, die auf dieser Seite eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f6578-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Planungstool – Netzwerk (Diagramm)](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="f6578-131">Das Planungstool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.</span><span class="sxs-lookup"><span data-stu-id="f6578-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="f6578-132">So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein</span><span class="sxs-lookup"><span data-stu-id="f6578-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="f6578-p110">Wählen Sie einen Abschnitt des Netzwerks aus, den Sie zuerst bearbeiten möchten. Machen Sie z. B. einen Doppelklick auf den Text **access1.contoso.net**. Geben Sie im nun geöffneten Dialogfeld den tatsächlichen FQDN für den Server „access1.contoso.net“ ein und ersetzen Sie die IP-Adresse 131.107.155.3 durch die tatsächliche IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="f6578-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="f6578-136">Klicken Sie auf **OK**, um die Einträge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f6578-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="f6578-137">Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.</span><span class="sxs-lookup"><span data-stu-id="f6578-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="f6578-p111">Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f6578-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="f6578-p112">Machen Sie einen Doppelklick auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.</span><span class="sxs-lookup"><span data-stu-id="f6578-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="f6578-142">Beispielsweise lautet der Startwert für den ersten Server "fe0101.contoso.net", und die IP-Adresse ist auf "192.168.21.222" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f6578-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="f6578-143">Geben Sie in FQDN des Front-End-Servers den Wert **fe0.contoso.com** und in **IP-Adresse des Front-End-Servers** die Adresse 192.168.21.131 ein und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6578-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="f6578-144">Die Funktion zur automatischen inkrementellen Erhöhung aktualisiert alle Server im Pool von "fe01" bis "fe06" und alle IP-Adressen von 192.168.21.131 bis 136.</span><span class="sxs-lookup"><span data-stu-id="f6578-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="f6578-145">Nachdem Sie die Bearbeitung abgeschlossen haben, speichern Sie die Topologie, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f6578-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="f6578-146">Um das Planungstool Design zu speichern, klicken Sie auf **Datei**und dann auf **Topologie speichern** oder **Topologie speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="f6578-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="f6578-147">Falls ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f6578-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6578-148">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f6578-148">See also</span></span>
<span data-ttu-id="f6578-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="f6578-149"></span></span>

[<span data-ttu-id="f6578-150">Bearbeiten des Entwurfs</span><span class="sxs-lookup"><span data-stu-id="f6578-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)