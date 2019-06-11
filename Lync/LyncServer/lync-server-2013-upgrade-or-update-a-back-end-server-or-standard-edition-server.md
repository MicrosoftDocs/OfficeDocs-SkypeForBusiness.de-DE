---
title: Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="19365-102">Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19365-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19365-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="19365-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="19365-104">In diesem Thema wird erläutert, wie Sie ein Update auf einem Enterprise Edition-Back-End-Server oder einem Standard Edition-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="19365-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="19365-105">Wenn ein Back-End-Server während eines Upgrades für mindestens 30 Minuten nicht mehr zur Verfügung steht, können Benutzer dann in den Widerstands Modus wechseln.</span><span class="sxs-lookup"><span data-stu-id="19365-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="19365-106">Wenn die Aktualisierung abgeschlossen ist und die Back-End-Server wieder mit den Front-End-Servern im Pool verbunden sind, werden die Benutzer an die vollständige Funktionalität zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="19365-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="19365-107">Wenn das Upgrade weniger als 30 Minuten dauert, sind die Benutzer davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="19365-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="19365-108">Back-End-Server oder Standard Edition-Server aktualisieren</span><span class="sxs-lookup"><span data-stu-id="19365-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="19365-109">Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle CsAdministrator an.</span><span class="sxs-lookup"><span data-stu-id="19365-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="19365-110">Laden Sie das Update herunter und extrahieren Sie es auf die lokale Festplatte.</span><span class="sxs-lookup"><span data-stu-id="19365-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="19365-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="19365-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="19365-112">Beenden Sie lync Server-Dienste.</span><span class="sxs-lookup"><span data-stu-id="19365-112">Stop Lync Server services.</span></span> <span data-ttu-id="19365-113">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="19365-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="19365-114">Beenden Sie den WWW-Dienst (World Wide Web).</span><span class="sxs-lookup"><span data-stu-id="19365-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="19365-115">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="19365-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="19365-116">Schließen Sie alle Fenster der lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="19365-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="19365-117">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="19365-117">Install the update.</span></span>

8.  <span data-ttu-id="19365-118">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="19365-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="19365-119">Beenden Sie lync Server Services erneut, um globalen Assemblycache (GAC) – d-Assemblys abzufangen.</span><span class="sxs-lookup"><span data-stu-id="19365-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="19365-120">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="19365-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="19365-121">Starten Sie den WWW-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="19365-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="19365-122">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="19365-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="19365-123">Wenden Sie die von LyncServerUpdateInstaller. exe vorgenommenen Änderungen auf die SQL Server-Datenbanken an, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="19365-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="19365-124">Wenn dies ein Enterprise Edition-Back-End-Server ist und auf diesem Server keine zusammengefassten Datenbanken wie Archivierungs-oder Überwachungsdatenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="19365-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="19365-125">Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server zusammengefasste Datenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="19365-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="19365-126">Wenn es sich um einen Standard Edition-Server handelt, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="19365-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

