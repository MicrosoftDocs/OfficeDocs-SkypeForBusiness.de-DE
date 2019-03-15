---
title: Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst ("MCX") in Skype für die Unterstützung für Clients von Vorversionen Business Server 2015.'
ms.openlocfilehash: 72d5dc8cafc0bbf0b33533d4548f2c7f1cd2d466
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226981"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="3eaf8-103">Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3eaf8-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3eaf8-104">**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst ("MCX") in Skype für Business Server 2015 Unterstützung für Clients von Vorversionen.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="3eaf8-105">Dieses Thema gilt nur für Bereitstellungen, die Lync 2010 Lync Mobile-Clients unterstützen und ist für den Mobilitätsdienst (Mcx) vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="3eaf8-106">Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3eaf8-107">Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3eaf8-108">Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="3eaf8-109">Wenn Sie Internetinformationsdienste (Internet Information Services, IIS) Request Tracing für Business Server-Mobilitätsdienst ("MCX") für die Skype aktivieren, können die Protokolldateien, die generiert werden bis zu drei Gigabyte Speicherplatz pro Tag nutzen.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="3eaf8-110">Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="3eaf8-111">Überwachen Sie den Front-End-Servern dafür sorgen, dass diese nicht mehr Festplattenspeicherplatz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="3eaf8-112">Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter „%SystemDrive%\inetpub\logs\LogFiles“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3eaf8-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="3eaf8-113">Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3eaf8-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="3eaf8-114">Ausführliche Informationen zum Befehl **HttpLogging** finden Sie unter [der Befehlsverzeichnis](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="3eaf8-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

