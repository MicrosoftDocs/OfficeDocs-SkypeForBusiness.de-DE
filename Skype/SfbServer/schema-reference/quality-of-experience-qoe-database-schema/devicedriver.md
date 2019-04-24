---
title: DeviceDriver-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: Die DeviceDriver-Tabelle ist eine Tabelle. Jeder Datensatz steht für ein Treiber vom entweder ein Aufnahmegerät verwendet oder darstellungsgerät.
ms.openlocfilehash: e985c594f0c1ad21bc95d266f908ed77a46ff76a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212256"
---
# <a name="devicedriver-table"></a><span data-ttu-id="63caa-104">DeviceDriver-Tabelle</span><span class="sxs-lookup"><span data-stu-id="63caa-104">DeviceDriver table</span></span>
 
<span data-ttu-id="63caa-105">Die DeviceDriver-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="63caa-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="63caa-106">Jeder Datensatz steht für ein Treiber vom entweder ein Aufnahmegerät verwendet oder darstellungsgerät.</span><span class="sxs-lookup"><span data-stu-id="63caa-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="63caa-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="63caa-107">**Column**</span></span>|<span data-ttu-id="63caa-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="63caa-108">**Data Type**</span></span>|<span data-ttu-id="63caa-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="63caa-109">**Key/Index**</span></span>|<span data-ttu-id="63caa-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="63caa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63caa-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="63caa-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="63caa-112">int</span><span class="sxs-lookup"><span data-stu-id="63caa-112">int</span></span>  <br/> |<span data-ttu-id="63caa-113">Primary</span><span class="sxs-lookup"><span data-stu-id="63caa-113">Primary</span></span>  <br/> |<span data-ttu-id="63caa-114">Eindeutige Zahl, die diesen gerätetreiberdatensatz identifiziert.</span><span class="sxs-lookup"><span data-stu-id="63caa-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="63caa-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="63caa-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="63caa-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="63caa-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="63caa-117">eindeutige</span><span class="sxs-lookup"><span data-stu-id="63caa-117">unique</span></span>  <br/> |<span data-ttu-id="63caa-118">Name des Aufnahmegeräts-Treiber.</span><span class="sxs-lookup"><span data-stu-id="63caa-118">Device driver name.</span></span>  <br/> |
   

