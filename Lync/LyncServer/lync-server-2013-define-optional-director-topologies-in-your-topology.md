---
title: 'Lync Server 2013: Definieren von optionalen Director-Topologien in Ihrer Topologie'
description: 'Lync Server 2013: definieren Sie die optionalen Director-Topologien in Ihrer Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542652"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="24825-103">Definieren von optionalen Director-Topologien in Ihrer Topologie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24825-103">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24825-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="24825-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="24825-105">Lync Server 2013 Directors können Einzelinstanzen Server sein oder als Pool mit Lastenausgleich von mehreren Directors installiert werden, um höhere Verfügbarkeit und Kapazität zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="24825-105">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="24825-106">Sowohl Hardwarelastenausgleich als auch Domain Name System (DNS) Lastenausgleich werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24825-106">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="24825-107">In diesem Thema wird erläutert, wie Sie den DNS-Lastenausgleich für Director-Pools konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24825-107">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="24825-108">Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen **RTCUniversalServerAdmins** und **Domänen-Admins** angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="24825-108">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="24825-109">Außerdem können Sie die erforderlichen Berechtigungen für das Hinzufügen von Serverrollen delegieren.</span><span class="sxs-lookup"><span data-stu-id="24825-109">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="24825-110">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Standard Edition-Server-oder Enterprise Edition-Server-Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="24825-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="24825-111">Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe **RTCUniversalServerAdmins** sein.</span><span class="sxs-lookup"><span data-stu-id="24825-111">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="24825-112">In diesem Thema werden die Schritte zum Definieren und Veröffentlichen der Topologie für die beiden Director-Topologien beschrieben:</span><span class="sxs-lookup"><span data-stu-id="24825-112">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="24825-113">So definieren Sie den Director (Einzelinstanz)</span><span class="sxs-lookup"><span data-stu-id="24825-113">To define the Director (single instance)</span></span>

  - <span data-ttu-id="24825-114">So definieren Sie den Director (Pool mit mehreren Directors)</span><span class="sxs-lookup"><span data-stu-id="24825-114">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="24825-115">So definieren Sie den Director (Einzelinstanz)</span><span class="sxs-lookup"><span data-stu-id="24825-115">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="24825-116">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="24825-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="24825-117">Klicken Sie auf der Willkommenseite auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="24825-117">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="24825-118">Geben Sie im Dialogfeld **Topologie speichern unter** den Namen und den Speicherort für die lokale Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24825-118">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="24825-119">Erweitern Sie den Standort, an dem der Director hinzugefügt werden soll, klicken Sie mit der rechten Maustaste auf **Director-Pools** und anschließend auf **Neuer Director-Pool**.</span><span class="sxs-lookup"><span data-stu-id="24825-119">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="24825-120">Führen Sie im Dialogfeld **FQDN für Director-Pool definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24825-120">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="24825-121">Geben Sie in **Pool-FQDN** den FQDN für den Director-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="24825-121">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="24825-122">Klicken Sie auf **Pool mit einem Computer** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-122">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="24825-123">Führen Sie im Dialogfeld **Dateifreigabe definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24825-123">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="24825-124">Zum Verwenden einer vorhandenen Dateifreigabe klicken Sie auf **Zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-124">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="24825-125">Zum Erstellen einer neuen Dateifreigabe klicken Sie auf **Neue Dateifreigabe definieren**, geben Sie in **Dateiserver-FQDN** den FQDN für das Verzeichnis der Dateifreigabe ein, geben Sie in **Dateifreigabe** den Namen der Freigabe ein, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-125">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24825-126">Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor der Veröffentlichung der Topologie vorhanden sein oder erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="24825-126">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="24825-127">Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, Sie können dem Director also die Dateifreigabe jedes Pools in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="24825-127">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="24825-128">Geben Sie im Dialogfeld **Webdienste-URL angeben** in **Externe Basis-URL** den FQDN für die Directors an, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="24825-128">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24825-129">Der Name muss von Internet-DNS-Servern aufgelöst werden können und auf die öffentliche IP-Adresse des Reverseproxys verweisen, der an diese URL gesendete HTTP/HTTPS-Anforderungen überwacht und diese an das virtuelle Verzeichnis der externen Webdienste auf diesem Director weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="24825-129">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="24825-130">Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="24825-130">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="24825-131">Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="24825-131">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="24825-132">Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="24825-132">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="24825-133">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="24825-133">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="24825-134">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="24825-134">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="24825-135">So definieren Sie den Director (Pool mit mehreren Directors)</span><span class="sxs-lookup"><span data-stu-id="24825-135">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="24825-136">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="24825-136">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="24825-137">Klicken Sie auf der Willkommenseite auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="24825-137">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="24825-138">Geben Sie im Dialogfeld **Topologie speichern unter** den Namen und den Speicherort für die lokale Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="24825-138">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="24825-139">Erweitern Sie den Standort, an dem der Director hinzugefügt werden soll, klicken Sie mit der rechten Maustaste auf **Director-Pools** und anschließend auf **Neuer Director-Pool**.</span><span class="sxs-lookup"><span data-stu-id="24825-139">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="24825-140">Führen Sie im Dialogfeld **FQDN für Director-Pool definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24825-140">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="24825-141">Geben Sie in **Pool-FQDN** den FQDN für den Director-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="24825-141">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="24825-142">Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-142">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="24825-143">Führen Sie im Dialogfeld **Computer in diesem Pool definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24825-143">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="24825-144">Geben Sie den Computer-FQDN des ersten Mitglieds im Pool an, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="24825-144">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="24825-p104">Wiederholen Sie diesen Schritt für jeden Computer, den Sie hinzufügen möchten, und klicken Sie zum Schluss auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="24825-147">Führen Sie im Dialogfeld **Dateifreigabe definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24825-147">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="24825-148">Zum Verwenden einer vorhandenen Dateifreigabe klicken Sie auf **Zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-148">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="24825-149">Zum Erstellen einer neuen Dateifreigabe klicken Sie auf **Neue Dateifreigabe definieren**, geben Sie in **Dateiserver-FQDN** den FQDN für das Verzeichnis der Dateifreigabe ein, geben Sie in **Dateifreigabe** den Namen der Freigabe ein, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="24825-149">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24825-150">Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor der Veröffentlichung der Topologie vorhanden sein oder erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="24825-150">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="24825-151">Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, Sie können dem Director also die Dateifreigabe jedes Pools in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="24825-151">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="24825-152">Geben Sie im Dialogfeld **Webdienste-URL angeben** in **Externe Basis-URL** den FQDN für die Directors an, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="24825-152">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24825-153">Der Name muss von Internet-DNS-Servern aufgelöst werden können und auf die öffentliche IP-Adresse des Reverseproxys verweisen, der an diese URL gesendete HTTP/HTTPS-Anforderungen überwacht und diese an das virtuelle Verzeichnis der externen Webdienste in diesem Director-Pool weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="24825-153">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="24825-154">Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="24825-154">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="24825-155">Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="24825-155">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="24825-156">Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="24825-156">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="24825-157">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="24825-157">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="24825-158">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="24825-158">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

