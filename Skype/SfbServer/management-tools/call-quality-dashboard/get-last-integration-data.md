---
title: Abrufen der letzten Integrationsdaten
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "letzte Integrationsdaten abrufen", der Teil der Daten-API für die Anruf Qualitätssteuerung ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: a4b455a543dd77f0edce223f43d64fe5c03e4bcb
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888794"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="83b21-104">Abrufen der letzten Integrationsdaten</span><span class="sxs-lookup"><span data-stu-id="83b21-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="83b21-105">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "letzte Integrationsdaten abrufen", der Teil der Daten-API für die Anruf Qualitätssteuerung ist.</span><span class="sxs-lookup"><span data-stu-id="83b21-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="83b21-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="83b21-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="83b21-107">Der Vorgang zum Abrufen der letzten Integrationsdaten ist Teil der Daten-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="83b21-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="83b21-108">Abrufen der letzten Integrationsdaten</span><span class="sxs-lookup"><span data-stu-id="83b21-108">Get Last Integration Data</span></span>

<span data-ttu-id="83b21-109">Abrufen des letzten Integrationsdaten Vorgangs gibt die Liste der letzten 5 Erfolge/Fehler bei der Archivierung und der Cube-Verarbeitung zurück.</span><span class="sxs-lookup"><span data-stu-id="83b21-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="83b21-110">Dieses Feature ist standardmäßig deaktiviert und muss durch Konfigurieren der Daten-API aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="83b21-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="83b21-111">**Methode**</span><span class="sxs-lookup"><span data-stu-id="83b21-111">**Method**</span></span>|<span data-ttu-id="83b21-112">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="83b21-112">**Request URI**</span></span>|<span data-ttu-id="83b21-113">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="83b21-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83b21-114">Erhalten</span><span class="sxs-lookup"><span data-stu-id="83b21-114">GET</span></span>  <br/> |<span data-ttu-id="83b21-115">https://\<-\>Portal/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="83b21-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="83b21-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="83b21-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="83b21-117">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="83b21-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="83b21-118">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="83b21-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="83b21-119">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="83b21-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="83b21-120">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="83b21-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="83b21-121">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="83b21-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="83b21-122">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="83b21-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="83b21-123">**Antworttext** : unten befindet sich ein Beispiel für einen Protokollstatus.</span><span class="sxs-lookup"><span data-stu-id="83b21-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
