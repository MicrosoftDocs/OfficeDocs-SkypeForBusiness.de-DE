---
title: Dialog-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809533"
---
# <a name="dialog-table"></a><span data-ttu-id="726b1-103">Dialog-Tabelle</span><span class="sxs-lookup"><span data-stu-id="726b1-103">Dialog table</span></span>
 
<span data-ttu-id="726b1-104">Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="726b1-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="726b1-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="726b1-105">**Column**</span></span>|<span data-ttu-id="726b1-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="726b1-106">**Data Type**</span></span>|<span data-ttu-id="726b1-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="726b1-107">**Key/Index**</span></span>|<span data-ttu-id="726b1-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="726b1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="726b1-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="726b1-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="726b1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="726b1-110">datetime</span></span>  <br/> |<span data-ttu-id="726b1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="726b1-111">Primary</span></span>  <br/> |<span data-ttu-id="726b1-112">Zeitpunkt, zu dem der Quality of Excellence (QoE)-Agent den ersten Bericht von einem Anrufer oder angerufenen erhält.</span><span class="sxs-lookup"><span data-stu-id="726b1-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="726b1-113">Wird in Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="726b1-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="726b1-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="726b1-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="726b1-115">int</span><span class="sxs-lookup"><span data-stu-id="726b1-115">int</span></span>  <br/> |<span data-ttu-id="726b1-116">Primary</span><span class="sxs-lookup"><span data-stu-id="726b1-116">Primary</span></span>  <br/> |<span data-ttu-id="726b1-117">Sequenznummer, um Sitzungen zu unterscheiden, wenn Sie dieselbe ConferenceDateTime haben.</span><span class="sxs-lookup"><span data-stu-id="726b1-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="726b1-118">**Dialogfeld-Nr**</span><span class="sxs-lookup"><span data-stu-id="726b1-118">**DialogID**</span></span> <br/> |<span data-ttu-id="726b1-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="726b1-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="726b1-120">Dialog Feld-ID, die global eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="726b1-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="726b1-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="726b1-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="726b1-122">int</span><span class="sxs-lookup"><span data-stu-id="726b1-122">int</span></span>  <br/> |<span data-ttu-id="726b1-123">Index</span><span class="sxs-lookup"><span data-stu-id="726b1-123">index</span></span>  <br/> |<span data-ttu-id="726b1-124">Die Prüfsumme der Dialog Feld-ID.</span><span class="sxs-lookup"><span data-stu-id="726b1-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

