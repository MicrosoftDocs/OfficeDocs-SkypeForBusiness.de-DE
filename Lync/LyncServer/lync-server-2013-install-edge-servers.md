---
title: 'Lync Server 2013: Installieren von Edge-Servern'
description: 'Lync Server 2013: Installieren von Edge-Servern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e699a7f41b0ee554bc85fb2d9a72a2d9a42870cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559581"
---
# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="8c252-103">Installieren von Edge-Servern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c252-103">Install Edge Servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c252-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8c252-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8c252-105">Sie installieren lync Server 2013 auf Edge-Servern mithilfe lync Server Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="8c252-105">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="8c252-106">Durch Ausführung des Bereitstellungs-Assistenten auf jedem Edgeserver können Sie die meisten Aufgaben ausführen, die zur Einrichtung des Edgeservers erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8c252-106">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="8c252-107">Um lync Server 2013 auf einem Edgeserver bereitstellen zu können, müssen Sie den Topologie-Generator bereits ausgeführt haben, um die Edgeserver Topologie zu definieren und zu veröffentlichen, und Sie auf Medien exportieren, die im Edgeserver verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8c252-107">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="8c252-108">Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und [Exportieren der lync Server 2013 Topologie und Kopieren dieser Daten in externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="8c252-108">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="8c252-109">Nachdem Sie die einzelnen Edgeserver mithilfe des Bereitstellungs-Assistenten installiert, installiert und die erforderlichen Zertifikate zugewiesen und die erforderlichen Dienste gestartet haben, können Sie das Setup mithilfe der Informationen unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) zum Aktivieren und Konfigurieren des Zugriffs durch externe Benutzer sowie der Informationen unter [Überprüfen der Edge-Bereitstellung in lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) abschließen, einschließlich der Server-und Clientkonnektivität.</span><span class="sxs-lookup"><span data-stu-id="8c252-109">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="8c252-110">So installieren Sie einen Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8c252-110">To install an Edge Server</span></span>

1.  <span data-ttu-id="8c252-111">Melden Sie sich als Mitglied der lokalen Administratorgruppe bei dem Computer an, auf dem Sie den Edgeserver installieren möchten, oder verwenden Sie ein Konto mit gleichwertigen Benutzerrechten und -berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="8c252-111">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="8c252-112">Stellen Sie sicher, dass die Topologie-Konfigurationsdatei, die Sie mithilfe des Topologie-Generators erstellt und anschließend auf externe Medien exportiert und kopiert haben, im Edgeserver verfügbar ist (beispielsweise Zugriff auf das USB-Laufwerk, auf dem Sie die topologiedatei kopiert haben, oder überprüfen Sie den Zugriff auf die Netzwerkfreigabe, in der Sie die Datei kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="8c252-112">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="8c252-113">Starten Sie den Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="8c252-113">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c252-p102">Wenn Sie in einer Meldung dazu aufgefordert werden, Microsoft Visual C++ Redistributable zu installieren, klicken Sie auf <STRONG>Ja</STRONG>. Im nächsten Dialogfeld können Sie den vorgegebenen <STRONG>Installationsspeicherort</STRONG> akzeptieren oder auf <STRONG>Durchsuchen</STRONG> klicken, um einen alternativen Speicherort anzugeben. Klicken Sie anschließend auf <STRONG>Installieren</STRONG>. Aktivieren Sie im nächsten Dialogfeld das Kontrollkästchen <STRONG>Ich stimme den Bedingungen des Lizenzvertrags zu</STRONG>, und klicken Sie auf <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c252-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="8c252-117">Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="8c252-117">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="8c252-118">Klicken Sie nach Abschluss der Bereitstellungsphase durch den Assistenten unter **Schritt 1. Lokalen Konfigurationsspeicher installieren** auf **Ausführen**, und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8c252-118">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="8c252-119">Klicken Sie im Dialogfeld **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** auf **Aus Datei importieren (für Edgeserver empfohlen)**, wechseln Sie zum Speicherort der exportierten Topologiekonfigurationsdatei, wählen Sie die ZIP-Datei aus, klicken Sie auf **Öffnen** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8c252-119">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="8c252-120">Der Bereitstellungs-Assistent liest die Konfigurationsinformationen aus der Konfigurationsdatei aus und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="8c252-120">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="8c252-121">Nachdem der Prozess **Befehle ausführen** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="8c252-121">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="8c252-122">Klicken Sie im Bereitstellungs-Assistenten auf **Schritt 2: lync Server Komponenten einrichten oder entfernen** , um die lync Server 2013-Edge-Komponenten zu installieren, die in der auf dem lokalen Computer gespeicherten XML-Konfigurationsdatei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8c252-122">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="8c252-123">Verwenden Sie nach Abschluss der Installation die Informationen unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md) , um die erforderlichen Zertifikate zu installieren und zuzuweisen, bevor Sie die Dienste starten.</span><span class="sxs-lookup"><span data-stu-id="8c252-123">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

