---
title: Dialog-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Session Initiation Protocol (SIP)-Dialogfeld.
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a><span data-ttu-id="4400b-103">Dialog-Tabelle</span><span class="sxs-lookup"><span data-stu-id="4400b-103">Dialog table</span></span>
 
<span data-ttu-id="4400b-104">Dialog-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Session Initiation Protocol (SIP)-Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="4400b-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="4400b-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4400b-105">**Column**</span></span>|<span data-ttu-id="4400b-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="4400b-106">**Data Type**</span></span>|<span data-ttu-id="4400b-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="4400b-107">**Key/Index**</span></span>|<span data-ttu-id="4400b-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="4400b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4400b-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4400b-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4400b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4400b-110">datetime</span></span>  <br/> |<span data-ttu-id="4400b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4400b-111">Primary</span></span>  <br/> |<span data-ttu-id="4400b-112">Zeitpunkt der Agent für die Qualität der Betriebsprozesse (QoE) den ersten Bericht vom Anrufer oder angerufenen empfängt Zeit.</span><span class="sxs-lookup"><span data-stu-id="4400b-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="4400b-113">In Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4400b-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="4400b-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4400b-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4400b-115">int</span><span class="sxs-lookup"><span data-stu-id="4400b-115">int</span></span>  <br/> |<span data-ttu-id="4400b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="4400b-116">Primary</span></span>  <br/> |<span data-ttu-id="4400b-117">Sequenznummer zur Unterscheidung von Sitzungen, wenn sie die dieselbe ConferenceDateTime aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4400b-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="4400b-118">**Dialog-ID**</span><span class="sxs-lookup"><span data-stu-id="4400b-118">**DialogID**</span></span> <br/> |<span data-ttu-id="4400b-119">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="4400b-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="4400b-120">Dialog-ID der global eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="4400b-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="4400b-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="4400b-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="4400b-122">int</span><span class="sxs-lookup"><span data-stu-id="4400b-122">int</span></span>  <br/> |<span data-ttu-id="4400b-123">Index</span><span class="sxs-lookup"><span data-stu-id="4400b-123">index</span></span>  <br/> |<span data-ttu-id="4400b-124">Prüfsumme der Dialog-ID.</span><span class="sxs-lookup"><span data-stu-id="4400b-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

