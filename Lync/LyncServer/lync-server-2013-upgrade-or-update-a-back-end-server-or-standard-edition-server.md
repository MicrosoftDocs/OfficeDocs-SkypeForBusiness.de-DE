---
title: Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Server
description: Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c529546bdcf88ada6fd82399d3b65b46b4312db0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580431"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="7727f-103">Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7727f-103">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7727f-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7727f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7727f-105">In diesem Thema wird erläutert, wie Sie ein Update auf einem Enterprise Edition-Back-End-Server oder einem Standard Edition-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="7727f-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="7727f-106">Wenn ein Back-End-Server während des Upgrades mindestens 30 Minuten lang ausfällt, können Benutzer in den Ausfall Sicherheitsmodus wechseln.</span><span class="sxs-lookup"><span data-stu-id="7727f-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="7727f-107">Wenn das Upgrade abgeschlossen ist und die Back-End-Server erneut mit den Front-End-Servern im Pool verbunden sind, werden die Benutzer an die vollständige Funktionalität zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7727f-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="7727f-108">Wenn das Upgrade weniger als 30 Minuten dauern kann, sind die Benutzer nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="7727f-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="7727f-109">So aktualisieren Sie einen Back-End-Server oder Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="7727f-109">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="7727f-110">Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="7727f-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="7727f-111">Laden Sie das Update herunter, und extrahieren Sie es auf die lokale Festplatte.</span><span class="sxs-lookup"><span data-stu-id="7727f-111">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="7727f-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7727f-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="7727f-113">Beenden Sie lync Server Dienste.</span><span class="sxs-lookup"><span data-stu-id="7727f-113">Stop Lync Server services.</span></span> <span data-ttu-id="7727f-114">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-114">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="7727f-115">Beenden Sie den WWW-Dienst (World Wide Web).</span><span class="sxs-lookup"><span data-stu-id="7727f-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="7727f-116">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-116">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="7727f-117">Schließen Sie alle lync Server-Verwaltungsshell Fenster.</span><span class="sxs-lookup"><span data-stu-id="7727f-117">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="7727f-118">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="7727f-118">Install the update.</span></span>

8.  <span data-ttu-id="7727f-119">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7727f-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="7727f-120">Beenden Sie lync Server Dienste erneut, um den globalen Assemblycache (GAC) – d-Assemblys zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="7727f-120">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="7727f-121">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-121">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="7727f-122">Starten Sie den WWW-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="7727f-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="7727f-123">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-123">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="7727f-124">Übernehmen Sie die mit "LyncServerUpdateInstaller.exe" vorgenommenen Änderungen für die SQL Server-Datenbanken, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7727f-124">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="7727f-125">Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und keine zusammengefassten Datenbanken auf diesem Server vorhanden sind, wie etwa Archivierungs-oder Überwachungsdatenbanken, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="7727f-126">Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server zusammengefasste Datenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="7727f-127">Wenn es sich um eine Standard Edition-Server handelt, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="7727f-127">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

