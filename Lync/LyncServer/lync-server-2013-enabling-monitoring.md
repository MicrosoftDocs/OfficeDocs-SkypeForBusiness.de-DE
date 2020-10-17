---
title: 'Lync Server 2013: Aktivieren der Überwachung'
description: 'Lync Server 2013: Aktivieren der Überwachung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8995042bdc9b121dc5253940104bb167567ddcc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558481"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="4591e-103">Aktivieren der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4591e-103">Enabling monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4591e-104">_**Letztes Änderungsstand des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="4591e-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="4591e-105">Obwohl die Unified Data Collection-Agents auf jedem Front-End-Server automatisch installiert und aktiviert werden, bedeutet das nicht, dass Sie automatisch mit der Erfassung von Überwachungsdaten beginnen, sobald Sie Microsoft lync Server 2013 fertig gestellt haben.</span><span class="sxs-lookup"><span data-stu-id="4591e-105">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4591e-106">Stattdessen müssen Sie zwei Schritte ausführen: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuweisen und die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder von QoE (Quality of Experience) auf globaler und/oder Standortebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-106">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="4591e-107">Eine Schritt-für-Schritt-Anleitung zum Zuordnen von Front-End-Servern und Front-End-Pools zu einer Überwachungsdatenbank finden Sie im Bereitstellungshandbuch im Thema [Zuordnen eines überwachungsspeichers mit einem Front-End-Pool in lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) .</span><span class="sxs-lookup"><span data-stu-id="4591e-107">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="4591e-108">Nach dem Festlegen dieser Zuweisungen und dem Veröffentlichen der neuen Lync Server-Topologie können Sie trotzdem noch keine Überwachungsdaten erfassen.</span><span class="sxs-lookup"><span data-stu-id="4591e-108">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="4591e-109">Das liegt daran, dass die KDS-und QoE-Datensammlung standardmäßig deaktiviert ist, wenn Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-109">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="4591e-110">Um mit der Datensammlung beginnen zu können, müssen Sie die KDS-und/oder QoE-Überwachung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-110">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="4591e-111">(Beachten Sie, dass Sie nicht sowohl die KDS-als auch die QoE-Überwachung aktivieren müssen, wenn Sie es vorziehen, können Sie eine Überwachungsart aktivieren, während Sie den anderen Typ deaktiviert lassen.) Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die KDS-Überwachung auf globaler Ebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4591e-111">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="4591e-112">Alternativ können Sie die KDS-Überwachung in der lync Server 2013-Systemsteuerung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-112">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4591e-113">Führen Sie in der lync Server-Systemsteuerung das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="4591e-113">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="4591e-114">Klicken Sie auf **Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="4591e-114">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="4591e-115">Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.</span><span class="sxs-lookup"><span data-stu-id="4591e-115">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="4591e-116">Wählen Sie im Bereich **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die Option **KDS-Überwachung aktivieren** aus, und klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4591e-116">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="4591e-117">Um die QoE-Überwachung auf globaler Ebene zu aktivieren, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="4591e-117">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="4591e-118">Wenn es Ihnen lieber ist, können Sie die QoE-Überwachung auch in der lync Server-Systemsteuerung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-118">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="4591e-119">Führen Sie in der Systemsteuerung die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4591e-119">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="4591e-120">Klicken Sie auf **Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="4591e-120">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="4591e-121">Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.</span><span class="sxs-lookup"><span data-stu-id="4591e-121">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="4591e-122">Wählen Sie im Bereich **Quality of Experience (QoE)-Einstellung bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus, und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4591e-122">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="4591e-123">Wie bereits erwähnt, ermöglichen die obigen Beispiele die Überwachung auf globaler Ebene; Das bedeutet, dass Sie die KDS-und QoE-Überwachung in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-123">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="4591e-124">Alternativ können Sie separate KDS-und QoE-Konfigurationseinstellungen auf Standortebene erstellen und dann die Überwachung für jeden Standort selektiv aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-124">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="4591e-125">Beispielsweise können Sie die KDS-Überwachung für Ihren Standort in Redmond aktivieren und dennoch die KDS-Überwachung für Ihren Standort in Dublin deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4591e-125">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="4591e-126">Weitere Informationen zum Verwalten der Überwachungs Konfigurationseinstellungen finden Sie im Bereitstellungshandbuch unter Konfigurieren der Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen [und der Qualität der Benutzerfreundlichkeit in lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4591e-126">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

