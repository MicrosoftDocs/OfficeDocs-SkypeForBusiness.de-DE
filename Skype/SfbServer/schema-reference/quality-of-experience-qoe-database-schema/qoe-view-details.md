---
title: Details zur QoE-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Ansichten decken die am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der QoE SQL-Datenbank ab. Es wird empfohlen, Ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen. Das liegt daran, dass Ansichten eher die Abwärtskompatibilität mit zukünftigen Versionen aufrecht erhalten.
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294754"
---
# <a name="qoe-view-details"></a><span data-ttu-id="19442-104">Details zur QoE-Ansicht</span><span class="sxs-lookup"><span data-stu-id="19442-104">QoE view details</span></span>
 
<span data-ttu-id="19442-105">Ansichten decken die am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der QoE SQL-Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="19442-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="19442-106">Es wird empfohlen, Ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen. Das liegt daran, dass Ansichten eher die Abwärtskompatibilität mit zukünftigen Versionen aufrecht erhalten.</span><span class="sxs-lookup"><span data-stu-id="19442-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="19442-107">**Ansichts Name**</span><span class="sxs-lookup"><span data-stu-id="19442-107">**View Name**</span></span>|<span data-ttu-id="19442-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="19442-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="19442-109">AudioStreamDetail-Ansicht</span><span class="sxs-lookup"><span data-stu-id="19442-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="19442-110">Speichert Informationen zu jedem Audiostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="19442-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="19442-111">Medienansicht</span><span class="sxs-lookup"><span data-stu-id="19442-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="19442-112">Speichert Informationen zu jeder medienzeile in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="19442-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="19442-113">Eine Audiositzung enthält in der Regel eine Audio-medienzeile.</span><span class="sxs-lookup"><span data-stu-id="19442-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="19442-114">Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-medienzeile und eine Video medienzeile. die Sitzung kann jedoch zwei Video Medien Linien enthalten, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19442-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="19442-115">NetworkConfigurationSettings-Ansicht</span><span class="sxs-lookup"><span data-stu-id="19442-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="19442-116">Speichert Informationen zur Netzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="19442-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="19442-117">Sitzungsansicht</span><span class="sxs-lookup"><span data-stu-id="19442-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="19442-118">Speichert Informationen zu Sitzungen mit Datensätzen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="19442-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="19442-119">UserAgent-Ansicht</span><span class="sxs-lookup"><span data-stu-id="19442-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="19442-120">Speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="19442-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="19442-121">VideoStreamDetail-Ansicht</span><span class="sxs-lookup"><span data-stu-id="19442-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="19442-122">Speichert Informationen zu jedem Videostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="19442-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

