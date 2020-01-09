---
title: Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Zusammenfassung: erfahren Sie mehr über den Mobilitätsdienst (MCX) in Skype for Business Server 2015-Unterstützung für Legacy-Clients.'
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992180"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="4dbcb-103">Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4dbcb-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4dbcb-104">**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst (MCX) in Skype for Business Server 2015-Unterstützung für Legacy-Clients.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="4dbcb-105">Dieses Thema gilt nur für Bereitstellungen, die Lync 2010 Lync Mobile-Clients unterstützen und ist für den Mobilitätsdienst (Mcx) vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="4dbcb-106">MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4dbcb-107">Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4dbcb-108">Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="4dbcb-109">Wenn Sie die Ablaufverfolgung für Internet Informationsdienste (IIS) für den Skype for Business Server-Mobilitätsdienst (MCX) aktivieren, können die generierten Protokolldateien pro Tag bis zu drei Gigabyte Speicherplatz belegen.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="4dbcb-110">Die IIS-Ablaufprotokollierung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="4dbcb-111">Sie sollten die Front-End-Server überwachen, um sicherzustellen, dass der Speicherplatz nicht ausgeht.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="4dbcb-112">Standardmäßig werden die Protokolldateien von Internetinformationsdienste (IIS) unter „%SystemDrive%\inetpub\logs\LogFiles“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4dbcb-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="4dbcb-113">Geben Sie an der Befehlszeile Folgendes ein, um die IIS-Ablaufverfolgung für Anforderungen für den gesamten Server zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="4dbcb-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="4dbcb-114">Details zum Befehl **httpLogging** finden Sie in [der Befehlsreferenz](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="4dbcb-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

