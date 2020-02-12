---
title: Abrufen des Integrationsprotokolls
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888804"
---
# <a name="get-integration-log"></a><span data-ttu-id="6c75e-104">Abrufen des Integrationsprotokolls</span><span class="sxs-lookup"><span data-stu-id="6c75e-104">Get Integration Log</span></span>
 
<span data-ttu-id="6c75e-105">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Integrations Protokollen, der Teil der Daten-API für das Dashboard für die Anrufqualität ist.</span><span class="sxs-lookup"><span data-stu-id="6c75e-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6c75e-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c75e-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6c75e-107">Der Vorgang "Integrationsprotokoll abrufen" ist Teil der Daten-API für das Anruf Qualitäts Dashboard</span><span class="sxs-lookup"><span data-stu-id="6c75e-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="6c75e-108">Abrufen des Integrationsprotokolls</span><span class="sxs-lookup"><span data-stu-id="6c75e-108">Get Integration Log</span></span>

<span data-ttu-id="6c75e-109">Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste der Protokolleinträge zurück, die die Aktivitäten in der QoE-Cube-Verarbeitung beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6c75e-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="6c75e-110">Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c75e-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="6c75e-111">Wenn diese Option deaktiviert ist, wird eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c75e-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="6c75e-112">Um diesen Vorgang zu aktivieren, müssen Administratoren die Web. config für die Host-Webanwendung der Daten-API konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c75e-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="6c75e-113">Methode</span><span class="sxs-lookup"><span data-stu-id="6c75e-113">Method</span></span>|<span data-ttu-id="6c75e-114">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="6c75e-114">**Request URI**</span></span>|<span data-ttu-id="6c75e-115">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="6c75e-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c75e-116">Erhalten</span><span class="sxs-lookup"><span data-stu-id="6c75e-116">GET</span></span>  <br/> |<span data-ttu-id="6c75e-117">https://\<-\>Portal/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="6c75e-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="6c75e-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6c75e-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6c75e-119">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="6c75e-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6c75e-120">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="6c75e-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6c75e-121">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="6c75e-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6c75e-122">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="6c75e-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6c75e-123">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="6c75e-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6c75e-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="6c75e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6c75e-125">**Antworttext** : Nachfolgend finden Sie eine Beispiel Struktur für Protokolleinträge.</span><span class="sxs-lookup"><span data-stu-id="6c75e-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


