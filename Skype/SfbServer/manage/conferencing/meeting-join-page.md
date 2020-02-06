---
title: Konfigurieren der Seite "Besprechungsteilnahme" in Skype for Business Server
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
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Seite "Besprechungsteilnahme" in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818516"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="04e28-103">Konfigurieren der Seite "Besprechungsteilnahme" in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="04e28-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="04e28-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Seite "Besprechungsteilnahme" in Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="04e28-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="04e28-105">Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", ob ein Skype for Business-Client bereits auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="04e28-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="04e28-106">Wenn ein Client bereits installiert ist, wird der Client geöffnet und der Besprechung beitreten.</span><span class="sxs-lookup"><span data-stu-id="04e28-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="04e28-107">Wenn ein Client nicht installiert ist, wird standardmäßig der Skype for Business-Client geöffnet.</span><span class="sxs-lookup"><span data-stu-id="04e28-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="04e28-108">Konfigurieren der Seite für den Besprechungsbeitritt</span><span class="sxs-lookup"><span data-stu-id="04e28-108">Configure the meeting join page</span></span>

<span data-ttu-id="04e28-109">Sie können das Verhalten der Seite "Besprechungsteilnahme" ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit anderen Versionen des Clients gestatten möchten.</span><span class="sxs-lookup"><span data-stu-id="04e28-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="04e28-110">Diese Konfigurationsoptionen wurden aus der Skype for Business Server-Systemsteuerung entfernt, aber Sie werden mithilfe des Cmdlets "festlegen-CsWebServiceConfiguration" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="04e28-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="04e28-111">**Seitensatz "Besprechungsteilnahme" – CsWebServiceConfiguration-Parameter**</span><span class="sxs-lookup"><span data-stu-id="04e28-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="04e28-112">**Satz-CsWebServiceConfiguration-Parameter**</span><span class="sxs-lookup"><span data-stu-id="04e28-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="04e28-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="04e28-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04e28-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="04e28-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="04e28-115">Dieser Parameter wurde für die Verwendung mit der lokalen Version von Skype for Business Server als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="04e28-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="04e28-116">Wenn die Einstellung auf "true" festgelegt ist, können Benutzer, die mit einer anderen Clientanwendung als Skype for Business an einer Besprechung teilnehmen, die Möglichkeit erhalten, an der Besprechung teilzunehmen, indem Sie Ihre aktuelle Clientanwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="04e28-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="04e28-117">Der Standardwert lautet "False".</span><span class="sxs-lookup"><span data-stu-id="04e28-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="04e28-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="04e28-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="04e28-119">Dieser Parameter wurde für die Verwendung mit der lokalen Version von Skype for Business Server als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="04e28-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="04e28-120">Wenn diese Option auf "true" festgelegt ist, werden die Alternativen für den Beitritt zu einer Onlinekonferenz automatisch erweitert und Benutzern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04e28-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="04e28-121">Wenn auf "false" (der Standardwert) festgelegt ist, stehen diese Optionen zur Verfügung, aber der Benutzer muss die Liste der Optionen für sich selbst anzeigen.</span><span class="sxs-lookup"><span data-stu-id="04e28-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

