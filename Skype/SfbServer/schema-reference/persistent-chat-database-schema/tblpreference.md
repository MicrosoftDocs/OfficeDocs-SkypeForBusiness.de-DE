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
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="260d5-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="260d5-104">tblPreference</span></span>
 
<span data-ttu-id="260d5-105">TblPreference enthält die Clientvoreinstellungen der der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="260d5-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="260d5-106">Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="260d5-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="260d5-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="260d5-107">**Columns**</span></span>

|<span data-ttu-id="260d5-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="260d5-108">**Column**</span></span>|<span data-ttu-id="260d5-109">**Typ**</span><span class="sxs-lookup"><span data-stu-id="260d5-109">**Type**</span></span>|<span data-ttu-id="260d5-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="260d5-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="260d5-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="260d5-111">prefLabel</span></span>  <br/> |<span data-ttu-id="260d5-112">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="260d5-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="260d5-113">Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\></span><span class="sxs-lookup"><span data-stu-id="260d5-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="260d5-114">Benutzername. \<Voreinstellungen\>.</span><span class="sxs-lookup"><span data-stu-id="260d5-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="260d5-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="260d5-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="260d5-116">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="260d5-116">int, not null</span></span>  <br/> |<span data-ttu-id="260d5-117">Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="260d5-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="260d5-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="260d5-118">prefContent</span></span>  <br/> |<span data-ttu-id="260d5-119">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="260d5-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="260d5-120">Verschlüsselter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="260d5-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="260d5-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="260d5-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="260d5-122">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="260d5-122">int, not null</span></span>  <br/> |<span data-ttu-id="260d5-123">ID des Prinzipals, der die Voreinstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="260d5-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="260d5-124">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="260d5-124">**Key**</span></span>

|<span data-ttu-id="260d5-125">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="260d5-125">**Column**</span></span>|<span data-ttu-id="260d5-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="260d5-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="260d5-127">\<PrefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="260d5-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="260d5-128">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="260d5-128">Primary key.</span></span>  <br/> |
   

