---
title: tblPreference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: TblPreference enthält die Clientvoreinstellungen der der Benutzer. Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879791"
---
# <a name="tblpreference"></a><span data-ttu-id="2b4ae-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="2b4ae-104">tblPreference</span></span>

<span data-ttu-id="2b4ae-105">TblPreference enthält die Clientvoreinstellungen der der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2b4ae-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="2b4ae-106">Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b4ae-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="2b4ae-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-107">**Columns**</span></span>


| <span data-ttu-id="2b4ae-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-108">**Column**</span></span>            | <span data-ttu-id="2b4ae-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-109">**Type**</span></span>                        | <span data-ttu-id="2b4ae-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="2b4ae-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="2b4ae-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="2b4ae-112">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="2b4ae-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="2b4ae-113">Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="2b4ae-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="2b4ae-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="2b4ae-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="2b4ae-115">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2b4ae-115">int, not null</span></span>  <br/>            | <span data-ttu-id="2b4ae-116">Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="2b4ae-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="2b4ae-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="2b4ae-117">prefContent</span></span>  <br/>    | <span data-ttu-id="2b4ae-118">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="2b4ae-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="2b4ae-119">Verschlüsselter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2b4ae-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="2b4ae-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2b4ae-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="2b4ae-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2b4ae-121">int, not null</span></span>  <br/>            | <span data-ttu-id="2b4ae-122">ID des Prinzipals, der die Voreinstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="2b4ae-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="2b4ae-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-123">**Key**</span></span>

|<span data-ttu-id="2b4ae-124">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-124">**Column**</span></span>|<span data-ttu-id="2b4ae-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2b4ae-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b4ae-126">\<PrefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="2b4ae-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="2b4ae-127">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="2b4ae-127">Primary key.</span></span>  <br/> |


