---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: "\"tblroletype\" ist eine statische Nachschlagetabelle mit Rollentypen und deren zugeordneten Berechtigungssätzen."
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212411"
---
# <a name="tblroletype"></a><span data-ttu-id="16413-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="16413-103">tblRoleType</span></span>
 
<span data-ttu-id="16413-104">"tblroletype" ist eine statische Nachschlagetabelle mit Rollentypen und deren zugeordneten Berechtigungssätzen.</span><span class="sxs-lookup"><span data-stu-id="16413-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="16413-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="16413-105">**Columns**</span></span>

|<span data-ttu-id="16413-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="16413-106">**Column**</span></span>|<span data-ttu-id="16413-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="16413-107">**Type**</span></span>|<span data-ttu-id="16413-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="16413-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16413-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="16413-109">rtypeID</span></span>  <br/> |<span data-ttu-id="16413-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="16413-110">int, not null</span></span>  <br/> |<span data-ttu-id="16413-111">Rollentyps.</span><span class="sxs-lookup"><span data-stu-id="16413-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="16413-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="16413-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="16413-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="16413-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="16413-114">Beschreibung der Rolle-Typ.</span><span class="sxs-lookup"><span data-stu-id="16413-114">Role type description.</span></span> <span data-ttu-id="16413-115">Es gibt vier verfügbare Rollen:</span><span class="sxs-lookup"><span data-stu-id="16413-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="16413-116">Mitglied: chatroommitglied</span><span class="sxs-lookup"><span data-stu-id="16413-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="16413-117">Manager: chatroommanager</span><span class="sxs-lookup"><span data-stu-id="16413-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="16413-118">Leitend: Referent für einen auditoriumchatroom</span><span class="sxs-lookup"><span data-stu-id="16413-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="16413-119">Ersteller: Kann Chatrooms erstellen.</span><span class="sxs-lookup"><span data-stu-id="16413-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="16413-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="16413-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="16413-121">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="16413-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="16413-122">Berechtigungssatz für die Rolle.</span><span class="sxs-lookup"><span data-stu-id="16413-122">Permission set for the role.</span></span> <span data-ttu-id="16413-123">Die verwendete Bits sind:</span><span class="sxs-lookup"><span data-stu-id="16413-123">The used bits are:</span></span> <br/>  <span data-ttu-id="16413-124">2: true, wenn die Rolle Knoten verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="16413-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="16413-125">4: true, wenn die Rolle untergeordnete Knoten erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="16413-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="16413-126">7: true, wenn die Rolle einen Chatroom (oder untergeordnete Chatrooms einer Kategorie) teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="16413-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="16413-127">8: true, wenn die Rolle in einem Chatroom (oder untergeordnete Chatrooms einer Kategorie) chatten kann.</span><span class="sxs-lookup"><span data-stu-id="16413-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="16413-128">10: true, wenn die Rolle den Chatverlauf, auch wenn nicht in einem Chatroom beigetreten lesen kann.</span><span class="sxs-lookup"><span data-stu-id="16413-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="16413-129">11: true, wenn die Rolle den Chatroom sehen kann.</span><span class="sxs-lookup"><span data-stu-id="16413-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="16413-130">(Dies wird durch Faktoren beeinflusst, beispielsweise von Bereich und Sichtbarkeit weiterentwickelte.)</span><span class="sxs-lookup"><span data-stu-id="16413-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="16413-131">12: true, wenn die Rolle in einem auditoriumchatroom chatten kann.</span><span class="sxs-lookup"><span data-stu-id="16413-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="16413-132">13: true, wenn die Rolle beim Anzeigen von Knoten Sichtbarkeitsregeln umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="16413-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="16413-133">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="16413-133">**Key**</span></span>

|<span data-ttu-id="16413-134">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="16413-134">**Column**</span></span>|<span data-ttu-id="16413-135">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="16413-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16413-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="16413-136">rtypeID</span></span>  <br/> |<span data-ttu-id="16413-137">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="16413-137">Primary key.</span></span>  <br/> |
   

