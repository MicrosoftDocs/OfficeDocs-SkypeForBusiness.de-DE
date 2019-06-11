---
title: 'Lync Server 2013: Einrichten der öffentlichen Chatkonnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="1ee6f-102">Einrichten der öffentlichen Chatkonnektivität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee6f-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee6f-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1ee6f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1ee6f-104">Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen (im) mit AOL unterstützen möchte, können Sie den lync Server-Bereitstellungs-Assistenten nicht verwenden, um das Zertifikat anzufordern.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="1ee6f-105">Führen Sie stattdessen die Schritte im folgenden Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="1ee6f-106">Einrichten der öffentlichen Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="1ee6f-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="1ee6f-107">Öffnen Sie auf einem Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="1ee6f-108">Erweitern Sie Edge-Pools, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edge-Serverpool.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="1ee6f-109">Wählen Sie Eigenschaften bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="1ee6f-110">Wählen Sie in Eigenschaften bearbeiten unter Allgemein die Option Föderation für diesen Edge-Pool aktivieren (Port 5061) aus.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="1ee6f-111">Klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-111">Click OK.</span></span>

3.  <span data-ttu-id="1ee6f-112">Klicken Sie auf Aktion, wählen Sie Topologie aus, und wählen Sie veröffentlichen aus.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="1ee6f-113">Wenn Sie dazu aufgefordert werden, die Topologie zu veröffentlichen, klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="1ee6f-114">Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf Fertig stellen.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="1ee6f-115">Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="1ee6f-116">Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="1ee6f-117">Klicken Sie erneut auf ausführen.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-117">Click Run Again.</span></span>

5.  <span data-ttu-id="1ee6f-118">Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="1ee6f-119">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="1ee6f-120">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="1ee6f-121">Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="1ee6f-122">So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edge-Servers zur Unterstützung öffentlicher Chat Verbindungen mit AOL</span><span class="sxs-lookup"><span data-stu-id="1ee6f-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="1ee6f-123">Wenn die erforderliche Vorlage für die Zertifizierungsstelle verfügbar ist, verwenden Sie das folgende Windows PowerShell-Cmdlet auf dem Edgeserver, um das Zertifikat anzufordern.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="1ee6f-124">Der Standardzertifikat Name der für lync Server verwendeten Vorlage ist Web Server.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="1ee6f-125">Geben Sie nur \<den Vorlagen\> Namen an, wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1ee6f-126">Wenn Ihre Organisation öffentliche Chat Verbindungen mit AOL unterstützen möchte, müssen Sie anstelle des Zertifikat-Assistenten Windows PowerShell verwenden, um das Zertifikat anzufordern, das dem externen Edge für den Access Edge-Dienst zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="1ee6f-127">Der Grund hierfür ist, dass die vom Zertifikat-Assistenten zum Anfordern eines Zertifikats verwendete Zertifikat Zertifizierungsstellen-Webservervorlage die Client-EKU-Konfiguration nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="1ee6f-128">Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der CA-Administrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ee6f-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

