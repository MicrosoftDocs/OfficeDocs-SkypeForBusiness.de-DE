---
title: Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Zusammenfassung: Lesen Sie in diesem Thema, um Informationen zu Hardware- und softwareanforderungen für die Archivierung in Skype für Business Server 2015 zu informieren.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="6e5f4-103">Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6e5f4-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e5f4-104">**Zusammenfassung:** Lesen Sie in diesem Thema, um Informationen zu Hardware- und softwareanforderungen für die Archivierung in Skype für Business Server 2015 zu informieren.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6e5f4-105">Skype für die Archivierung Business Server 2015 ist nun Teil der Front-End-Rolle, daher Sie keinen separaten Server installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="6e5f4-106">Sie müssen jedoch die folgenden Anforderungen berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="6e5f4-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="6e5f4-107">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e5f4-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="6e5f4-108">Erforderliche Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e5f4-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="6e5f4-109">Datenspeicherungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e5f4-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="6e5f4-110">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e5f4-110">Infrastructure requirements</span></span>

<span data-ttu-id="6e5f4-111">Skype für Business-Archivierung infrastrukturanforderungen sind die gleichen wie bei der Bereitstellung von Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="6e5f4-112">Weitere Informationen hierzu finden Sie unter [Anforderungen für Ihre Skype für Business-Umgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f4-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="6e5f4-113">Erforderliche Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e5f4-113">Prerequisite software requirements</span></span>

<span data-ttu-id="6e5f4-114">Archivierung erforderlichen Komponenten für Skype für Business Server sind aufgrund der folgenden einfacher als in früheren Versionen von Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6e5f4-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="6e5f4-115">Da eine Serverrolle Archivierung nicht mehr ist, müssen Sie nicht auf einen separaten Server für die Archivierung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="6e5f4-116">Stattdessen werden auf jedem Front-End-Pool der Enterprise Edition und auf jedem Server der Standard Edition automatisch einheitliche Datensammlungs-Agents installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="6e5f4-117">Sie müssen Ihre Archivierungstopologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="6e5f4-118">Archivierung werden die Skype für Business Server-Dateispeicher für die temporäre Speicherung von Dateien, sodass keine separate dateispeicherung für die Archivierung eingerichtet werden mit Besprechungsinhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="6e5f4-119">In Skype für Business Server ist das Microsoft Message Queuing nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="6e5f4-120">Datenspeicherungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6e5f4-120">Data Storage requirements</span></span>

<span data-ttu-id="6e5f4-p104">Die Infrastruktur für Archivierungsspeicher muss eingerichtet werden. Dies umfasst eine oder beide der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="6e5f4-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="6e5f4-123">**Microsoft Exchange-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="6e5f4-124">Dateien mit Besprechungsinhalten, z. B. PowerPoint-Präsentationen, werden als Anlagen archiviert.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="6e5f4-125">Wenn Sie Skype für Geschäftsdaten für Archivierung mit Exchange Kompatibilitätsdaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und stellen Sie sicher, dass die maximale Speichergröße Speicherung von der Besprechung Inhaltsdateien unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="6e5f4-126">Sie müssen vor dem Bereitstellen und Aktivieren der Archivierung die Option Microsoft Exchange-Integration mit Exchange bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="6e5f4-127">Wenn Sie Exchange-Speicher verwenden, müssen Sie nicht zum Bereitstellen von separater SQL Server-Datenbanken für die Archivierung, es sei denn, Sie Skype für Unternehmensbenutzer verfügen, die nicht auf Ihren Exchange-Servern verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="6e5f4-128">Wenn Sie die Archivierung die Option Microsoft Exchange-Integration mit bereitstellen, wird Skype für Geschäftsdaten-Archivierung mit Exchange Kompatibilitätsdaten nur für die Benutzer gespeichert, die auf Ihren Exchange-Servern verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="6e5f4-129">**Skype als Archivierungsspeicher Business Server**.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="6e5f4-130">Zur Unterstützung von Benutzern, die nicht auf Exchange-Servern verwaltet werden, oder wenn Sie nicht die Option Microsoft Exchange-Integration verwenden möchten, müssen Sie Archivierungsspeicher mithilfe einer SQL Server-Datenbank bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="6e5f4-131">Skype für Business Server unterstützt die folgenden 64-Bit-Versionen von SQL Server:</span><span class="sxs-lookup"><span data-stu-id="6e5f4-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="6e5f4-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e5f4-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="6e5f4-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="6e5f4-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="6e5f4-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e5f4-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="6e5f4-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="6e5f4-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="6e5f4-136">Microsoft SQL Server 2014 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e5f4-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="6e5f4-137">Microsoft SQL Server 2014 Standard</span><span class="sxs-lookup"><span data-stu-id="6e5f4-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e5f4-138">Microsoft SQL Server Express-Versionen werden für die Archivierung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="6e5f4-139">32-Bit-Versionen von SQL Server werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="6e5f4-140">Zusätzliche Anforderungen für SQL Server und Einschränkungen finden Sie unter [Anforderungen für Ihre Skype für Business-Umgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f4-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="6e5f4-141">Sie müssen die SQL Server-Plattformen vor der Bereitstellung und Aktivieren der Archivierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="6e5f4-142">Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen der Topologie erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="6e5f4-143">Sie können die Datenbank auch später erstellen, z. B. im Rahmen des Installationsverfahrens.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="6e5f4-144">Ausführliche Informationen zu SQL Server finden Sie im [SQL Server-TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span><span class="sxs-lookup"><span data-stu-id="6e5f4-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="6e5f4-145">Die Auslastung im Zuge der Archivierung kann erheblich steigen.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="6e5f4-146">Aus diesem Grund sollten Sie sicherstellen, dass Speicherplatz für Front-End-Servern geeignet ist, auf dem die Archivierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6e5f4-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

