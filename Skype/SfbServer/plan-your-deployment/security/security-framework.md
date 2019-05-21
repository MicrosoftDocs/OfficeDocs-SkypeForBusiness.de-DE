---
title: Sicherheitsframework für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Wenn Sie wissen möchten, wie diese Elemente zusammenarbeiten, ist es wichtig, fundierte Entscheidungen über die Sicherung ihrer speziellen Skype for Business Server-Bereitstellung zu treffen.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296875"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="fe9a7-104">Sicherheitsframework für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="fe9a7-105">Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="fe9a7-106">Wenn Sie wissen möchten, wie diese Elemente zusammenarbeiten, ist es wichtig, fundierte Entscheidungen über die Sicherung ihrer speziellen Skype for Business Server-Bereitstellung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="fe9a7-107">Es handelt sich um die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="fe9a7-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="fe9a7-108">Active Directory-Domänendienste (AD DS) bietet ein einzelnes vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="fe9a7-109">Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="fe9a7-110">Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="fe9a7-p103">Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="fe9a7-113">Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="fe9a7-114">Windows PowerShell bietet Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass Benutzer keine einfachen oder unwissentlichen Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="fe9a7-115">Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um sicherzustellen, dass ein sicheres Fundament für Skype for Business Server besteht.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fe9a7-116">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="fe9a7-116">In this section</span></span>

<span data-ttu-id="fe9a7-117">In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit Ihrer Skype for Business Server-Infrastruktur zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="fe9a7-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="fe9a7-118">Active Directory-Domänendienste für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="fe9a7-119">Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="fe9a7-120">Infrastruktur öffentlicher Schlüssel für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="fe9a7-121">TLS und MTLS für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="fe9a7-122">Verschlüsselung für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="fe9a7-123">Benutzer-und Clientauthentifizierung für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe9a7-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="fe9a7-124">Windows PowerShell und Skype for Business Server-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="fe9a7-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

