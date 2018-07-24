---
title: Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Zusammenfassung: Informationen zum Konfigurieren der Besprechung teilnehmen Seite in Skype für Business Server.'
ms.openlocfilehash: 7574dee341e0226a6a6e2ee8c77cdfb2353beb5a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977614"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="922ad-103">Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="922ad-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="922ad-104">**Zusammenfassung:** Informationen zum Konfigurieren der Besprechung teilnehmen Seite in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="922ad-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="922ad-105">Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt, ob ein Skype für Business-Client bereits auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="922ad-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="922ad-106">Wenn ein Client bereits installiert ist, wird der Client wird geöffnet und der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="922ad-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="922ad-107">Wenn ein Client nicht installiert ist, öffnet standardmäßig die Skype für Business Client.</span><span class="sxs-lookup"><span data-stu-id="922ad-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="922ad-108">Konfigurieren die Besprechung teilnehmen-Seite</span><span class="sxs-lookup"><span data-stu-id="922ad-108">Configure the meeting join page</span></span>

<span data-ttu-id="922ad-109">Sie können das Verhalten der Teilnahme an einer Besprechung ändern Seite, wenn Sie Benutzer zur Teilnahme an Besprechungen mit anderen Versionen des Clients zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="922ad-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="922ad-110">Diese Konfigurationsoptionen aus der Skype Business Server-Systemsteuerung entfernt wurden, aber Sie mit dem Cmdlet "Set-cswebserviceconfiguration" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="922ad-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="922ad-111">**Besprechung teilnehmen Seite Set-CsWebServiceConfiguration-Parameter**</span><span class="sxs-lookup"><span data-stu-id="922ad-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="922ad-112">**Set-CsWebServiceConfiguration-parameter**</span><span class="sxs-lookup"><span data-stu-id="922ad-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="922ad-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="922ad-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="922ad-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="922ad-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="922ad-115">Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype für Business Server veraltet.</span><span class="sxs-lookup"><span data-stu-id="922ad-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="922ad-116">Bei auf True festgelegt, teilnehmen an einer Besprechung mithilfe einer anderen Clientanwendung als Benutzer Skype für Unternehmen Teilnahme an der Besprechung mithilfe ihrer aktuellen Clientanwendung Gelegenheit sein wird.</span><span class="sxs-lookup"><span data-stu-id="922ad-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="922ad-117">Der Standardwert ist "False".</span><span class="sxs-lookup"><span data-stu-id="922ad-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="922ad-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="922ad-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="922ad-119">Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype für Business Server veraltet.</span><span class="sxs-lookup"><span data-stu-id="922ad-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="922ad-120">Wenn Sie True festlegen, alternative Optionen für die Teilnahme an einer Konferenz online automatisch erweitert und anschließend den Benutzern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="922ad-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="922ad-121">Wenn auf False (Standardwert) gesetzt, diese Optionen zur Verfügung, aber der Benutzer die Liste der Optionen für sich selbst anzuzeigen muss.</span><span class="sxs-lookup"><span data-stu-id="922ad-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

