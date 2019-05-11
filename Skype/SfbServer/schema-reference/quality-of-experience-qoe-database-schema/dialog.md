---
title: Dialog-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Session Initiation Protocol (SIP)-Dialogfeld.
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920089"
---
# <a name="dialog-table"></a><span data-ttu-id="656e1-103">Dialog-Tabelle</span><span class="sxs-lookup"><span data-stu-id="656e1-103">Dialog table</span></span>
 
<span data-ttu-id="656e1-104">Dialog-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Session Initiation Protocol (SIP)-Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="656e1-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="656e1-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="656e1-105">**Column**</span></span>|<span data-ttu-id="656e1-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="656e1-106">**Data Type**</span></span>|<span data-ttu-id="656e1-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="656e1-107">**Key/Index**</span></span>|<span data-ttu-id="656e1-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="656e1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="656e1-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="656e1-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="656e1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="656e1-110">datetime</span></span>  <br/> |<span data-ttu-id="656e1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="656e1-111">Primary</span></span>  <br/> |<span data-ttu-id="656e1-112">Zeitpunkt der Agent für die Qualität der Betriebsprozesse (QoE) den ersten Bericht vom Anrufer oder angerufenen empfängt Zeit.</span><span class="sxs-lookup"><span data-stu-id="656e1-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="656e1-113">In Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="656e1-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="656e1-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="656e1-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="656e1-115">int</span><span class="sxs-lookup"><span data-stu-id="656e1-115">int</span></span>  <br/> |<span data-ttu-id="656e1-116">Primary</span><span class="sxs-lookup"><span data-stu-id="656e1-116">Primary</span></span>  <br/> |<span data-ttu-id="656e1-117">Sequenznummer zur Unterscheidung von Sitzungen, wenn sie die dieselbe ConferenceDateTime aufweisen.</span><span class="sxs-lookup"><span data-stu-id="656e1-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="656e1-118">**Dialog-ID**</span><span class="sxs-lookup"><span data-stu-id="656e1-118">**DialogID**</span></span> <br/> |<span data-ttu-id="656e1-119">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="656e1-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="656e1-120">Dialog-ID der global eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="656e1-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="656e1-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="656e1-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="656e1-122">int</span><span class="sxs-lookup"><span data-stu-id="656e1-122">int</span></span>  <br/> |<span data-ttu-id="656e1-123">Index</span><span class="sxs-lookup"><span data-stu-id="656e1-123">index</span></span>  <br/> |<span data-ttu-id="656e1-124">Prüfsumme der Dialog-ID.</span><span class="sxs-lookup"><span data-stu-id="656e1-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

