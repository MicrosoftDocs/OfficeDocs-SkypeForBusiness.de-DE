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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294957"
---
# <a name="dialog-table"></a><span data-ttu-id="b264c-103">Dialog-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b264c-103">Dialog table</span></span>
 
<span data-ttu-id="b264c-104">Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="b264c-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="b264c-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b264c-105">**Column**</span></span>|<span data-ttu-id="b264c-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b264c-106">**Data Type**</span></span>|<span data-ttu-id="b264c-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b264c-107">**Key/Index**</span></span>|<span data-ttu-id="b264c-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="b264c-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b264c-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b264c-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b264c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b264c-110">datetime</span></span>  <br/> |<span data-ttu-id="b264c-111">Primary</span><span class="sxs-lookup"><span data-stu-id="b264c-111">Primary</span></span>  <br/> |<span data-ttu-id="b264c-112">Zeitpunkt, zu dem der Quality of Excellence (QoE)-Agent den ersten Bericht von einem Anrufer oder angerufenen erhält.</span><span class="sxs-lookup"><span data-stu-id="b264c-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="b264c-113">Wird in Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b264c-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="b264c-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b264c-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b264c-115">int</span><span class="sxs-lookup"><span data-stu-id="b264c-115">int</span></span>  <br/> |<span data-ttu-id="b264c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b264c-116">Primary</span></span>  <br/> |<span data-ttu-id="b264c-117">Sequenznummer, um Sitzungen zu unterscheiden, wenn Sie dieselbe ConferenceDateTime haben.</span><span class="sxs-lookup"><span data-stu-id="b264c-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="b264c-118">**Dialogfeld-Nr**</span><span class="sxs-lookup"><span data-stu-id="b264c-118">**DialogID**</span></span> <br/> |<span data-ttu-id="b264c-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b264c-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="b264c-120">Dialog Feld-ID, die global eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="b264c-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="b264c-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="b264c-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="b264c-122">int</span><span class="sxs-lookup"><span data-stu-id="b264c-122">int</span></span>  <br/> |<span data-ttu-id="b264c-123">Index</span><span class="sxs-lookup"><span data-stu-id="b264c-123">index</span></span>  <br/> |<span data-ttu-id="b264c-124">Die Prüfsumme der Dialog Feld-ID.</span><span class="sxs-lookup"><span data-stu-id="b264c-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

