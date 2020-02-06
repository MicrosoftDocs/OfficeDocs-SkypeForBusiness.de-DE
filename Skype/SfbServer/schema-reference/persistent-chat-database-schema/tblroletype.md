---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812903"
---
# <a name="tblroletype"></a><span data-ttu-id="379bb-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="379bb-103">tblRoleType</span></span>
 
<span data-ttu-id="379bb-104">tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.</span><span class="sxs-lookup"><span data-stu-id="379bb-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="379bb-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="379bb-105">**Columns**</span></span>

|<span data-ttu-id="379bb-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="379bb-106">**Column**</span></span>|<span data-ttu-id="379bb-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="379bb-107">**Type**</span></span>|<span data-ttu-id="379bb-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="379bb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="379bb-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="379bb-109">rtypeID</span></span>  <br/> |<span data-ttu-id="379bb-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="379bb-110">int, not null</span></span>  <br/> |<span data-ttu-id="379bb-111">ID des Rollentyps.</span><span class="sxs-lookup"><span data-stu-id="379bb-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="379bb-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="379bb-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="379bb-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="379bb-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="379bb-114">Beschreibung des Rollentyps.</span><span class="sxs-lookup"><span data-stu-id="379bb-114">Role type description.</span></span> <span data-ttu-id="379bb-115">Es gibt vier verfügbare Rollen:</span><span class="sxs-lookup"><span data-stu-id="379bb-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="379bb-116">Mitglied: Chatroom-Mitglied</span><span class="sxs-lookup"><span data-stu-id="379bb-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="379bb-117">Manager: Chat Room Manager</span><span class="sxs-lookup"><span data-stu-id="379bb-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="379bb-118">Geäußert: Referent für einen Chatroom für Auditorium</span><span class="sxs-lookup"><span data-stu-id="379bb-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="379bb-119">Creator: kann Chatrooms erstellen</span><span class="sxs-lookup"><span data-stu-id="379bb-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="379bb-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="379bb-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="379bb-121">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="379bb-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="379bb-122">Der Berechtigungssatz für die Rolle.</span><span class="sxs-lookup"><span data-stu-id="379bb-122">Permission set for the role.</span></span> <span data-ttu-id="379bb-123">Die verwendeten Bits sind:</span><span class="sxs-lookup"><span data-stu-id="379bb-123">The used bits are:</span></span> <br/>  <span data-ttu-id="379bb-124">2: true, wenn die Rolle Knoten verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="379bb-125">4: true, wenn die Rolle untergeordnete Knoten erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="379bb-126">7: true, wenn die Rolle einem Chatroom (oder Chatrooms einer Kategorie) beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="379bb-127">8: true, wenn die Rolle in einem Chatroom (oder in Chatrooms einer Kategorie) chatten kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="379bb-128">10: true, wenn die Rolle das Chat-Protokoll lesen kann, selbst wenn Sie nicht zu einem Chatroom gehört.</span><span class="sxs-lookup"><span data-stu-id="379bb-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="379bb-129">11: true, wenn die Rolle den Chatroom sehen kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="379bb-130">(Dies wird durch Faktoren wie Bereich und Sichtbarkeit weiter verfeinert.)</span><span class="sxs-lookup"><span data-stu-id="379bb-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="379bb-131">12: true, wenn die Rolle in einem Auditorium-Chatroom chatten kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="379bb-132">13: true, wenn die Rolle Sichtbarkeitsregeln beim Anzeigen von Knoten umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="379bb-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="379bb-133">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="379bb-133">**Key**</span></span>

|<span data-ttu-id="379bb-134">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="379bb-134">**Column**</span></span>|<span data-ttu-id="379bb-135">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="379bb-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="379bb-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="379bb-136">rtypeID</span></span>  <br/> |<span data-ttu-id="379bb-137">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="379bb-137">Primary key.</span></span>  <br/> |
   

