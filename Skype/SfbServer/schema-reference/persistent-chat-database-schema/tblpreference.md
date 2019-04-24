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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212537"
---
# <a name="tblpreference"></a><span data-ttu-id="2148c-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="2148c-104">tblPreference</span></span>

<span data-ttu-id="2148c-105">TblPreference enthält die Clientvoreinstellungen der der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2148c-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="2148c-106">Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="2148c-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="2148c-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="2148c-107">**Columns**</span></span>


| <span data-ttu-id="2148c-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2148c-108">**Column**</span></span>            | <span data-ttu-id="2148c-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2148c-109">**Type**</span></span>                        | <span data-ttu-id="2148c-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2148c-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="2148c-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="2148c-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="2148c-112">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="2148c-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="2148c-113">Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="2148c-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="2148c-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="2148c-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="2148c-115">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2148c-115">int, not null</span></span>  <br/>            | <span data-ttu-id="2148c-116">Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="2148c-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="2148c-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="2148c-117">prefContent</span></span>  <br/>    | <span data-ttu-id="2148c-118">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="2148c-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="2148c-119">Verschlüsselter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2148c-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="2148c-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2148c-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="2148c-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2148c-121">int, not null</span></span>  <br/>            | <span data-ttu-id="2148c-122">ID des Prinzipals, der die Voreinstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="2148c-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="2148c-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="2148c-123">**Key**</span></span>

|<span data-ttu-id="2148c-124">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2148c-124">**Column**</span></span>|<span data-ttu-id="2148c-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2148c-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2148c-126">\<PrefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="2148c-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="2148c-127">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="2148c-127">Primary key.</span></span>  <br/> |


