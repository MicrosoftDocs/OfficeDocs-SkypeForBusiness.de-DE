---
title: DeviceDriver-Tabelle
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: Die Tabelle ACPITreiber ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Treiber, der entweder von einem Aufnahmegerät oder einem Render-Gerät verwendet wird.
ms.openlocfilehash: 8a502a1fc07c3541522931554064f7708b3e6187
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809713"
---
# <a name="devicedriver-table"></a><span data-ttu-id="62f54-104">DeviceDriver-Tabelle</span><span class="sxs-lookup"><span data-stu-id="62f54-104">DeviceDriver table</span></span>
 
<span data-ttu-id="62f54-105">Die Tabelle ACPITreiber ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="62f54-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="62f54-106">Jeder Datensatz steht für einen Treiber, der entweder von einem Aufnahmegerät oder einem Render-Gerät verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62f54-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="62f54-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="62f54-107">**Column**</span></span>|<span data-ttu-id="62f54-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="62f54-108">**Data Type**</span></span>|<span data-ttu-id="62f54-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="62f54-109">**Key/Index**</span></span>|<span data-ttu-id="62f54-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="62f54-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62f54-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="62f54-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="62f54-112">int</span><span class="sxs-lookup"><span data-stu-id="62f54-112">int</span></span>  <br/> |<span data-ttu-id="62f54-113">Primary</span><span class="sxs-lookup"><span data-stu-id="62f54-113">Primary</span></span>  <br/> |<span data-ttu-id="62f54-114">Eindeutige Nummer, die diesen Gerätetreiber Eintrag kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="62f54-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="62f54-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="62f54-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="62f54-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="62f54-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="62f54-117">eindeutigen</span><span class="sxs-lookup"><span data-stu-id="62f54-117">unique</span></span>  <br/> |<span data-ttu-id="62f54-118">Name des Gerätetreibers</span><span class="sxs-lookup"><span data-stu-id="62f54-118">Device driver name.</span></span>  <br/> |
   

