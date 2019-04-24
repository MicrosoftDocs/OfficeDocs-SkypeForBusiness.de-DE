---
title: ClientVersions-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Die ClientVersions-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Clienttypen gespeichert, und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Clientversion.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213382"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d1dba-104">ClientVersions-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d1dba-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1dba-105">Die ClientVersions-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Clienttypen gespeichert, und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="d1dba-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d1dba-106">Jeder Datensatz in der Tabelle steht für eine Clientversion.</span><span class="sxs-lookup"><span data-stu-id="d1dba-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="d1dba-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d1dba-107">**Column**</span></span>|<span data-ttu-id="d1dba-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d1dba-108">**Data Type**</span></span>|<span data-ttu-id="d1dba-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d1dba-109">**Key/Index**</span></span>|<span data-ttu-id="d1dba-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d1dba-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1dba-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="d1dba-111">**VersionId**</span></span> <br/> |<span data-ttu-id="d1dba-112">**int**</span><span class="sxs-lookup"><span data-stu-id="d1dba-112">**int**</span></span> <br/> |<span data-ttu-id="d1dba-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d1dba-113">Primary</span></span>  <br/> |<span data-ttu-id="d1dba-114">Eindeutige Zahl, identifiziert dieser Clienttyp und Version.</span><span class="sxs-lookup"><span data-stu-id="d1dba-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="d1dba-115">**Version**</span><span class="sxs-lookup"><span data-stu-id="d1dba-115">**Version**</span></span> <br/> |<span data-ttu-id="d1dba-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="d1dba-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="d1dba-117">Versionsname</span><span class="sxs-lookup"><span data-stu-id="d1dba-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="d1dba-118">**Clienttyp**</span><span class="sxs-lookup"><span data-stu-id="d1dba-118">**ClientType**</span></span> <br/> |<span data-ttu-id="d1dba-119">int</span><span class="sxs-lookup"><span data-stu-id="d1dba-119">int</span></span>  <br/> ||<span data-ttu-id="d1dba-120">Gibt den Typ des Clients, die in der Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1dba-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="d1dba-121">[UserAgentDef-Tabelle](useragentdef.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="d1dba-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="d1dba-122">Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d1dba-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

