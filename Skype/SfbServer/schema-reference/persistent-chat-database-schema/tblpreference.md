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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference enthält die Clienteinstellungen des Benutzers. Diese wird in der Regel von Clients vor lync 2013 verwendet.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814553"
---
# <a name="tblpreference"></a><span data-ttu-id="ab11e-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="ab11e-104">tblPreference</span></span>

<span data-ttu-id="ab11e-105">tblPreference enthält die Clienteinstellungen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ab11e-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="ab11e-106">Diese wird in der Regel von Clients vor lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab11e-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="ab11e-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="ab11e-107">**Columns**</span></span>


| <span data-ttu-id="ab11e-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ab11e-108">**Column**</span></span>            | <span data-ttu-id="ab11e-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ab11e-109">**Type**</span></span>                        | <span data-ttu-id="ab11e-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ab11e-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="ab11e-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="ab11e-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="ab11e-112">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ab11e-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="ab11e-113">Beschriftung mit einem Format wie: \<SIP-URI des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="ab11e-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="ab11e-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="ab11e-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="ab11e-115">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ab11e-115">int, not null</span></span>  <br/>            | <span data-ttu-id="ab11e-116">Eine sequenzielle Zahl (pro Etikett) für die Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ab11e-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="ab11e-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="ab11e-117">prefContent</span></span>  <br/>    | <span data-ttu-id="ab11e-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ab11e-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="ab11e-119">Codierter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="ab11e-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="ab11e-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="ab11e-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="ab11e-121">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ab11e-121">int, not null</span></span>  <br/>            | <span data-ttu-id="ab11e-122">Die ID des Prinzipals, der die Einstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ab11e-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="ab11e-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="ab11e-123">**Key**</span></span>

|<span data-ttu-id="ab11e-124">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ab11e-124">**Column**</span></span>|<span data-ttu-id="ab11e-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ab11e-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab11e-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="ab11e-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="ab11e-127">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="ab11e-127">Primary key.</span></span>  <br/> |


