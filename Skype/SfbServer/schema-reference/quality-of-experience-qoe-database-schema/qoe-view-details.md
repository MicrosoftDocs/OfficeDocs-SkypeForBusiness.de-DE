---
title: Details zur QoE-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Ansichten beschäftigen sich mit die am häufigsten verwendeten Szenarien zum Zurückgeben von Daten aus der QoE-SQL-Datenbank. Es empfiehlt sich Ansichten, die zum Erstellen von benutzerdefinierten Berichten anstelle der direkte Zugriff auf die Datenbanktabellen verwendet; Dies liegt daran Ansichten zum Aufrechterhalten der Abwärtskompatibilität Kompatibilität mit zukünftigen Versionen mehr wahrscheinlich eine Rolle spielen.
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212144"
---
# <a name="qoe-view-details"></a><span data-ttu-id="f58b7-104">Details zur QoE-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-104">QoE view details</span></span>
 
<span data-ttu-id="f58b7-105">Ansichten beschäftigen sich mit die am häufigsten verwendeten Szenarien zum Zurückgeben von Daten aus der QoE-SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f58b7-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="f58b7-106">Es empfiehlt sich Ansichten, die zum Erstellen von benutzerdefinierten Berichten anstelle der direkte Zugriff auf die Datenbanktabellen verwendet; Dies liegt daran Ansichten zum Aufrechterhalten der Abwärtskompatibilität Kompatibilität mit zukünftigen Versionen mehr wahrscheinlich eine Rolle spielen.</span><span class="sxs-lookup"><span data-stu-id="f58b7-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="f58b7-107">**Name der Ansicht**</span><span class="sxs-lookup"><span data-stu-id="f58b7-107">**View Name**</span></span>|<span data-ttu-id="f58b7-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f58b7-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f58b7-109">AudioStreamDetail-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="f58b7-110">Speichert Informationen zu jedem Audiostream in der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="f58b7-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="f58b7-111">MediaLine-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="f58b7-112">Speichert Informationen zu jeder medienzeile in der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="f58b7-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="f58b7-113">Eine audiositzung enthält in der Regel eine Audiomedien-Zeile.</span><span class="sxs-lookup"><span data-stu-id="f58b7-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="f58b7-114">Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält eine Audiomedien Zeile und eine Videomedien Zeile; die Sitzung kann jedoch zwei Videomedien Zeilen enthalten, wenn ein Konferenzgerät verwendet wird oder Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f58b7-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="f58b7-115">NetworkConfigurationSettings-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="f58b7-116">Speichert Informationen über die Netzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f58b7-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="f58b7-117">Session-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="f58b7-118">Speichert Informationen über Sitzungen, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="f58b7-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="f58b7-119">UserAgent-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="f58b7-120">Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="f58b7-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="f58b7-121">VideoStreamDetail-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f58b7-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="f58b7-122">Speichert Informationen zu jedem Videostream in der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="f58b7-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

