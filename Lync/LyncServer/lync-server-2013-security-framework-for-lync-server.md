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
ms.openlocfilehash: f84b7eaf3476624479d1ecb7c7bb564a4eae8ad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510442"
---
# <a name="security-framework-for-lync-server-2013"></a>Sicherheitsframework für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-08_

Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Microsoft lync Server 2013 bilden. Grundlegendes zur Zusammenarbeit dieser Elemente ist unerlässlich, um fundierte Entscheidungen zur Sicherung ihrer speziellen lync Server 2013-Bereitstellung zu treffen.

Folgende Komponenten sind beteiligt:

  - Die Active Directory-Domänendienste (AD DS) bieten ein zentrales vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.

  - Mit Role-Based Zugriffssteuerung (RBAC) können Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards aufrecht erhalten.

  - Die Public Key-Infrastruktur (PKI) verwendet Zertifikate, die von vertrauenswürdigen Zertifizierungsstellen ausgestellt wurden, um Server zu authentifizieren und die Datenintegrität sicherzustellen.

  - TLS (Transport Layer Security), HTTPS über SSL (HTTPS) und MTLS (Mutual TLS) ermöglichen die Authentifizierung von Endgeräten und die Sofortnachrichtenverschlüsselung. Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme werden mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt.

  - Standardprotokolle zur Authentifizierung von Benutzern, sofern möglich.

  - Windows PowerShell-Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass die Benutzer nicht auf einfache Weise oder unwissentlich Skripts ausführen können.

Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um eine sichere Grundlage für lync Server 2013 sicherzustellen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

In den Themen in diesem Abschnitt wird beschrieben, wie diese grundlegenden Elemente verwendet werden, um die Sicherheit Ihrer lync Server Infrastruktur zu verbessern.

  - [Active Directory-Domänendienste für lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC) für lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Öffentliche Schlüsselinfrastruktur für lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS und MTLS für lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Verschlüsselung für lync Server 2013](lync-server-2013-encryption.md)

  - [Benutzer-und Clientauthentifizierung für lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell-und lync Server 2013-Verwaltungstools](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

