---
title: 'Lync Server 2013: zusätzliche Server Unterstützung und-Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd3dad53b954fed8e1513ff9704b35c3c4831ffd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521252"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-09_

Zusätzlich zu der in den anderen Abschnitten dieser Unterstützungsdokumentation beschriebenen Softwareunterstützung verfügt lync Server 2013 über die folgenden Supporteinschränkungen:

  - Lync Server 2013 unterstützt Domain Name System (DNS)-und Hardwarelastenausgleich für bestimmte Server Rollen. Außerdem wird der Anwendungslastenausgleich für Vermittlungsserver nach Bedarf unterstützt. Ausführliche Informationen dazu, in welchen Fällen welcher Lastenausgleich eingesetzt wird, finden Sie in der Planungsdokumentation.

  - Lync Server 2013 verwendet das dlx (Distribution List Expansion Protocol), um Verteilerlisten zu erweitern. Dieses Protokoll legt außerdem die Webdienstmethode fest, die zum Erhalten der Mitgliedschaft in einer Verteilerliste verwendet wird. Exchange Server unterstützt dynamische Gruppen, denen keine Mitglieder statisch zugewiesen sind. Stattdessen werden darin Abfragen gespeichert, die beim Erweitern der Gruppe ausgewertet werden. DLX unterstützt keine dynamischen Verteilerlisten. Diese dlx-Einschränkung gilt für alle Versionen von lync Server.

  - Der Assistent zum Aktivieren von Benutzern unterstützt nicht die automatische Konvertierung nicht-englischer Zeichen in einen SIP-kompatiblen URI, daher müssen Sie die SIP-Adresse manuell ändern.

  - Für Server, auf denen Antivirensoftware installiert ist, finden Sie unter [Antivirus Scanning Ausschlüsse für lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) für vorgeschlagene Viren Ausschlüsse und andere sicherheitsrelevante Empfehlungen.

  - Wenn Sie IPsec verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von Audio- und Videodaten verwendet werden. Ausführliche Informationen finden Sie unter [IPSec Exceptions in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.

  - Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt. Ausführliche Informationen zum Implementieren von QoS finden Sie unter [Managing Quality of Service (QoS) in lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in der Betriebsdokumentation.

  - Die Verwendung der Betriebssystemfirewall wird unterstützt. Lync Server 2013 verwaltet die Firewall-Ausnahmen für die Betriebssystem Firewall, mit Ausnahme von Microsoft SQL Server-Datenbanksoftware. Ausführliche Informationen zu den Anforderungen hinsichtlich der Firewall für SQL Server finden Sie in der SQL Server-Dokumentation.

  - Die zum Implementieren der Unterstützung für den externen Benutzerzugriff verwendeten externen Schnittstellen müssen sich in einem separaten Subnetz befinden, *nicht* in demselben Netzwerk wie die internen Schnittstellen.

  - Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.

  - Mit der Veröffentlichung lync Server 2013 kumulativen Updates: Juli 2013 unterstützt lync Server 2013 jetzt die zweistufige Authentifizierung. Weitere Informationen finden Sie unter [zweistufige Authentifizierung in lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - Für die meisten internen Server ist ein Zertifikattyp erforderlich, der als **Open Authentication** (OAuth) definiert ist. Sie müssen während der **Anforderungs-, install-und Assign** -Phase des lync Server-Bereitstellungs-Assistenten ein OAuth-Zertifikat anfordern und zuweisen. Die Mindestgröße für einen OAuth-Zertifikatschlüssel beträgt 1024 Bit. Eine Warnung wird möglicherweise angezeigt, wenn Sie ein Zertifikat mit einer Schlüssellänge von weniger als 2048 Bits anfordern. Um potenzielle Probleme zu vermeiden, falls eine Schlüssellänge von 2048 anstelle von Warnungen erzwungen wird, wird dringend empfohlen, immer eine Schlüssellänge von 2048 für OAuth-Zertifikate zu verwenden.

  - Lync Server 2013 und Microsoft Exchange Server 2010 Service Pack 1 (SP1) arbeiten mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server 2008 R2-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert sind. Um die FIPS-Unterstützung zu implementieren, müssen Sie jeden Server konfigurieren, der lync Server 2013 ausführt, um ihn zu unterstützen. Ausführliche Informationen zu FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, "System Cryptography: Verwenden von FIPS-kompatiblen Algorithmen für Verschlüsselung, Hashing und Signieren von Sicherheitseinstellungen in Windows XP und höheren Windows-Versionen unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) . Ausführliche Informationen zur Unterstützung von FIPS 140-2 und zu Einschränkungen in Exchange 2010 finden Sie unter "Exchange 2010 SP1 und Unterstützung für FIPS-konforme Algorithmen" unter [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .

Lync Server 2013 erfordert die Installation anderer Software auf bestimmten Komponenten vor oder während der Bereitstellung. Dies umfasst Software, die mit dem Betriebssystem, herunterladbare Software und Software zur Verfügung steht, die bei der Installation von lync Server 2013 automatisch installiert wird. In der folgenden Liste wird zusätzliche Software aufgeführt, die möglicherweise erforderlich ist:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4,5 Framework

  - Microsoft Visual C++ 2012 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable wird bei der Installation von lync Server 2013 automatisch installiert. Sie sollten keine andere Version installieren und verwenden.

    
    </div>

  - URL Rewrite Module Version 2.0 Redistributable

  - Windows Media Format-Laufzeitkomponente

  - Windows PowerShell Version 3,0

  - Microsoft Silverlight 4-Browser-Plug-In (Silverlight 4.0.50524.0 oder neueste Version für die Lync Server-Systemsteuerung)

  - Active Directory-Domänendienste Tools

Einige dieser Softwareanforderungen gelten nur für bestimmte Serverrollen oder Komponenten. Ausführliche Informationen zu diesen Softwareanforderungen finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

