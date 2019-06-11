---
title: 'Lync Server 2013: Sicherheitsframework für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="da666-102">Sicherheitsframework für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da666-103">_**Letztes Änderungsdatum des Themas:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="da666-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="da666-104">Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Microsoft lync Server 2013 bilden.</span><span class="sxs-lookup"><span data-stu-id="da666-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="da666-105">Wenn Sie wissen möchten, wie diese Elemente zusammenarbeiten, ist es wichtig, fundierte Entscheidungen zum Sichern Ihrer speziellen lync Server 2013-Bereitstellung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="da666-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="da666-106">Es handelt sich um die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="da666-106">These elements are as follows:</span></span>

  - <span data-ttu-id="da666-107">Active Directory-Domänendienste (AD DS) bietet ein einzelnes vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="da666-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="da666-108">Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.</span><span class="sxs-lookup"><span data-stu-id="da666-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="da666-109">Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.</span><span class="sxs-lookup"><span data-stu-id="da666-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="da666-p102">Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="da666-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="da666-112">Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.</span><span class="sxs-lookup"><span data-stu-id="da666-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="da666-113">Windows PowerShell bietet Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass Benutzer keine einfachen oder unwissentlichen Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="da666-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="da666-114">Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um eine sichere Grundlage für lync Server 2013 zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="da666-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="da666-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="da666-115">In This Section</span></span>

<span data-ttu-id="da666-116">In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit Ihrer lync Server-Infrastruktur zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="da666-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="da666-117">Active Directory-Domänendienste für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="da666-118">Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="da666-119">Infrastruktur öffentlicher Schlüssel für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="da666-120">TLS und MTLS für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="da666-121">Verschlüsselung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="da666-122">Benutzer-und Clientauthentifizierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da666-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="da666-123">Windows PowerShell und Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="da666-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

