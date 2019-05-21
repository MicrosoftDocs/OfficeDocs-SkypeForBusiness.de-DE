---
title: Abrufen des Integrationsprotokolls
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 58be983ff3b282c94a4b42619a6c37c6270afcb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274758"
---
# <a name="get-integration-log"></a><span data-ttu-id="ff661-104">Abrufen des Integrationsprotokolls</span><span class="sxs-lookup"><span data-stu-id="ff661-104">Get Integration Log</span></span>
 
<span data-ttu-id="ff661-105">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Integrations Protokollen, der Teil der Daten-API für das Dashboard für die Anrufqualität ist.</span><span class="sxs-lookup"><span data-stu-id="ff661-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="ff661-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ff661-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ff661-107">Der Vorgang "Integrationsprotokoll abrufen" ist Teil der Daten-API für das Anruf Qualitäts Dashboard</span><span class="sxs-lookup"><span data-stu-id="ff661-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="ff661-108">Abrufen des Integrationsprotokolls</span><span class="sxs-lookup"><span data-stu-id="ff661-108">Get Integration Log</span></span>

<span data-ttu-id="ff661-109">Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste der Protokolleinträge zurück, die die Aktivitäten in der QoE-Cube-Verarbeitung beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ff661-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="ff661-110">Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ff661-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="ff661-111">Wenn diese Option deaktiviert ist, wird eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ff661-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="ff661-112">Um diesen Vorgang zu aktivieren, müssen Administratoren die Web. config für die Host-Webanwendung der Daten-API konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ff661-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="ff661-113">Methode</span><span class="sxs-lookup"><span data-stu-id="ff661-113">Method</span></span>|<span data-ttu-id="ff661-114">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="ff661-114">**Request URI**</span></span>|<span data-ttu-id="ff661-115">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="ff661-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff661-116">Erhalten</span><span class="sxs-lookup"><span data-stu-id="ff661-116">GET</span></span>  <br/> |<span data-ttu-id="ff661-117">https://\<-\>Portal/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="ff661-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="ff661-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ff661-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ff661-119">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="ff661-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ff661-120">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="ff661-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ff661-121">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="ff661-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ff661-122">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="ff661-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ff661-123">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="ff661-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ff661-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="ff661-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ff661-125">**Antworttext** : Nachfolgend finden Sie eine Beispiel Struktur für Protokolleinträge.</span><span class="sxs-lookup"><span data-stu-id="ff661-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


