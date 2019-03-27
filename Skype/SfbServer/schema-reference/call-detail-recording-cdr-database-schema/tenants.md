---
title: Tenants-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Die Mandanten-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Mandanten gespeichert. Jeder Datensatz in der Tabelle steht für einen Mandanten.
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873990"
---
# <a name="tenants-table"></a><span data-ttu-id="2f0d4-104">Tenants-Tabelle</span><span class="sxs-lookup"><span data-stu-id="2f0d4-104">Tenants table</span></span>
 
<span data-ttu-id="2f0d4-105">Die Mandanten-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Mandanten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2f0d4-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="2f0d4-106">Jeder Datensatz in der Tabelle steht für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2f0d4-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f0d4-107">In der lokalen Bereitstellung verwendet CDR die integrierte Mandanten-ID, um verschiedene Authentifizierungstyp wie öffentliche Instant Messaging-Diensten Federated und anonym anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f0d4-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="2f0d4-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2f0d4-108">**Column**</span></span>|<span data-ttu-id="2f0d4-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2f0d4-109">**Data Type**</span></span>|<span data-ttu-id="2f0d4-110">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="2f0d4-110">**Key/Index**</span></span>|<span data-ttu-id="2f0d4-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="2f0d4-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f0d4-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="2f0d4-112">**TenantId**</span></span> <br/> |<span data-ttu-id="2f0d4-113">int</span><span class="sxs-lookup"><span data-stu-id="2f0d4-113">int</span></span>  <br/> |<span data-ttu-id="2f0d4-114">Primary</span><span class="sxs-lookup"><span data-stu-id="2f0d4-114">Primary</span></span>  <br/> |<span data-ttu-id="2f0d4-115">Eindeutige Zahl, die diese Mandanten-ID identifiziert</span><span class="sxs-lookup"><span data-stu-id="2f0d4-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="2f0d4-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="2f0d4-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="2f0d4-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2f0d4-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2f0d4-118">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="2f0d4-118">Allowed values:</span></span> <br/>  <span data-ttu-id="2f0d4-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="2f0d4-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="2f0d4-120">00000000-0000-0000-0000-000000000001-Verbund</span><span class="sxs-lookup"><span data-stu-id="2f0d4-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="2f0d4-121">00000000-0000-0000-0000-000000000002 - anonyme</span><span class="sxs-lookup"><span data-stu-id="2f0d4-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="2f0d4-122">00000000-0000-0000-0000-000000000003-öffentliche Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="2f0d4-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

