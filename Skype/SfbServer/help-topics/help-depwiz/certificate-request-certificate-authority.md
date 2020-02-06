---
title: Zertifikatsanforderung (Zertifizierungsstelle)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite Zertifizierungsstelle auswählen werden zwei Optionen angezeigt:'
ms.openlocfilehash: b70daa9a4b9a212d770176b652e3ac70b7149c4e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823889"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="d1642-103">Zertifikatsanforderung (Zertifizierungsstelle)</span><span class="sxs-lookup"><span data-stu-id="d1642-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="d1642-104">Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite **Zertifizierungsstelle auswählen** werden zwei Optionen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d1642-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="d1642-105">Wählen Sie eine Zertifizierungsstelle aus der Liste mit den in Ihrer Umgebung erkannten Stellen aus.</span><span class="sxs-lookup"><span data-stu-id="d1642-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="d1642-106">Wählen Sie eine andere Zertifizierungsstelle aus.</span><span class="sxs-lookup"><span data-stu-id="d1642-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="d1642-107">Wenn Sie die erste Option auswählen, wird eine Dropdownliste angezeigt, die alle auf Windows Server basierenden Zertifizierungsstellen enthält, die in Ihrer Umgebung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d1642-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="d1642-108">Wählen Sie die Zertifizierungsstelle aus, die für Ihr Zertifikat geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d1642-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="d1642-109">Möglicherweise müssen Sie sich bei Ihrem Zertifizierungsstellenadministrator erkundigen, welche Zertifizierungsstelle Sie auswählen sollen.</span><span class="sxs-lookup"><span data-stu-id="d1642-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="d1642-p102">Bei Wahl der zweiten Option geben Sie den vollqualifizierten Domänennamen und die Zertifizierungsstelleninstanz der Zertifizierungsstelle ein, die Sie für das Zertifikat verwenden möchten. Diese Option kommt in Frage, wenn die gewünschte Zertifizierungsstelle keine Windows Server-basierte Zertifizierungsstelle ist, jedoch für Windows Server-basierte Zertifizierungsstellen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d1642-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1642-112">Für eine erfolgreiche Zertifikatsanforderung müssen Sie Mitglied der entsprechenden Gruppen sein.</span><span class="sxs-lookup"><span data-stu-id="d1642-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="d1642-113">In der Regel verfügen Zertifizierungsstellen über eine andere Berechtigungsanforderung als die Anforderungen für die Installation von Skype for Business Server auf Servern.</span><span class="sxs-lookup"><span data-stu-id="d1642-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="d1642-114">Informieren Sie sich über die Voraussetzungen für das Anfordern des Zertifikats bei Ihrem Zertifizierungsstellenadministrator.</span><span class="sxs-lookup"><span data-stu-id="d1642-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

