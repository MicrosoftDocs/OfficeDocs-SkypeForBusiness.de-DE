---
title: Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: erfahren Sie mehr über den Benutzer Einstellungsdienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274485"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="09499-104">Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="09499-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="09499-105">**Zusammenfassung:** Erfahren Sie mehr über den Benutzer Einstellungsdienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist.</span><span class="sxs-lookup"><span data-stu-id="09499-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="09499-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09499-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="09499-107">Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="09499-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="09499-108">Benutzereinstellungsdienst</span><span class="sxs-lookup"><span data-stu-id="09499-108">User Settings Service</span></span>

<span data-ttu-id="09499-109">Benutzereinstellungen sind Schlüssel-Wert-Paare, mit denen Anwendungen Metadaten für verschiedene Zwecke speichern können, einschließlich der Anpassung von Anwendungsverhalten pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="09499-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="09499-110">Jeder Benutzer erhält einen Speicher für Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="09499-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="09499-111">Benutzereinstellungen können nur von den Besitzern hinzugefügt, geändert und entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="09499-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="09499-112">**Globale Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="09499-112">**Global Settings**</span></span>
  
<span data-ttu-id="09499-113">Bei globalen Einstellungen handelt es sich um die Benutzereinstellungen des Systembenutzers, und alle Benutzer verfügen über schreibgeschützten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="09499-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="09499-114">Globale Einstellungen sind Konstanten: Sie werden während der Erstellung des Repositorys erstellt, und Sie ändern sich nie.</span><span class="sxs-lookup"><span data-stu-id="09499-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="09499-115">Jeder Benutzer kann die globalen Einstellungen außer Kraft setzen, indem Benutzereinstellungen mit denselben Tasten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="09499-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="09499-116">Wenn die Anwendung die effektiven Benutzereinstellungen anfordert, gibt die API einen Satz globaler Einstellungen zurück, die mit den Benutzereinstellungen zusammengeführt wurden, wobei jede Benutzereinstellung die jeweilige globale Einstellung ersetzt, wenn die Schlüssel identisch sind.</span><span class="sxs-lookup"><span data-stu-id="09499-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="09499-117">Die API kann auch nur die Benutzereinstellungen zurückgeben, damit Anwendungen herausfinden können, welche Einstellungen überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="09499-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="09499-118">Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="09499-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="09499-119">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="09499-119">**Operation**</span></span>|<span data-ttu-id="09499-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="09499-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="09499-121">Abrufen der Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="09499-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="09499-122">Abrufen von Benutzereinstellungen gibt eine Liste der Einstellungen für einen bestimmten Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="09499-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="09499-123">Abrufen einer Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="09499-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="09499-124">Benutzereinstellung abrufen gibt eine Einstellung für einen einzelnen Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="09499-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

