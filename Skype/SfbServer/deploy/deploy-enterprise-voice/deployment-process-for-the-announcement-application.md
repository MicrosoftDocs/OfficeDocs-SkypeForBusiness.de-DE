---
title: Bereitstellungsprozess für die ansageanwendung in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Bereitstellungsprozess und Schritte für die ansageanwendung in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 96925df57a36373ee6f031b953f1933b3bac5681
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885599"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="a73ab-103">Bereitstellungsprozess für die ansageanwendung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a73ab-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="a73ab-104">Bereitstellungsprozess und Schritte für die ansageanwendung in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="a73ab-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a73ab-105">Der ankündigungsanwendung ist eine Enterprise-VoIP-Funktion, mit der Benutzer konfigurieren, was geschieht, wenn Anrufe an nicht zugewiesene Durchwahlnummern (Durchwahlnummern, die für Ihre Organisation gültig sind, aber nicht an eine Person oder ein Telefon zugewiesen werden).</span><span class="sxs-lookup"><span data-stu-id="a73ab-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="a73ab-106">Beispielsweise können Sie eine Nachricht wiedergegeben oder in ein anderes Ziel oder beides übertragen werden Anrufe bei nicht zugewiesenen Nummern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a73ab-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="a73ab-107">Der ankündigungsanwendung wird als Feature von Anwendung "Reaktionsgruppe" auf dem Front-End-Server oder Standard Edition-Server installiert, bei der Bereitstellung von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="a73ab-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a73ab-108">Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion und die Tabelle nicht zugewiesener Nummern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a73ab-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="a73ab-109">Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen der ankündigungsanwendung.</span><span class="sxs-lookup"><span data-stu-id="a73ab-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="a73ab-110">Sie müssen Enterprise-VoIP bereitstellen, vor dem Konfigurieren von Ansagen.</span><span class="sxs-lookup"><span data-stu-id="a73ab-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="a73ab-111">Von der Anwendung Ankündigung erforderlichen Komponenten werden installiert und bei der Bereitstellung von Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a73ab-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="a73ab-112">**Bereitstellungsprozess für Ansagen**</span><span class="sxs-lookup"><span data-stu-id="a73ab-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="a73ab-113">**Phase**</span><span class="sxs-lookup"><span data-stu-id="a73ab-113">**Phase**</span></span>|<span data-ttu-id="a73ab-114">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="a73ab-114">**Steps**</span></span>|<span data-ttu-id="a73ab-115">**Rollen**</span><span class="sxs-lookup"><span data-stu-id="a73ab-115">**Roles**</span></span>|<span data-ttu-id="a73ab-116">**Bereitstellungsdokumentation**</span><span class="sxs-lookup"><span data-stu-id="a73ab-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a73ab-117">Konfigurieren von Ansageeinstellungen</span><span class="sxs-lookup"><span data-stu-id="a73ab-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="a73ab-118">Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS)</span><span class="sxs-lookup"><span data-stu-id="a73ab-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="a73ab-119">Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu.</span><span class="sxs-lookup"><span data-stu-id="a73ab-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="a73ab-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a73ab-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="a73ab-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a73ab-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="a73ab-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a73ab-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="a73ab-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a73ab-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="a73ab-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="a73ab-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="a73ab-125">Erstellen oder Löschen einer Ankündigung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a73ab-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="a73ab-126">Erstellen Sie oder ändern Sie einen Bereichs nicht zugewiesenen Nummern in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a73ab-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="a73ab-127">Überprüfen Ihrer Bereitstellung von Ansagen</span><span class="sxs-lookup"><span data-stu-id="a73ab-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="a73ab-128">Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.</span><span class="sxs-lookup"><span data-stu-id="a73ab-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="a73ab-129">(Optional) Überprüfen der ansagebereitstellung in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a73ab-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

