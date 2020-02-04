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
ms.openlocfilehash: 1a2b58d34c1ed1f899e0daac8c1bb0132b1a22d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Sicherheitsframework für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-08_

Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Microsoft lync Server 2013 bilden. Wenn Sie wissen möchten, wie diese Elemente zusammenarbeiten, ist es wichtig, fundierte Entscheidungen zum Sichern Ihrer speziellen lync Server 2013-Bereitstellung zu treffen.

Es handelt sich um die folgenden Elemente:

  - Active Directory-Domänendienste (AD DS) bietet ein einzelnes vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.

  - Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.

  - Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.

  - Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.

  - Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.

  - Windows PowerShell bietet Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass Benutzer keine einfachen oder unwissentlichen Skripts ausführen können.

Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um eine sichere Grundlage für lync Server 2013 zu gewährleisten.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit Ihrer lync Server-Infrastruktur zu verbessern.

  - [Active Directory-Domänendienste für lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infrastruktur öffentlicher Schlüssel für lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS und MTLS für lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Verschlüsselung für lync Server 2013](lync-server-2013-encryption.md)

  - [Benutzer-und Clientauthentifizierung für lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell und Lync Server 2013-Verwaltungstools](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

