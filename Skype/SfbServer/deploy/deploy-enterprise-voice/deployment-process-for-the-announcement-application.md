---
title: Bereitstellungsprozess für die Ankündigungs Anwendung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Bereitstellungsprozess und Schritte zur Ankündigungs Anwendung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275608"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="d874f-103">Bereitstellungsprozess für die Ankündigungs Anwendung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d874f-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="d874f-104">Bereitstellungsprozess und Schritte zur Ankündigungs Anwendung in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d874f-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d874f-105">Bei der Ankündigungs Anwendung handelt es sich um ein Enterprise-VoIP-Feature, mit dem Sie konfigurieren können, was mit Anrufen zu nicht zugewiesenen Erweiterungen geschieht (Erweiterungen, die für Ihre Organisation gültig sind, aber keiner Person oder einem Telefon zugeordnet sind).</span><span class="sxs-lookup"><span data-stu-id="d874f-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="d874f-106">So können Sie beispielsweise Anrufe an nicht zugewiesene Nummern konfigurieren, um eine Nachricht wiederzugeben oder an ein anderes Ziel oder beides übertragen zu werden.</span><span class="sxs-lookup"><span data-stu-id="d874f-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="d874f-107">Die Ankündigungs Anwendung wird auf dem Front-End-Server oder Standard Edition-Server als Feature der reaktionsgruppenanwendung installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d874f-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d874f-108">Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion und die Tabelle nicht zugewiesener Nummern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d874f-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="d874f-109">Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen der Ankündigungs Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d874f-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="d874f-110">Sie müssen Enterprise-VoIP bereitstellen, bevor Sie Ankündigungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d874f-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="d874f-111">Die von der Ankündigungs Anwendung benötigten Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d874f-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="d874f-112">**Bereitstellungsprozess für Ansagen**</span><span class="sxs-lookup"><span data-stu-id="d874f-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="d874f-113">**Phase**</span><span class="sxs-lookup"><span data-stu-id="d874f-113">**Phase**</span></span>|<span data-ttu-id="d874f-114">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="d874f-114">**Steps**</span></span>|<span data-ttu-id="d874f-115">**Rollen**</span><span class="sxs-lookup"><span data-stu-id="d874f-115">**Roles**</span></span>|<span data-ttu-id="d874f-116">**Bereitstellungsdokumentation**</span><span class="sxs-lookup"><span data-stu-id="d874f-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d874f-117">Konfigurieren von Ansageeinstellungen</span><span class="sxs-lookup"><span data-stu-id="d874f-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="d874f-118">Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS)</span><span class="sxs-lookup"><span data-stu-id="d874f-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="d874f-119">Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu.</span><span class="sxs-lookup"><span data-stu-id="d874f-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="d874f-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d874f-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="d874f-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d874f-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="d874f-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d874f-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="d874f-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d874f-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="d874f-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="d874f-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="d874f-125">Erstellen oder Löschen einer Ankündigung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d874f-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="d874f-126">Erstellen oder Ändern eines nicht zugewiesenen Nummernbereichs in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d874f-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="d874f-127">Überprüfen Ihrer Bereitstellung von Ansagen</span><span class="sxs-lookup"><span data-stu-id="d874f-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="d874f-128">Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.</span><span class="sxs-lookup"><span data-stu-id="d874f-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="d874f-129">Optional Überprüfen der Ankündigungs Bereitstellung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d874f-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

