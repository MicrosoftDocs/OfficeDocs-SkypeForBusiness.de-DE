---
title: Abrufen von Integrationsdaten der letzten
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Zusammenfassung: Informationen Sie zum Vorgang letzten Integrationsdaten abrufen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: b2e759766987b6ee52795845ee55546920181807
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035595"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="afa1f-104">Abrufen von Integrationsdaten der letzten</span><span class="sxs-lookup"><span data-stu-id="afa1f-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="afa1f-105">**Zusammenfassung:** Informationen Sie zu den letzten Integrationsdaten abrufen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="afa1f-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="afa1f-106">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="afa1f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="afa1f-107">Der letzte Integrationsdaten abrufen-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="afa1f-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="afa1f-108">Abrufen von Integrationsdaten der letzten</span><span class="sxs-lookup"><span data-stu-id="afa1f-108">Get Last Integration Data</span></span>

<span data-ttu-id="afa1f-109">Rufen Sie zuletzt Integrationsdaten Vorgang gibt die Liste der letzten 5 Erfolg/Fehlschlag der Archivierung und Verarbeiten des Cubes.</span><span class="sxs-lookup"><span data-stu-id="afa1f-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="afa1f-110">Dieses Feature ist standardmäßig deaktiviert und muss aktiviert werden, um die Daten-API konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="afa1f-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="afa1f-111">**Methode**</span><span class="sxs-lookup"><span data-stu-id="afa1f-111">**Method**</span></span>|<span data-ttu-id="afa1f-112">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="afa1f-112">**Request URI**</span></span>|<span data-ttu-id="afa1f-113">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="afa1f-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afa1f-114">Erhalten</span><span class="sxs-lookup"><span data-stu-id="afa1f-114">GET</span></span>  <br/> |<span data-ttu-id="afa1f-115">https://\<Portal\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="afa1f-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="afa1f-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="afa1f-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="afa1f-117">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="afa1f-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="afa1f-118">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="afa1f-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="afa1f-119">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="afa1f-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="afa1f-120">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="afa1f-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="afa1f-121">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="afa1f-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="afa1f-122">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="afa1f-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="afa1f-123">**Antworttext** - ist im folgenden Beispiel Protokollierungsstatus.</span><span class="sxs-lookup"><span data-stu-id="afa1f-123">**Response Body** - Below is a sample log status.</span></span>
  
```
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