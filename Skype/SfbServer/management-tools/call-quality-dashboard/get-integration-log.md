---
title: Integration Protokoll abrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: Informationen Sie zum Vorgang Integration Protokoll abrufen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 6408d0a773ee00854f82c4430e4402e79db23fa6
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035560"
---
# <a name="get-integration-log"></a><span data-ttu-id="e611c-104">Integration Protokoll abrufen</span><span class="sxs-lookup"><span data-stu-id="e611c-104">Get Integration Log</span></span>
 
<span data-ttu-id="e611c-105">**Zusammenfassung:** Informationen Sie zu den Vorgang Integration Protokoll erhalten möchten, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="e611c-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="e611c-106">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="e611c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e611c-107">Die erste Integration Log-Operation ist Teil der Daten-API für die Qualitätsdashboard aufrufen</span><span class="sxs-lookup"><span data-stu-id="e611c-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="e611c-108">Integration Protokoll abrufen</span><span class="sxs-lookup"><span data-stu-id="e611c-108">Get Integration Log</span></span>

<span data-ttu-id="e611c-109">Möchten Sie Integration Protokoll Operation gibt eine Liste der Protokolleinträge, beschreibt die Aktivitäten in QoE-Cube zurück, Verarbeitung erhalten.</span><span class="sxs-lookup"><span data-stu-id="e611c-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="e611c-110">Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e611c-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="e611c-111">Wenn deaktiviert, wird eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e611c-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="e611c-112">Um diesen Vorgang zu aktivieren, müssen die Administratoren die Web.config-Datei für Daten-API-Host-Web-Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e611c-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="e611c-113">Methode</span><span class="sxs-lookup"><span data-stu-id="e611c-113">Method</span></span>|<span data-ttu-id="e611c-114">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="e611c-114">**Request URI**</span></span>|<span data-ttu-id="e611c-115">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="e611c-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e611c-116">Erhalten</span><span class="sxs-lookup"><span data-stu-id="e611c-116">GET</span></span>  <br/> |<span data-ttu-id="e611c-117">https://\<Portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="e611c-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="e611c-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e611c-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e611c-119">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="e611c-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e611c-120">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="e611c-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e611c-121">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="e611c-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e611c-122">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="e611c-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e611c-123">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="e611c-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="e611c-124">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="e611c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e611c-125">**Antworttext** – Es folgt eine Beispielstruktur der Protokolleinträge.</span><span class="sxs-lookup"><span data-stu-id="e611c-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


