---
title: 'Lync Server 2013: Unterstützung der Zertifikatinfrastruktur'
TOCTitle: Unterstützung der Zertifikatinfrastruktur
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425950(v=OCS.15)
ms:contentKeyID: 49293880
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung der Zertifikatinfrastruktur in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS- (Transport Layer Security) und MTLS-Verbindungen (Mutual TLS). Standardmäßig ist Lync Server 2013 für die Verwendung von TLS für Verbindungen zwischen Clients und Servern konfiguriert. MTLS wird für Verbindungen zwischen Servern verwendet.

MTLS-Zertifikate müssen von vertrauenswürdigen Zertifizierungsstellen für Lync Server 2013 ausgestellt werden. Lync Server unterstützt Zertifikate von folgenden Zertifizierungsstellen:

  - Zertifikate, die von einer internen Zertifizierungsstelle ausgestellt wurden:
    
      - Die Windows Server 2003-Betriebssystem-Zertifizierungsstelle
    
      - Die Windows Server 2008-Betriebssystem-Zertifizierungsstelle
    
      - Die Windows Server 2008 R2-Betriebssystem-Zertifizierungsstelle
    
      - Die Zertifizierungsstelle des Betriebssystems Windows Server 2012
    
      - Die Zertifizierungsstelle des Betriebssystems Windows Server 2012 R2

  - Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden

Für die Kommunikation mit anderen Anwendungen und Servern, z. B. Exchange 2013, ist ein Zertifikat erforderlich, das von anderen Anwendungen und Produkten unterstützt wird. Für Version 2013 unterstützen Lync Server 2013 und andere Microsoft-Serverprodukte, darunter Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Authentifizierung und Autorisierung von Server zu Server. Ausführliche Informationen finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungs- oder Betriebsdokumentation.

Für Verbindungen von Clients, auf denen Windows 7-Betriebssystem, Windows Server 2008 R2-Betriebssystem und Microsoft Office Communicator 2007 Phone Edition ausgeführt wird, umfasst Lync Server 2013 Unterstützung für Zertifikate (ohne diese zu erfordern), die mithilfe der kryptografischen Hashfunktion SHA-256 signiert wurden. Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.

Nähere Informationen zu den Zertifikatanforderungen finden Sie in der Planungsdokumentation unter [Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md). Nähere Informationen über die Verwendung von Platzhaltern in Zertifikaten finden Sie in der Unterstützungsdokumentation unter [Unterstützung von Platzhalterzertifikaten in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md).

