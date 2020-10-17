---
title: 'Lync Server 2013: Einrichten der Verbindung mit öffentlichen Instant Messaging-Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2c3cfec8a685251a3a1627392d6d4eb9691748
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521832"
---
# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="f8428-102">Einrichten der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8428-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8428-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f8428-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f8428-p101">Wenn Ihre Organisation Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL unterstützen möchte, können Sie das Zertifikat nicht mit dem Lync Server-Bereitstellungs-Assistenten anfordern. Führen Sie stattdessen die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f8428-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="f8428-106">So richten Sie die Verbindung mit öffentlichen Instant Messaging-Diensten ein</span><span class="sxs-lookup"><span data-stu-id="f8428-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="f8428-p102">Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern Sie "Edgepools", und klicken Sie mit der rechten Maustaste auf "Edgeserver" oder "Edgeserver-Pool". Klicken Sie auf "Eigenschaften bearbeiten".</span><span class="sxs-lookup"><span data-stu-id="f8428-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="f8428-p103">Klicken Sie in "Eigenschaften bearbeiten" unter "Allgemein" auf "Partnerverbund für diesen Edgepool aktivieren" (Port 5061). Klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="f8428-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="f8428-p104">Klicken Sie auf "Aktion", wählen Sie "Topologie", und wählen Sie "Veröffentlichen" aus. Wenn Sie unter "Topologie veröffentlichen" dazu aufgefordert werden, klicken Sie auf "Weiter". Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf "Fertig stellen".</span><span class="sxs-lookup"><span data-stu-id="f8428-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="f8428-p105">Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".</span><span class="sxs-lookup"><span data-stu-id="f8428-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="f8428-p106">Klicken Sie unter "Lync Server-Komponenten einrichten" auf "Weiter". Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Nachdem Sie die Bereitstellung durchgeführt haben, klicken Sie auf "Protokoll anzeigen", um verfügbare Protokolldateien anzuzeigen. Klicken Sie auf "Fertig stellen", um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f8428-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="f8428-122">So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten über AOL</span><span class="sxs-lookup"><span data-stu-id="f8428-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="f8428-123">Wenn die erforderliche Vorlage für die Zertifizierungsstelle zur Verfügung gestellt wurde, verwenden Sie auf dem Edgeserver das folgende Cmdlet der Windows PowerShell, um das Zertifikat anzufordern:</span><span class="sxs-lookup"><span data-stu-id="f8428-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="f8428-124">Der standardmäßige Zertifikatname der Vorlage, die für lync Server verwendet wird, ist Webserver.</span><span class="sxs-lookup"><span data-stu-id="f8428-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="f8428-125">Geben Sie nur die an \<template name\> , wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f8428-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f8428-126">Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen mit AOL unterstützen möchte, müssen Sie Windows PowerShell anstelle des Zertifikat-Assistenten verwenden, um das Zertifikat dem externen Edge für die Zugriffs-Edgedienst zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f8428-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="f8428-127">Der Grund dafür ist, dass die "Web Server"-Vorlage der Zertifizierungsstelle, die der Zertifikat-Assistent zum Anfordern von Zertifikaten verwendet, keine EKU-Clientkonfiguration unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8428-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="f8428-128">Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der Zertifizierungsstellenadministrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8428-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

