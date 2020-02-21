---
title: 'Lync Server 2013: Sicherheitsframework für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7871d662d76f47685a58384804dfc6dee3b7b1d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="a6bfd-102">Sicherheitsframework für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6bfd-103">_**Letztes Änderungsstand des Themas:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="a6bfd-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="a6bfd-104">Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Microsoft lync Server 2013 bilden.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a6bfd-105">Grundlegendes zur Zusammenarbeit dieser Elemente ist unerlässlich, um fundierte Entscheidungen zur Sicherung ihrer speziellen lync Server 2013-Bereitstellung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="a6bfd-106">Folgende Komponenten sind beteiligt:</span><span class="sxs-lookup"><span data-stu-id="a6bfd-106">These elements are as follows:</span></span>

  - <span data-ttu-id="a6bfd-107">Die Active Directory-Domänendienste (AD DS) bieten ein zentrales vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="a6bfd-108">Mit der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) können Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards aufrecht erhalten.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="a6bfd-109">Die Public Key-Infrastruktur (PKI) verwendet Zertifikate, die von vertrauenswürdigen Zertifizierungsstellen ausgestellt wurden, um Server zu authentifizieren und die Datenintegrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="a6bfd-p102">TLS (Transport Layer Security), HTTPS über SSL (HTTPS) und MTLS (Mutual TLS) ermöglichen die Authentifizierung von Endgeräten und die Sofortnachrichtenverschlüsselung. Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme werden mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="a6bfd-112">Standardprotokolle zur Authentifizierung von Benutzern, sofern möglich.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="a6bfd-113">Windows PowerShell-Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass die Benutzer nicht auf einfache Weise oder unwissentlich Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="a6bfd-114">Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um eine sichere Grundlage für lync Server 2013 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a6bfd-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a6bfd-115">In This Section</span></span>

<span data-ttu-id="a6bfd-116">In den Themen in diesem Abschnitt wird beschrieben, wie diese grundlegenden Elemente verwendet werden, um die Sicherheit Ihrer lync Server Infrastruktur zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="a6bfd-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="a6bfd-117">Active Directory-Domänendienste für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="a6bfd-118">Rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="a6bfd-119">Öffentliche Schlüsselinfrastruktur für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="a6bfd-120">TLS und MTLS für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="a6bfd-121">Verschlüsselung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="a6bfd-122">Benutzer-und Clientauthentifizierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bfd-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="a6bfd-123">Windows PowerShell-und lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="a6bfd-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

