---
title: Sicherheitsframework für Lync Server 2013
TOCTitle: Sicherheitsframework für Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59682862
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sicherheitsframework für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-08_

Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Microsoft Lync Server 2013 bilden. Es ist wichtig zu verstehen, wie diese Elemente zusammenarbeiten, damit Sie fundierte Entscheidungen zum Sichern Ihrer bestimmten Lync Server 2013-Bereitstellung treffen können.

Es handelt sich um die folgenden Elemente:

  - Active Directory-Domänendienste (AD DS) bietet ein einziges vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.

  - Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.

  - Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.

  - Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und Chatverschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.

  - Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich

  - Windows PowerShell bietet Sicherheitsfunktionen, die standardmäßig aktiviert sind, damit Benutzer nicht einfach oder unwissentlich Skripte ausführen können.

Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Abläufe zu definieren und so eine sichere Grundlage für Lync Server 2013 zu sichern.

## In diesem Abschnitt

Unter den einzelnen Themen in diesem Abschnitt wird beschrieben, wie all diese grundlegenden Elemente funktionieren, um die Sicherheit Ihrer Lync Server-Infrastruktur zu verbessern.

  - [Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Rollenbasierte Zugriffskontrolle (RBAC) für Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Public Key-Infrastruktur für Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS und MTLS für Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Verschlüsselung für Lync Server 2013](lync-server-2013-encryption.md)

  - [Benutzer- und Clientauthentifizierung für Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell und Lync Server 2013-Verwaltungstools](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

