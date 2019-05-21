---
title: Device-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295006"
---
# <a name="device-table"></a><span data-ttu-id="28b76-104">Device-Tabelle</span><span class="sxs-lookup"><span data-stu-id="28b76-104">Device table</span></span>
 
<span data-ttu-id="28b76-105">Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="28b76-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="28b76-106">Jeder Datensatz in der Tabelle steht für ein Gerät.</span><span class="sxs-lookup"><span data-stu-id="28b76-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="28b76-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="28b76-107">**Column**</span></span>|<span data-ttu-id="28b76-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="28b76-108">**Data Type**</span></span>|<span data-ttu-id="28b76-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="28b76-109">**Key/Index**</span></span>|<span data-ttu-id="28b76-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="28b76-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28b76-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="28b76-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="28b76-112">int</span><span class="sxs-lookup"><span data-stu-id="28b76-112">int</span></span>  <br/> |<span data-ttu-id="28b76-113">Primary</span><span class="sxs-lookup"><span data-stu-id="28b76-113">Primary</span></span>  <br/> |<span data-ttu-id="28b76-114">Eindeutige Nummer, die dieses Gerät kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="28b76-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="28b76-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="28b76-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="28b76-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="28b76-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="28b76-117">DeviceName + DeviceType ist eindeutig</span><span class="sxs-lookup"><span data-stu-id="28b76-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="28b76-118">Gerätename.</span><span class="sxs-lookup"><span data-stu-id="28b76-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="28b76-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="28b76-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="28b76-120">bit</span><span class="sxs-lookup"><span data-stu-id="28b76-120">bit</span></span>  <br/> |<span data-ttu-id="28b76-121">DeviceName + DeviceType ist eindeutig</span><span class="sxs-lookup"><span data-stu-id="28b76-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="28b76-122">Gerätetyp.</span><span class="sxs-lookup"><span data-stu-id="28b76-122">Device type.</span></span> <span data-ttu-id="28b76-123">1 ist ein Aufnahmegerät, 0 ist ein Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="28b76-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

