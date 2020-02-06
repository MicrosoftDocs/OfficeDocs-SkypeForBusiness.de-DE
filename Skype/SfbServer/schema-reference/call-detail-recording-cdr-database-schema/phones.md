---
title: Phones-Tabelle
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Die Tabelle Telefone ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815003"
---
# <a name="phones-table"></a><span data-ttu-id="2a67b-104">Phones-Tabelle</span><span class="sxs-lookup"><span data-stu-id="2a67b-104">Phones table</span></span>
 
<span data-ttu-id="2a67b-105">Die Tabelle Telefone ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2a67b-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="2a67b-106">Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2a67b-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="2a67b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2a67b-107">**Column**</span></span>|<span data-ttu-id="2a67b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2a67b-108">**Data Type**</span></span>|<span data-ttu-id="2a67b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="2a67b-109">**Key/Index**</span></span>|<span data-ttu-id="2a67b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="2a67b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a67b-111">**Telefonnummer**</span><span class="sxs-lookup"><span data-stu-id="2a67b-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="2a67b-112">int</span><span class="sxs-lookup"><span data-stu-id="2a67b-112">int</span></span>  <br/> |<span data-ttu-id="2a67b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2a67b-113">Primary</span></span>  <br/> |<span data-ttu-id="2a67b-114">Eindeutige Nummer, die dieses Telefon kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="2a67b-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="2a67b-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="2a67b-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="2a67b-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2a67b-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="2a67b-117">Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="2a67b-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="2a67b-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2a67b-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2a67b-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="2a67b-119">dateTime</span></span>  <br/> ||<span data-ttu-id="2a67b-120">Zeitstempel (nur für interne Nutzung).</span><span class="sxs-lookup"><span data-stu-id="2a67b-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="2a67b-121">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2a67b-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

