---
title: Tenants-Tabelle
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
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a><span data-ttu-id="34870-104">Tenants-Tabelle</span><span class="sxs-lookup"><span data-stu-id="34870-104">Tenants table</span></span>
 
<span data-ttu-id="34870-105">Die Mandanten-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Mandanten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="34870-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="34870-106">Jeder Datensatz in der Tabelle steht für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="34870-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34870-107">In der lokalen Bereitstellung verwendet CDR die integrierte Mandanten-ID, um verschiedene Authentifizierungstyp wie öffentliche Instant Messaging-Diensten Federated und anonym anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="34870-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="34870-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="34870-108">**Column**</span></span>|<span data-ttu-id="34870-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="34870-109">**Data Type**</span></span>|<span data-ttu-id="34870-110">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="34870-110">**Key/Index**</span></span>|<span data-ttu-id="34870-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="34870-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34870-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="34870-112">**TenantId**</span></span> <br/> |<span data-ttu-id="34870-113">int</span><span class="sxs-lookup"><span data-stu-id="34870-113">int</span></span>  <br/> |<span data-ttu-id="34870-114">Primary</span><span class="sxs-lookup"><span data-stu-id="34870-114">Primary</span></span>  <br/> |<span data-ttu-id="34870-115">Eindeutige Zahl, die diese Mandanten-ID identifiziert</span><span class="sxs-lookup"><span data-stu-id="34870-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="34870-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="34870-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="34870-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34870-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="34870-118">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="34870-118">Allowed values:</span></span> <br/>  <span data-ttu-id="34870-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="34870-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="34870-120">00000000-0000-0000-0000-000000000001-Verbund</span><span class="sxs-lookup"><span data-stu-id="34870-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="34870-121">00000000-0000-0000-0000-000000000002 - anonyme</span><span class="sxs-lookup"><span data-stu-id="34870-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="34870-122">00000000-0000-0000-0000-000000000003-öffentliche Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="34870-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

