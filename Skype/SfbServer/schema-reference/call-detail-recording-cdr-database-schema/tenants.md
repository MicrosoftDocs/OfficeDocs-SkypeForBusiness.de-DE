---
title: Tenants-Tabelle
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Die Tabelle Mandanten ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814853"
---
# <a name="tenants-table"></a><span data-ttu-id="e06f4-104">Tenants-Tabelle</span><span class="sxs-lookup"><span data-stu-id="e06f4-104">Tenants table</span></span>
 
<span data-ttu-id="e06f4-105">Die Tabelle Mandanten ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Mandanten gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e06f4-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="e06f4-106">Jeder Datensatz in der Tabelle steht für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e06f4-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e06f4-107">In der lokalen Bereitstellung verwendet CdR die integrierte Mandanten-ID, um einen anderen Authentifizierungstyp anzugeben, beispielsweise öffentliche im-Konnektivität, Federated und Anonymous.</span><span class="sxs-lookup"><span data-stu-id="e06f4-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="e06f4-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e06f4-108">**Column**</span></span>|<span data-ttu-id="e06f4-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e06f4-109">**Data Type**</span></span>|<span data-ttu-id="e06f4-110">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e06f4-110">**Key/Index**</span></span>|<span data-ttu-id="e06f4-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="e06f4-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e06f4-112">**Mandanten**</span><span class="sxs-lookup"><span data-stu-id="e06f4-112">**TenantId**</span></span> <br/> |<span data-ttu-id="e06f4-113">int</span><span class="sxs-lookup"><span data-stu-id="e06f4-113">int</span></span>  <br/> |<span data-ttu-id="e06f4-114">Primary</span><span class="sxs-lookup"><span data-stu-id="e06f4-114">Primary</span></span>  <br/> |<span data-ttu-id="e06f4-115">Eindeutige Nummer, die diese Mandanten-ID kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e06f4-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="e06f4-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="e06f4-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="e06f4-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e06f4-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e06f4-118">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="e06f4-118">Allowed values:</span></span> <br/>  <span data-ttu-id="e06f4-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="e06f4-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="e06f4-120">00000000-0000-0000-0000-000000000001-Federated</span><span class="sxs-lookup"><span data-stu-id="e06f4-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="e06f4-121">00000000-0000-0000-0000-000000000002-anonym</span><span class="sxs-lookup"><span data-stu-id="e06f4-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="e06f4-122">00000000-0000-0000-0000-000000000003 – Konnektivität für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="e06f4-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

