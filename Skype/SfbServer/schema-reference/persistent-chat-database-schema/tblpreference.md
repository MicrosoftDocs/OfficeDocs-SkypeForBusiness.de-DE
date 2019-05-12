---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: TblPreference enthält die Clientvoreinstellungen der der Benutzer. Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929918"
---
# <a name="tblpreference"></a><span data-ttu-id="53471-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="53471-104">tblPreference</span></span>

<span data-ttu-id="53471-105">TblPreference enthält die Clientvoreinstellungen der der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="53471-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="53471-106">Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="53471-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="53471-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="53471-107">**Columns**</span></span>


| <span data-ttu-id="53471-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="53471-108">**Column**</span></span>            | <span data-ttu-id="53471-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="53471-109">**Type**</span></span>                        | <span data-ttu-id="53471-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="53471-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="53471-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="53471-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="53471-112">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="53471-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="53471-113">Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="53471-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="53471-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="53471-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="53471-115">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="53471-115">int, not null</span></span>  <br/>            | <span data-ttu-id="53471-116">Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="53471-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="53471-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="53471-117">prefContent</span></span>  <br/>    | <span data-ttu-id="53471-118">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="53471-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="53471-119">Verschlüsselter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="53471-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="53471-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="53471-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="53471-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="53471-121">int, not null</span></span>  <br/>            | <span data-ttu-id="53471-122">ID des Prinzipals, der die Voreinstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="53471-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="53471-123">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="53471-123">**Key**</span></span>

|<span data-ttu-id="53471-124">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="53471-124">**Column**</span></span>|<span data-ttu-id="53471-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="53471-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53471-126">\<PrefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="53471-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="53471-127">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="53471-127">Primary key.</span></span>  <br/> |


