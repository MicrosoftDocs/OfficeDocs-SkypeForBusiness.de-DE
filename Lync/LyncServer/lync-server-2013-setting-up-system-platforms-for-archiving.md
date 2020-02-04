---
title: 'Lync Server 2013: Einrichten von Systemplattformen für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13682b7507e133dd49c102bf6c25293ff5da2c08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="ba0b0-102">Einrichten von Systemplattformen für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba0b0-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba0b0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ba0b0-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ba0b0-104">Bevor Sie die Bereitstellung der Archivierung starten, müssen Sie das erforderliche Betriebssystem und alle anderen erforderlichen Software auf Hardware installieren, die den Systemanforderungen entspricht:</span><span class="sxs-lookup"><span data-stu-id="ba0b0-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="ba0b0-105">**Lync Server 2013 Platform**   lync Server 2013-Bereitstellungen verfügen nicht über Archivierungsserver.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="ba0b0-106">Stattdessen werden Unified Data Collection-Agents auf Front-End-Servern und Standard Edition-Servern ausgeführt, um Daten für die Archivierung zu erfassen, sodass keine separate Systemplattform zum Hosten der Archivierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="ba0b0-107">**Datenspeicherplattform**   in lync Server 2013 können Sie Daten mithilfe einer der folgenden Optionen speichern:</span><span class="sxs-lookup"><span data-stu-id="ba0b0-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="ba0b0-108">**Microsoft Exchange-Integration**   Wenn Sie lync Server 2013-Archivierungsdaten mithilfe Ihrer Exchange 2013-Bereitstellung speichern möchten, anstatt eine separate Datenbank für die Speicherung von Archivierungsdaten einzurichten, muss Ihre Exchange-Bereitstellung Exchange 2013 ausführen.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="ba0b0-109">Details zum Einrichten von Systemplattformen für Exchange 2013 finden Sie in der Exchange-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="ba0b0-110">**SQL Server**   Wenn Sie eine separate SQL Server-Datenbank für die Speicherung von Archivierungsdaten verwenden möchten, müssen Sie die Systemplattform für die Datenbank vor der Bereitstellung der Archivierung einrichten, anstatt die Microsoft Exchange-Integration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="ba0b0-111">Die spezifischen Anforderungen an die Systemplattform hängen davon ab, ob Sie Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für die Archivierungsdatenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="ba0b0-112">Details zum Einrichten von Systemplattformen für diese Datenbanken finden Sie in der Produktdokumentation zu Microsoft SQL Server 2008 R2 und Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="ba0b0-113">**Die Dateiserver Plattform**   lync Server 2013 speichert lync Server-Archivierungsdateien an dem Speicherort, den Sie für die Dateispeicherung angeben, wenn Sie Ihre Front-End-Server oder Standard Edition-Server einrichten.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="ba0b0-114">Sie können keinen separaten Speicherort für das Archivieren von Dateispeicher angeben, daher ist keine separate Systemplattform für die Archivierung von Dateispeicher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="ba0b0-115">Wenn Sie die Microsoft Exchange-Integration verwenden, werden die Dateien für archivierte lync-Kommunikationen auf Exchange 2013 2013-Servern für Benutzer gespeichert, die auf diesen Exchange-Servern verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ba0b0-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

