---
title: 'Lync Server 2013: Definieren einer IP-Adresse für das SIP/CSTA-Gateway'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a88aa2209617a93b0feebf7c1cc6d8cccd0cf7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516382"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="dabc6-102">Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dabc6-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dabc6-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dabc6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dabc6-104">Wenn lync Server eine Verbindung mit dem SIP/CSTA-Gateway herstellen, das Sie für die Remoteanrufsteuerung mithilfe einer TCP-Verbindung (Transmission Control Protocol) bereitgestellt haben, müssen Sie die IP-Adresse des Gateways im Topologie-Generator definieren.</span><span class="sxs-lookup"><span data-stu-id="dabc6-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="dabc6-105">Dieser Schritt ist für Gateways, die TLS-Verbindungen (Transport Layer Security) unterstützen, nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dabc6-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="dabc6-106">Für jedes Gateway, das TLS-Verbindungen unterstützt, können Sie dieses Verfahren überspringen und die Bereitstellung der Remoteanrufsteuerung fortsetzen, indem Sie die Schritte unter [Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="dabc6-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="dabc6-107">So definieren Sie die IP-Adresse des SIP/CSTA-Gateways mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="dabc6-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="dabc6-108">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="dabc6-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="dabc6-109">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="dabc6-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="dabc6-110">Wählen Sie die Option zum Herunterladen einer vorhandenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="dabc6-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="dabc6-111">Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver**.</span><span class="sxs-lookup"><span data-stu-id="dabc6-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="dabc6-112">Klicken Sie mit der rechten Maustaste auf den vertrauenswürdigen Anwendungspool, den Sie erstellt haben, wie unter [Konfigurieren eines Eintrags für vertrauenswürdige Anwendungen für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)beschrieben, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dabc6-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="dabc6-113">Deaktivieren Sie das Kontrollkästchen **Replikation von Konfigurationsdaten in diesen Pool aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="dabc6-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="dabc6-p102">Klicken Sie auf **Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Die Standardeinstellung ist **Alle konfigurierten IP-Adressen verwenden**.</span><span class="sxs-lookup"><span data-stu-id="dabc6-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="dabc6-116">Geben Sie in das Textfeld **Primäre IP-Adresse** die IP-Adresse des SIP/CSTA-Gateways ein.</span><span class="sxs-lookup"><span data-stu-id="dabc6-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="dabc6-117">Klicken Sie zum Aktualisieren der Topologie im zentralen Verwaltungsspeicher in der Konsolenstruktur auf **Lync Server 2010**, und klicken Sie dann im Bereich **Aktionen** auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="dabc6-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dabc6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dabc6-118">See Also</span></span>


[<span data-ttu-id="dabc6-119">Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dabc6-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="dabc6-120">Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dabc6-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

