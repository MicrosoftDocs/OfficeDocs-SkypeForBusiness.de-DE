---
title: Dialogs-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs-Tabelle ist eine unterstützende Tabelle, die Informationen über DialogIDs für Peer-zu-Peer-Sitzungen gespeichert.
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1cdc1-103">Dialogs-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1cdc1-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1cdc1-104">Dialogs-Tabelle ist eine unterstützende Tabelle, die Informationen über DialogIDs für Peer-zu-Peer-Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="1cdc1-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-105">**Column**</span></span>|<span data-ttu-id="1cdc1-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-106">**Data Type**</span></span>|<span data-ttu-id="1cdc1-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-107">**Key/Index**</span></span>|<span data-ttu-id="1cdc1-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cdc1-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="1cdc1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1cdc1-110">datetime</span></span>  <br/> |<span data-ttu-id="1cdc1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1cdc1-111">Primary</span></span>  <br/> |<span data-ttu-id="1cdc1-112">Zeitpunkt der sitzungsanforderung; zusammen mit SessionIDSeq verwendet zur eindeutigen Identifizierung eine Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="1cdc1-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="1cdc1-114">int</span><span class="sxs-lookup"><span data-stu-id="1cdc1-114">int</span></span>  <br/> |<span data-ttu-id="1cdc1-115">Primary</span><span class="sxs-lookup"><span data-stu-id="1cdc1-115">Primary</span></span>  <br/> |<span data-ttu-id="1cdc1-116">ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-116">ID number to identify the session.</span></span> <span data-ttu-id="1cdc1-117">In Verbindung mit SessionIDTime verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="1cdc1-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="1cdc1-119">int</span><span class="sxs-lookup"><span data-stu-id="1cdc1-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="1cdc1-120">Prüfsumme der ExternalID.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="1cdc1-121">Dieses Feld wird verwendet, um die Datenbank Suchvorgänge zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="1cdc1-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="1cdc1-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="1cdc1-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="1cdc1-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="1cdc1-124">SIP-Dialog-ID als binäre gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="1cdc1-125">Das Format der Binärdatei ist:</span><span class="sxs-lookup"><span data-stu-id="1cdc1-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="1cdc1-126">Dialogfeld; aus Tag; -tag</span><span class="sxs-lookup"><span data-stu-id="1cdc1-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="1cdc1-127">Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="1cdc1-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

