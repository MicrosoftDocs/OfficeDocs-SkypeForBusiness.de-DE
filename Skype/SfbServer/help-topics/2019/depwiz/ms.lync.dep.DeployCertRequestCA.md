---
title: Zertifikatsanforderung (Zertifizierungsstelle)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite Zertifizierungsstelle auswählen werden zwei Optionen angezeigt:'
ms.openlocfilehash: be47dba48d448f73cf43890921fd7531a336d124
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893763"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="2de57-103">Zertifikatsanforderung (Zertifizierungsstelle)</span><span class="sxs-lookup"><span data-stu-id="2de57-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="2de57-104">Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite **Zertifizierungsstelle auswählen** werden zwei Optionen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="2de57-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="2de57-105">Wählen Sie eine Zertifizierungsstelle aus der Liste mit den in Ihrer Umgebung erkannten Stellen aus.</span><span class="sxs-lookup"><span data-stu-id="2de57-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="2de57-106">Wählen Sie eine andere Zertifizierungsstelle aus.</span><span class="sxs-lookup"><span data-stu-id="2de57-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="2de57-107">Wenn Sie die erste Option auswählen, sehen Sie ein Dropdown-Listenfeld, das alle Windows Server-basierten Zertifizierungsstellen enthält, die in Ihrer Umgebung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="2de57-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="2de57-108">Wählen Sie die Zertifizierungsstelle, die für das Zertifikat geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="2de57-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="2de57-109">Möglicherweise müssen den Zertifizierungsstellen-Administrator wissen, welche Zertifizierungsstelle auswählen zu konsultieren.</span><span class="sxs-lookup"><span data-stu-id="2de57-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="2de57-p102">Bei Wahl der zweiten Option geben Sie den vollqualifizierten Domänennamen und die Zertifizierungsstelleninstanz der Zertifizierungsstelle ein, die Sie für das Zertifikat verwenden möchten. Diese Option kommt in Frage, wenn die gewünschte Zertifizierungsstelle keine Windows Server-basierte Zertifizierungsstelle ist, jedoch für Windows Server-basierte Zertifizierungsstellen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2de57-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2de57-112">Für eine erfolgreiche Zertifikatsanforderung müssen Sie Mitglied der entsprechenden Gruppen sein.</span><span class="sxs-lookup"><span data-stu-id="2de57-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="2de57-113">Zertifizierungsstellen verfügen normalerweise über eine andere Berechtigung Anforderung die Anforderungen für die Installation von Skype für Business Server auf Servern.</span><span class="sxs-lookup"><span data-stu-id="2de57-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="2de57-114">Informieren Sie sich über die Voraussetzungen für das Anfordern des Zertifikats bei Ihrem Zertifizierungsstellenadministrator.</span><span class="sxs-lookup"><span data-stu-id="2de57-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

