---
title: 'Lync Server 2013: Installieren der Dateien für Vermittlungsserver'
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
ms.openlocfilehash: 39d2072b32f386e182ea51f6bf88e8d67028a0d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="6702e-102">Installieren der Dateien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6702e-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6702e-103">_**Letztes Änderungsstand des Themas:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="6702e-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="6702e-104">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie am Server mindestens als lokaler Administrator und als Domänenbenutzer angemeldet sein, der mindestens Mitglied der Gruppe RTCUniversalReadOnlyAdmins ist.</span><span class="sxs-lookup"><span data-stu-id="6702e-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="6702e-105">Führen Sie die Schritte in diesem Thema aus, um lync Server 2013-Bereitstellungs-Assistenten auszuführen, um die Dateien für Vermittlungsserver auf einem Computer zu installieren, den Sie einem Vermittlungsserver Pool hinzugefügt haben, als Sie den Pool mithilfe des Topologie-Generators definiert und veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="6702e-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="6702e-106">Bei der Installation von Dateien Vermittlungsserver müssen Sie auch das für jeden Computer in einem Vermittlungsserver-Pool erforderliche Zertifikat installieren und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6702e-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="6702e-107">Wenn Sie auf dieser Website bereits Vermittlungsserver in den Front-End-Pools oder Standard Edition-Server bereitgestellt haben, können Sie dieses Thema überspringen und stattdessen mit der [Konfiguration von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6702e-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6702e-108">In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen Vermittlungsserver Pool definiert und veröffentlicht haben, wie unter <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">define a Vermittlungsserver in Topology Builder in lync Server 2013</A> beschrieben, und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation und dass Sie sichergestellt haben, dass die Computer im Vermittlungsserver Pool die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</A> beschriebenen Voraussetzungen erfüllen <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md"> Voice in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6702e-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="6702e-109">So installieren Sie die Dateien für einen eigenständigen Vermittlungsserver Pool</span><span class="sxs-lookup"><span data-stu-id="6702e-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="6702e-110">Klicken Sie auf dem Installationsmedium mit der \<rechten Maustaste\>auf Installationsmedien**\\Setup\\amd64\\Setup. exe**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6702e-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="6702e-111">Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6702e-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="6702e-112">Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich akzeptiere**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6702e-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="6702e-113">(Erforderlich, um den Vorgang fortzusetzen.)</span><span class="sxs-lookup"><span data-stu-id="6702e-113">(Required to continue.)</span></span>

4.  <span data-ttu-id="6702e-114">Klicken Sie auf der Seite **lync Server 2010-Bereitstellungs-Assistenten** auf **lync Server System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="6702e-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="6702e-115">Klicken Sie neben **Schritt 1: lokalen Konfigurationsspeicher installieren**auf **Ausführen**, und folgen Sie dann den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="6702e-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="6702e-116">Übernehmen Sie auf der Seite **lokales Replikat von zentraler Verwaltungsspeicher konfigurieren** den Standard **Abruf direkt aus der zentraler Verwaltungsspeicher**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6702e-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="6702e-117">Wenn der Aufgabenstatus als **abgeschlossen**angezeigt wird, klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6702e-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="6702e-118">Klicken Sie neben **Schritt 2: lync Server Komponenten einrichten oder entfernen**auf **Ausführen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6702e-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="6702e-119">Wenn der Aufgabenstatus als **abgeschlossen**angezeigt wird, klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6702e-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="6702e-120">Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6702e-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="6702e-121">Folgen Sie den Anweisungen auf dem Bildschirm, und akzeptieren Sie die Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6702e-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="6702e-122">Für den Vermittlungsserver ist ein Zertifikat erforderlich, und Sie führen **Schritt 3** zweimal aus: einmal, um das erforderliche Zertifikat auszustellen und es erneut zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6702e-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="6702e-123">Wenn das Zertifikat ausgestellt und ordnungsgemäß zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten**auf **Ausführen**, und folgen Sie dann den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="6702e-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="6702e-124">Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu, und melden Sie sich als Mitglied der Admins-Gruppe am Server an.</span><span class="sxs-lookup"><span data-stu-id="6702e-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="6702e-125">Überprüfen Sie auf dem Computer, auf dem Sie lync Server-Systemsteuerung durchführen, auf der Seite **Topologie** von lync Server-Systemsteuerung, ob der Dienststatus der Vermittlungsserver als grünes Häkchen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6702e-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="6702e-126">Wenn stattdessen ein rotes X angezeigt wird, wählen Sie das Vermittlungsserver aus.</span><span class="sxs-lookup"><span data-stu-id="6702e-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="6702e-127">Klicken Sie im Menü **Aktion** auf **alle Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="6702e-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="6702e-128">Wenn Sie dem Vermittlungsserver Pool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im Vermittlungsserver-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="6702e-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="6702e-129">Wenn Sie keine Dateien für Vermittlungsserver für andere Computer installieren müssen, befolgen Sie die Verfahren unter Konfigurieren von [Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) , um Einstellungen für die trunkverbindung zwischen diesem Vermittlungsserver Pool (oder allen Vermittlungsservern an einem Standort) und seinem Peer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6702e-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6702e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6702e-130">See Also</span></span>


[<span data-ttu-id="6702e-131">Zertifikatanforderungen für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6702e-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

