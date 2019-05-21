---
title: Tabelle "Dialogfelder" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Die Tabelle Dialogfelder ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296322"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="588fa-103">Tabelle "Dialogfelder" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="588fa-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="588fa-104">Die Tabelle Dialogfelder ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="588fa-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="588fa-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="588fa-105">**Column**</span></span>|<span data-ttu-id="588fa-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="588fa-106">**Data Type**</span></span>|<span data-ttu-id="588fa-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="588fa-107">**Key/Index**</span></span>|<span data-ttu-id="588fa-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="588fa-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="588fa-109">**SessionID**</span><span class="sxs-lookup"><span data-stu-id="588fa-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="588fa-110">datetime</span><span class="sxs-lookup"><span data-stu-id="588fa-110">datetime</span></span>  <br/> |<span data-ttu-id="588fa-111">Primary</span><span class="sxs-lookup"><span data-stu-id="588fa-111">Primary</span></span>  <br/> |<span data-ttu-id="588fa-112">Uhrzeit der Sitzungsanforderung; wird in Verbindung mit SessionIDSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="588fa-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="588fa-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="588fa-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="588fa-114">int</span><span class="sxs-lookup"><span data-stu-id="588fa-114">int</span></span>  <br/> |<span data-ttu-id="588fa-115">Primary</span><span class="sxs-lookup"><span data-stu-id="588fa-115">Primary</span></span>  <br/> |<span data-ttu-id="588fa-116">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="588fa-116">ID number to identify the session.</span></span> <span data-ttu-id="588fa-117">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="588fa-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="588fa-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="588fa-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="588fa-119">int</span><span class="sxs-lookup"><span data-stu-id="588fa-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="588fa-120">Prüfsumme der externen-Nr.</span><span class="sxs-lookup"><span data-stu-id="588fa-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="588fa-121">Dieses Feld wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="588fa-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="588fa-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="588fa-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="588fa-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="588fa-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="588fa-124">SIP-Dialogfeld-ID, als Binärdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="588fa-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="588fa-125">Das Format der Binärdatei lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="588fa-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="588fa-126">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="588fa-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="588fa-127">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="588fa-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

