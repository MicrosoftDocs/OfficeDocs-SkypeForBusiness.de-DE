---
title: Phones-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über eine Rufnummer beteiligt VoIP-Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212887"
---
# <a name="phones-table"></a><span data-ttu-id="f245b-104">Phones-Tabelle</span><span class="sxs-lookup"><span data-stu-id="f245b-104">Phones table</span></span>
 
<span data-ttu-id="f245b-105">Phones-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f245b-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="f245b-106">Jeder Datensatz in der Tabelle speichert Informationen über eine Rufnummer beteiligt VoIP-Anrufe, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="f245b-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="f245b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f245b-107">**Column**</span></span>|<span data-ttu-id="f245b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f245b-108">**Data Type**</span></span>|<span data-ttu-id="f245b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="f245b-109">**Key/Index**</span></span>|<span data-ttu-id="f245b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f245b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f245b-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="f245b-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="f245b-112">int</span><span class="sxs-lookup"><span data-stu-id="f245b-112">int</span></span>  <br/> |<span data-ttu-id="f245b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f245b-113">Primary</span></span>  <br/> |<span data-ttu-id="f245b-114">Eindeutige Zahl, die dieses Telefon identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f245b-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="f245b-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="f245b-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="f245b-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="f245b-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="f245b-117">Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="f245b-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="f245b-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="f245b-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="f245b-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="f245b-119">dateTime</span></span>  <br/> ||<span data-ttu-id="f245b-120">Zeitstempel (nur zur internen Verwendung).</span><span class="sxs-lookup"><span data-stu-id="f245b-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="f245b-121">Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f245b-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

