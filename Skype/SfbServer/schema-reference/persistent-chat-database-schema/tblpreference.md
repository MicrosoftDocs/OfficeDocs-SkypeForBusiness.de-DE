---
title: tblPreference
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
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375943"
---
# <a name="tblpreference"></a><span data-ttu-id="e9beb-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="e9beb-104">tblPreference</span></span>

<span data-ttu-id="e9beb-105">TblPreference enthält die Clientvoreinstellungen der der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e9beb-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="e9beb-106">Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9beb-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="e9beb-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="e9beb-107">**Columns**</span></span>


| <span data-ttu-id="e9beb-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e9beb-108">**Column**</span></span>            | <span data-ttu-id="e9beb-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e9beb-109">**Type**</span></span>                        | <span data-ttu-id="e9beb-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e9beb-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="e9beb-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="e9beb-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="e9beb-112">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="e9beb-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="e9beb-113">Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="e9beb-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="e9beb-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="e9beb-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="e9beb-115">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e9beb-115">int, not null</span></span>  <br/>            | <span data-ttu-id="e9beb-116">Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="e9beb-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="e9beb-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="e9beb-117">prefContent</span></span>  <br/>    | <span data-ttu-id="e9beb-118">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="e9beb-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="e9beb-119">Verschlüsselter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="e9beb-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="e9beb-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="e9beb-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="e9beb-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="e9beb-121">int, not null</span></span>  <br/>            | <span data-ttu-id="e9beb-122">ID des Prinzipals, der die Voreinstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="e9beb-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="e9beb-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="e9beb-123">**Key**</span></span>

|<span data-ttu-id="e9beb-124">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e9beb-124">**Column**</span></span>|<span data-ttu-id="e9beb-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e9beb-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9beb-126">\<PrefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="e9beb-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="e9beb-127">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="e9beb-127">Primary key.</span></span>  <br/> |


