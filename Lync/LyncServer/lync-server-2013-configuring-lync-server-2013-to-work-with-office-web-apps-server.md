---
title: Konfigurieren lync Server 2013 für die Verwendung mit Office-webapps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a5cd13b139cb2544e1d89971a8480d1e1fb296
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="7f332-102">Konfigurieren lync Server 2013 für die Verwendung mit Office-webapps Server</span><span class="sxs-lookup"><span data-stu-id="7f332-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f332-103">_**Letztes Änderungsstand des Themas:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="7f332-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="7f332-104">Bevor Sie lync Server 2013 für die Verwendung von Office-webapps Server konfigurieren können, müssen Office-webapps-Server bereitgestellt und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7f332-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="7f332-105">Ausführliche Informationen über die Installation und Konfiguration eines einzelnen Office Web Apps-Servers oder einer Office Web Apps-Serverfarm für Hochverfügbarkeitszwecke finden Sie im **Handbuch zur Bereitstellung von Office Web Apps-Server und Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="7f332-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="7f332-106">Nachdem Sie den Office-webapps-Server erfolgreich installiert und die Webfarm ordnungsgemäß konfiguriert haben, müssen Sie lync Server für die Kommunikation mit dem neuen Server konfigurieren. Fügen Sie dazu die Office-webapps Server Discovery-URL zu ihrer lync Server-Topologie hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f332-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="7f332-107">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7f332-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="7f332-108">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="7f332-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7f332-109">Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus einer vorhandenen Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f332-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="7f332-p103">Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) in **Dateiname** ein, und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.</span><span class="sxs-lookup"><span data-stu-id="7f332-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="7f332-112">Erweitern Sie im Topologie-Generator **lync Server 2013**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen eines Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f332-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="7f332-113">Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen**, und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).</span><span class="sxs-lookup"><span data-stu-id="7f332-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="7f332-114">Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.</span><span class="sxs-lookup"><span data-stu-id="7f332-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="7f332-115">Wenn der Office Web Apps-Server lokal und in der gleichen Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (d. "Perimeter/Internet")** sollte nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="7f332-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="7f332-116">Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.</span><span class="sxs-lookup"><span data-stu-id="7f332-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="7f332-p104">Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK**, und klicken Sie dann auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Web Apps-Such-URL wird dann unter den Zuordnungen des Pools aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f332-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="7f332-119">Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f332-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="7f332-p105">Nachdem Sie die Such-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7f332-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="7f332-122">Klicken Sie auf **Aktion**, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="7f332-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="7f332-123">Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7f332-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="7f332-124">Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7f332-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="7f332-125">Schließen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="7f332-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

