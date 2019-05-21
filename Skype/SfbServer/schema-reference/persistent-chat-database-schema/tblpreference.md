---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference enthält die Clienteinstellungen des Benutzers. Diese wird in der Regel von Clients vor lync 2013 verwendet.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295342"
---
# <a name="tblpreference"></a><span data-ttu-id="83a35-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="83a35-104">tblPreference</span></span>

<span data-ttu-id="83a35-105">tblPreference enthält die Clienteinstellungen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="83a35-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="83a35-106">Diese wird in der Regel von Clients vor lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="83a35-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="83a35-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="83a35-107">**Columns**</span></span>


| <span data-ttu-id="83a35-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="83a35-108">**Column**</span></span>            | <span data-ttu-id="83a35-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="83a35-109">**Type**</span></span>                        | <span data-ttu-id="83a35-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="83a35-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="83a35-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="83a35-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="83a35-112">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="83a35-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="83a35-113">Beschriftung mit einem Format wie: \<SIP-URI des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="83a35-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="83a35-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="83a35-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="83a35-115">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="83a35-115">int, not null</span></span>  <br/>            | <span data-ttu-id="83a35-116">Eine sequenzielle Zahl (pro Etikett) für die Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="83a35-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="83a35-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="83a35-117">prefContent</span></span>  <br/>    | <span data-ttu-id="83a35-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="83a35-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="83a35-119">Codierter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="83a35-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="83a35-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="83a35-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="83a35-121">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="83a35-121">int, not null</span></span>  <br/>            | <span data-ttu-id="83a35-122">Die ID des Prinzipals, der die Einstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="83a35-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="83a35-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="83a35-123">**Key**</span></span>

|<span data-ttu-id="83a35-124">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="83a35-124">**Column**</span></span>|<span data-ttu-id="83a35-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="83a35-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83a35-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="83a35-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="83a35-127">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="83a35-127">Primary key.</span></span>  <br/> |


