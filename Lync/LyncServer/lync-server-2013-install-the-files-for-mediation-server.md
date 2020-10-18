---
title: 'Lync Server 2013: Installieren der Dateien für Vermittlungsserver'
description: 'Lync Server 2013: Installieren Sie die Dateien für Vermittlungsserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574071"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="e5352-103">Installieren der Dateien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5352-103">Install the files for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5352-104">_**Letztes Änderungsstand des Themas:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="e5352-104">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="e5352-105">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie am Server mindestens als lokaler Administrator und als Domänenbenutzer angemeldet sein, der mindestens Mitglied der Gruppe RTCUniversalReadOnlyAdmins ist.</span><span class="sxs-lookup"><span data-stu-id="e5352-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="e5352-106">Führen Sie die Schritte in diesem Thema aus, um lync Server 2013-Bereitstellungs-Assistenten auszuführen, um die Dateien für Vermittlungsserver auf einem Computer zu installieren, den Sie einem Vermittlungsserver Pool hinzugefügt haben, als Sie den Pool mithilfe des Topologie-Generators definiert und veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="e5352-106">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="e5352-107">Bei der Installation von Dateien Vermittlungsserver müssen Sie auch das für jeden Computer in einem Vermittlungsserver-Pool erforderliche Zertifikat installieren und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e5352-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="e5352-108">Wenn Sie auf dieser Website bereits Vermittlungsserver in den Front-End-Pools oder Standard Edition-Server bereitgestellt haben, können Sie dieses Thema überspringen und stattdessen mit der [Konfiguration von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e5352-108">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5352-109">In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen Vermittlungsserver-Pool definiert und veröffentlicht haben, wie unter <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">define a Vermittlungsserver in Topology Builder in lync Server 2013</A> beschrieben, und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation und dass Sie <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">sicher</A>gestellt haben, dass die Computer im Vermittlungsserver Pool die Voraussetzungen erfüllen, die unter " <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP</A> in lync Server 2013"</span><span class="sxs-lookup"><span data-stu-id="e5352-109">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="e5352-110">So installieren Sie die Dateien für einen eigenständigen Vermittlungsserver Pool</span><span class="sxs-lookup"><span data-stu-id="e5352-110">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="e5352-111">Klicken Sie auf dem Installationsmedium mit der rechten Maustaste auf \<installation media\> \*\* \\ Setup \\ amd64 \\Setup.exe\*\*, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e5352-111">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="e5352-112">Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5352-112">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="e5352-113">Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich akzeptiere**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5352-113">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="e5352-114">(Erforderlich, um den Vorgang fortzusetzen.)</span><span class="sxs-lookup"><span data-stu-id="e5352-114">(Required to continue.)</span></span>

4.  <span data-ttu-id="e5352-115">Klicken Sie auf der Seite **lync Server 2010-Bereitstellungs-Assistenten** auf **lync Server System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="e5352-115">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="e5352-116">Klicken Sie neben **Schritt 1: lokalen Konfigurationsspeicher installieren**auf **Ausführen**, und folgen Sie dann den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="e5352-116">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="e5352-117">Übernehmen Sie auf der Seite **lokales Replikat von zentraler Verwaltungsspeicher konfigurieren** den Standard **Abruf direkt aus der zentraler Verwaltungsspeicher**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5352-117">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="e5352-118">Wenn der Aufgabenstatus als **abgeschlossen**angezeigt wird, klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e5352-118">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="e5352-119">Klicken Sie neben **Schritt 2: lync Server Komponenten einrichten oder entfernen**auf **Ausführen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5352-119">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="e5352-120">Wenn der Aufgabenstatus als **abgeschlossen**angezeigt wird, klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e5352-120">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="e5352-121">Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e5352-121">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="e5352-122">Folgen Sie den Anweisungen auf dem Bildschirm, und akzeptieren Sie die Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e5352-122">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="e5352-123">Für den Vermittlungsserver ist ein Zertifikat erforderlich, und Sie führen **Schritt 3** zweimal aus: einmal, um das erforderliche Zertifikat auszustellen und es erneut zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e5352-123">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="e5352-124">Wenn das Zertifikat ausgestellt und ordnungsgemäß zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten**auf **Ausführen**, und folgen Sie dann den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="e5352-124">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="e5352-125">Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu, und melden Sie sich als Mitglied der Admins-Gruppe am Server an.</span><span class="sxs-lookup"><span data-stu-id="e5352-125">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="e5352-126">Überprüfen Sie auf dem Computer, auf dem Sie lync Server-Systemsteuerung durchführen, auf der Seite **Topologie** von lync Server-Systemsteuerung, ob der Dienststatus der Vermittlungsserver als grünes Häkchen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e5352-126">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="e5352-127">Wenn stattdessen ein rotes X angezeigt wird, wählen Sie das Vermittlungsserver aus.</span><span class="sxs-lookup"><span data-stu-id="e5352-127">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="e5352-128">Klicken Sie im Menü **Aktion** auf **alle Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="e5352-128">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="e5352-129">Wenn Sie dem Vermittlungsserver Pool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im Vermittlungsserver-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="e5352-129">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="e5352-130">Wenn Sie keine Dateien für Vermittlungsserver für andere Computer installieren müssen, befolgen Sie die Verfahren unter Konfigurieren von [Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) , um Einstellungen für die trunkverbindung zwischen diesem Vermittlungsserver Pool (oder allen Vermittlungsservern an einem Standort) und seinem Peer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e5352-130">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5352-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5352-131">See Also</span></span>


[<span data-ttu-id="e5352-132">Zertifikatanforderungen für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5352-132">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

