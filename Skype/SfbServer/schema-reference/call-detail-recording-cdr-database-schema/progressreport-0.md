---
title: ProgressReport-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: In der ProgressReport-Ansicht werden Informationen zu abgeschlossenen Sitzungen gespeichert. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814983"
---
# <a name="progressreport-view"></a><span data-ttu-id="66fb1-105">ProgressReport-Ansicht</span><span class="sxs-lookup"><span data-stu-id="66fb1-105">ProgressReport view</span></span>
 
<span data-ttu-id="66fb1-106">In der ProgressReport-Ansicht werden Informationen zu abgeschlossenen Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="66fb1-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="66fb1-107">Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können.</span><span class="sxs-lookup"><span data-stu-id="66fb1-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="66fb1-108">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66fb1-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66fb1-109">Die Felder "Fehler", "ErrorReportSeq" und "ProgressReportSeq" beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="66fb1-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="66fb1-110">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="66fb1-110">**Column**</span></span>|<span data-ttu-id="66fb1-111">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="66fb1-111">**Data Type**</span></span>|<span data-ttu-id="66fb1-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="66fb1-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66fb1-113">**Fehlerzeit**</span><span class="sxs-lookup"><span data-stu-id="66fb1-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="66fb1-114">datetime</span><span class="sxs-lookup"><span data-stu-id="66fb1-114">datetime</span></span>  <br/> |<span data-ttu-id="66fb1-115">Zeitpunkt des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="66fb1-115">Time of error occurred.</span></span> <span data-ttu-id="66fb1-116">Wird in Verbindung mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66fb1-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="66fb1-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="66fb1-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="66fb1-118">int</span><span class="sxs-lookup"><span data-stu-id="66fb1-118">int</span></span>  <br/> |<span data-ttu-id="66fb1-119">Die ID-Nummer, um den Fehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66fb1-119">ID number to identify the error.</span></span> <span data-ttu-id="66fb1-120">Wird in Verbindung mit Fehlerzeit verwendet, um einen Fehler eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="66fb1-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="66fb1-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="66fb1-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="66fb1-122">int</span><span class="sxs-lookup"><span data-stu-id="66fb1-122">int</span></span>  <br/> |<span data-ttu-id="66fb1-123">ID zum Identifizieren des Statusberichts</span><span class="sxs-lookup"><span data-stu-id="66fb1-123">ID to identify the progress report.</span></span> <span data-ttu-id="66fb1-124">Wird verwendet, um Fortschrittsberichte desselben Fehlerberichts zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="66fb1-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="66fb1-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="66fb1-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="66fb1-126">int</span><span class="sxs-lookup"><span data-stu-id="66fb1-126">int</span></span>  <br/> |<span data-ttu-id="66fb1-127">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="66fb1-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="66fb1-128">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="66fb1-128">**Source**</span></span> <br/> |<span data-ttu-id="66fb1-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="66fb1-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="66fb1-130">Name des Servers, der den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="66fb1-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="66fb1-131">**Anwendung**</span><span class="sxs-lookup"><span data-stu-id="66fb1-131">**Application**</span></span> <br/> |<span data-ttu-id="66fb1-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="66fb1-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="66fb1-133">Der Name der Anwendung, die den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="66fb1-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="66fb1-134">**Telemetrie**</span><span class="sxs-lookup"><span data-stu-id="66fb1-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="66fb1-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="66fb1-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="66fb1-136">Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="66fb1-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="66fb1-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="66fb1-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="66fb1-138">int</span><span class="sxs-lookup"><span data-stu-id="66fb1-138">int</span></span>  <br/> |<span data-ttu-id="66fb1-139">Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="66fb1-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="66fb1-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="66fb1-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="66fb1-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="66fb1-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="66fb1-142">Weitere Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="66fb1-142">Additional error information.</span></span>  <br/> |
   

