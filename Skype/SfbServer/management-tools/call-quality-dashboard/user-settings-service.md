---
title: Einstellungen Benutzerdienst für Anruf Qualitätsdashboard (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: Erfahren Sie mehr über die Benutzerdienst Einstellungen, die Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 9e72d051699269b404d72e77ca00923b8ca240a3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293763"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="2d92e-104">Einstellungen Benutzerdienst für Anruf Qualitätsdashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="2d92e-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="2d92e-105">**Zusammenfassung:** Informationen Sie zu den Benutzerdienst Einstellungen, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="2d92e-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="2d92e-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2d92e-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2d92e-107">Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2d92e-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="2d92e-108">Benutzerdienst-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="2d92e-108">User Settings Service</span></span>

<span data-ttu-id="2d92e-109">Benutzereinstellungen sind Schlüssel-Wert-Paaren, die Anwendungen verwenden können, um Metadaten für verschiedene Zwecke einschließlich Anpassung der Anwendung Verhaltensweisen jeden Benutzer einzeln zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d92e-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="2d92e-110">Jeder Benutzer erhält einen Speicher für benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2d92e-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="2d92e-111">Nur die Besitzer können hinzufügen, ändern und Entfernen von benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2d92e-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="2d92e-112">**Globale Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="2d92e-112">**Global Settings**</span></span>
  
<span data-ttu-id="2d92e-113">Globale Einstellungen werden die benutzereinstellungen Besitz des Systembenutzers, und alle Benutzer haben schreibgeschützten Zugriff auf diese.</span><span class="sxs-lookup"><span data-stu-id="2d92e-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="2d92e-114">Globale Einstellungen werden Konstanten: werden während der Erstellung Repository erstellt, und sie nie ändern.</span><span class="sxs-lookup"><span data-stu-id="2d92e-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="2d92e-115">Jeder Benutzer überschreibbar globale Einstellungen, indem Sie benutzereinstellungen mit demselben Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d92e-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="2d92e-116">Bei der Anwendung die benutzereinstellungen für eine effektive anfordert, gibt die API einen Satz von globalen Einstellungen mit den benutzereinstellungen für mit jedem benutzereinstellung Ablösen der jeweiligen globale Einstellung, wenn Schlüssel identisch sind zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="2d92e-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="2d92e-117">Die API kann auch nur die für die Benutzer zurückgegeben, damit Sie ermitteln können, welche Einstellungen außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2d92e-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="2d92e-118">In der folgenden Tabelle sind die REST-Vorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="2d92e-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="2d92e-119">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="2d92e-119">**Operation**</span></span>|<span data-ttu-id="2d92e-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2d92e-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2d92e-121">Abrufen von Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="2d92e-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="2d92e-122">Get-Benutzereinstellungen gibt eine Liste der Einstellungen für einen angegebenen Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="2d92e-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="2d92e-123">Get-Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="2d92e-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="2d92e-124">Rufen Sie die Einstellung für Benutzer gibt eine Einstellung für die einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2d92e-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

