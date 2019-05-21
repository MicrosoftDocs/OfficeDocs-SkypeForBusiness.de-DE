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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Die Tabelle Telefone ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295944"
---
# <a name="phones-table"></a><span data-ttu-id="02c54-104">Phones-Tabelle</span><span class="sxs-lookup"><span data-stu-id="02c54-104">Phones table</span></span>
 
<span data-ttu-id="02c54-105">Die Tabelle Telefone ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="02c54-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="02c54-106">Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="02c54-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="02c54-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="02c54-107">**Column**</span></span>|<span data-ttu-id="02c54-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="02c54-108">**Data Type**</span></span>|<span data-ttu-id="02c54-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="02c54-109">**Key/Index**</span></span>|<span data-ttu-id="02c54-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="02c54-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="02c54-111">**Telefonnummer**</span><span class="sxs-lookup"><span data-stu-id="02c54-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="02c54-112">int</span><span class="sxs-lookup"><span data-stu-id="02c54-112">int</span></span>  <br/> |<span data-ttu-id="02c54-113">Primary</span><span class="sxs-lookup"><span data-stu-id="02c54-113">Primary</span></span>  <br/> |<span data-ttu-id="02c54-114">Eindeutige Nummer, die dieses Telefon kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="02c54-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="02c54-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="02c54-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="02c54-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="02c54-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="02c54-117">Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="02c54-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="02c54-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="02c54-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="02c54-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="02c54-119">dateTime</span></span>  <br/> ||<span data-ttu-id="02c54-120">Zeitstempel (nur für interne Nutzung).</span><span class="sxs-lookup"><span data-stu-id="02c54-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="02c54-121">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="02c54-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

