---
title: 'Lync Server 2013: definieren und Konfigurieren der Topologie'
description: 'Lync Server 2013: definieren und Konfigurieren der Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec444a1ddf434c5a80fdc2d56bdba27573da14ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542081"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="2d054-103">Definieren und Konfigurieren der Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-103">Defining and configuring the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d054-104">_**Letztes Änderungsstand des Themas:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="2d054-104">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="2d054-105">Sie definieren und konfigurieren Ihre Topologie mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="2d054-105">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="2d054-106">Für den Topologie-Generator ist es nicht erforderlich, Mitglied der lokalen Gruppe Administratoren oder einer privilegierten Domänengruppe (beispielsweise Domänenadministratoren) zu sein.</span><span class="sxs-lookup"><span data-stu-id="2d054-106">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="2d054-107">Sie können die Topologie als Standardbenutzer definieren.</span><span class="sxs-lookup"><span data-stu-id="2d054-107">You can define your topology as a standard user.</span></span> <span data-ttu-id="2d054-108">Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll.</span><span class="sxs-lookup"><span data-stu-id="2d054-108">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="2d054-109">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="2d054-109">The choices are the following:</span></span>

  - <span data-ttu-id="2d054-110">Herunterladen der Topologie aus einer vorhandenen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="2d054-110">Download topology from existing deployment</span></span>

  - <span data-ttu-id="2d054-111">Öffnen der Topologie aus einer lokalen Datei</span><span class="sxs-lookup"><span data-stu-id="2d054-111">Open topology from a local file</span></span>

  - <span data-ttu-id="2d054-112">Neue Topologie</span><span class="sxs-lookup"><span data-stu-id="2d054-112">New topology</span></span>

<span data-ttu-id="2d054-113">Wenn Sie bereits eine Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2d054-113">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="2d054-114">Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab.</span><span class="sxs-lookup"><span data-stu-id="2d054-114">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="2d054-115">Wenn Sie über einen vorhandenen zentralen Verwaltungsspeicher verfügen, sollten Sie diese Option immer auswählen.</span><span class="sxs-lookup"><span data-stu-id="2d054-115">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="2d054-116">Wenn Sie keinen zentralen Verwaltungsspeicher eingerichtet haben und eine zuvor gespeicherte Konfiguration bearbeiten möchten, sollten Sie sich dafür entscheiden, die Topologie aus einer lokalen Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d054-116">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="2d054-117">Bei dieser Datei handelt es sich um die Konfigurationsdatei, die in einer vorherigen Sitzung gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="2d054-117">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="2d054-118">Diese Option kann zum Bearbeiten der zuvor gespeicherten Topologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d054-118">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2d054-p104">Wenn Sie bereits eine Topologie veröffentlicht haben, sollten Sie keine lokale Konfigurationsdatei laden. Laden Sie die Topologie in diesem Fall aus einer vorhandenen Bereitstellung herunter.</span><span class="sxs-lookup"><span data-stu-id="2d054-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="2d054-121">Wählen Sie diese Option aus, um eine neue Topologie zu erstellen, wenn Sie eine neue Topologie-Generator-Konfiguration erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d054-121">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="2d054-122">Ein zuvor gespeicherter Entwurf wird nur überschrieben, wenn Sie die neue Topologie unter demselben Dateinamen speichern wie die in einer vorherigen Entwurfssitzung erstellte Topologie.</span><span class="sxs-lookup"><span data-stu-id="2d054-122">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="2d054-123">In jeder dieser Optionen werden Sie aufgefordert, einen Speicherort für die Konfigurationsdatei des Topologie-Generators zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d054-123">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="2d054-124">Die Datei kann an einem lokalen Speicherort, an einem gemeinsam genutzten Speicherort auf einer bereits eingerichteten Dateifreigabe oder auf einem Wechselmedium gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2d054-124">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d054-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2d054-125">In This Section</span></span>

  - [<span data-ttu-id="2d054-126">Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-126">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="2d054-127">Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-127">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="2d054-128">Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-128">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="2d054-129">Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-129">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="2d054-130">Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-130">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="2d054-131">Wählen Sie den zentralen Verwaltungs Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d054-131">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

