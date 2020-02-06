---
title: Bearbeiten der Topologie in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite Globale Topologie einen Doppelklick auf den Standort, den Sie bearbeiten möchten.
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816444"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="a536a-104">Bearbeiten der Topologie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a536a-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="a536a-p102">Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite **Globale Topologie** einen Doppelklick auf den Standort, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a536a-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="a536a-107">Das Planungs Tool zeigt die Standorttopologie für die ausgewählte Website an.</span><span class="sxs-lookup"><span data-stu-id="a536a-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="a536a-108">Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a536a-108">At the bottom of the site page are four tabs:</span></span>

![Standorttopologie des Planungstools](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="a536a-110">Website Topologie – die aktuell angezeigte Seite mit einer visuellen Übersicht über die Topologie, wie empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a536a-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="a536a-111">Edge-Netzwerkdiagramm – auf der Seite "Edge-Netzwerkdiagramm" werden die meisten Arbeiten des Designers im Planungs Tool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a536a-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="a536a-112">Das Diagramm zeigt die Netzwerkkonfiguration einer empfohlenen Skype for Business Server 2015-Topologie mit bearbeitbaren Einträgen für IP-Adressen und FQDNs für Server, Pool sowie Hardware-und DNS-Lastenausgleichssysteme (Domain Name System) an.</span><span class="sxs-lookup"><span data-stu-id="a536a-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="a536a-113">Edge-Administrator Bericht – der Bericht Edge-Administrator enthält insgesamt vier Berichte:</span><span class="sxs-lookup"><span data-stu-id="a536a-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Seite "Edge-Administrator Bericht"](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="a536a-115">Zusammenfassungsbericht – ein allgemeiner Bericht über die Einstellungen für die Edge-Netzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a536a-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="a536a-116">Wenn Sie auf der Seite **Edge-Netzwerkdiagramm** die TCP-IP- und FQDN-Werte der Topologie in die der tatsächlichen Bereitstellung ändern, werden diese Adressen und Namen hier dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a536a-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="a536a-117">Andernfalls wird hier der Standardtext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a536a-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="a536a-118">Zertifikat Bericht – im Zertifikat Bericht werden der Antragstellername und die alternativen Namen für die Zertifikate aufgelistet, die für die Topologie erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a536a-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="a536a-119">Firewallbericht – der firewallbericht enthält Informationen, die für die Konfiguration von Umkreisfirewalls in der Infrastruktur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a536a-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="a536a-120">Diese umfassen die IP-Adressen (entweder die Standardwerte oder die bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.</span><span class="sxs-lookup"><span data-stu-id="a536a-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="a536a-121">DNS-Bericht – im DNS-Bericht sind relevante Informationen zu den DNS-Einträgen aufgeführt, die Sie erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="a536a-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="a536a-122">Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.</span><span class="sxs-lookup"><span data-stu-id="a536a-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="a536a-123">Website Zusammenfassung: die Website Zusammenfassung zeigt eine Übersicht über die von Ihnen vorgenommenen Auswahlen, indem Sie entweder die ersten Fragen des Interviews beantwortet oder die Werte in **Design Websites**ausgefüllt haben.</span><span class="sxs-lookup"><span data-stu-id="a536a-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="a536a-124">Es werden auch Kapazitätsinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a536a-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a536a-125">Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="a536a-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="a536a-126">Bearbeiten des Netzwerkkonfigurationsdiagramms</span><span class="sxs-lookup"><span data-stu-id="a536a-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="a536a-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="a536a-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="a536a-128">Der größte Teil der Arbeit, die ein Designer im Planungs Tool von Skype for Business Server 2015 durchführt, besteht darin, die Einträge für die IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für die Einträge im Netzplandiagramm zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a536a-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="a536a-129">Die Informationen, die auf dieser Seite eingegeben werden, werden in die Berichte und andere Informationen übernommen, die im Planungs Tool enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a536a-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Planungs Tool-Netzwerkdiagramm](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="a536a-131">Das Planungs Tool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.</span><span class="sxs-lookup"><span data-stu-id="a536a-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="a536a-132">So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein</span><span class="sxs-lookup"><span data-stu-id="a536a-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="a536a-p110">Wählen Sie einen Abschnitt des Netzwerks aus, den Sie zuerst bearbeiten möchten. Machen Sie z. B. einen Doppelklick auf den Text **access1.contoso.net**. Geben Sie im nun geöffneten Dialogfeld den tatsächlichen FQDN für den Server „access1.contoso.net“ ein und ersetzen Sie die IP-Adresse 131.107.155.3 durch die tatsächliche IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="a536a-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="a536a-136">Klicken Sie auf **OK**, um die Einträge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a536a-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="a536a-137">Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.</span><span class="sxs-lookup"><span data-stu-id="a536a-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="a536a-p111">Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a536a-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="a536a-p112">Machen Sie einen Doppelklick auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.</span><span class="sxs-lookup"><span data-stu-id="a536a-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="a536a-142">Beispielsweise lautet der Startwert für den ersten Server "fe0101.contoso.net", und die IP-Adresse ist auf "192.168.21.222" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a536a-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="a536a-143">Geben Sie in FQDN des Front-End-Servers den Wert **fe0.contoso.com** und in **IP-Adresse des Front-End-Servers** die Adresse 192.168.21.131 ein und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a536a-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="a536a-144">Die Funktion zur automatischen inkrementellen Erhöhung aktualisiert alle Server im Pool von "fe01" bis "fe06" und alle IP-Adressen von 192.168.21.131 bis 136.</span><span class="sxs-lookup"><span data-stu-id="a536a-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="a536a-145">Nachdem Sie die Bearbeitung abgeschlossen haben, speichern Sie die Topologie, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a536a-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="a536a-146">Wenn Sie das Planungs Tool Design speichern möchten, klicken Sie auf **Datei**, und klicken Sie dann auf **Topologie speichern** oder **Topologie speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="a536a-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="a536a-147">Falls ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a536a-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a536a-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a536a-148">See also</span></span>
<span data-ttu-id="a536a-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="a536a-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="a536a-150">Editing the Design</span><span class="sxs-lookup"><span data-stu-id="a536a-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
