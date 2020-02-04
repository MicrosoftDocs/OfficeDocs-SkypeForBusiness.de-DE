---
title: 'Lync Server 2013: Zusätzliche Serverunterstützung und Anforderungen'
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
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-09_

Zusätzlich zu der Softwareunterstützung, die in den anderen Abschnitten dieser Dokumentation zur unter Stützungs Dokumentation beschrieben wird, weist lync Server 2013 die folgenden Supporteinschränkungen auf:

  - Lync Server 2013 unterstützt DNS (Domain Name System) und den Hardwarelastenausgleich für bestimmte Server Rollen. Sie unterstützt auch den Anwendungslastenausgleich für Vermittlungsserver, falls dies angemessen ist. Einzelheiten zur Verwendung der einzelnen Informationen finden Sie in der Planungsdokumentation.

  - Lync Server 2013 verwendet das dlx (Distribution List Expansion Protocol) zum Erweitern von Verteilerlisten. Dieses Protokoll gibt auch die Webdienstmethode an, die zum Abrufen der Mitgliedschaft einer Verteilerliste verwendet wird. Microsoft Exchange Server unterstützt dynamische Gruppen, denen keine Mitglieder statisch zugewiesen sind. Stattdessen werden Abfragen gespeichert, die ausgewertet werden, wenn die Gruppe erweitert wird. DLX unterstützt keine dynamischen Verteilerlisten. Diese dlx-Einschränkung gilt für alle Versionen von lync Server.

  - Der Assistent zum Aktivieren des Benutzers unterstützt keine automatische Konvertierung von nicht englischen Zeichen in einen SIP-kompatiblen URI, daher müssen Sie die SIP-Adresse manuell ändern.

  - Informationen zu Servern, auf denen Antivirus-Software ausgeführt wird, finden Sie unter [Ausschlüsse für Antivirus-Scans für lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) für vorgeschlagene Viren Ausschlüsse und andere sicherheitsrelevante Empfehlungen.

  - Wenn Sie IPSec verwenden, empfiehlt es sich, IPSec über die für Audio-und Videodatenverkehr verwendeten Portbereiche zu deaktivieren. Ausführliche Informationen finden Sie unter [IPsec-Ausnahmen in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.

  - Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt. Ausführliche Informationen zum Implementieren von QoS finden Sie unter [Verwalten von Quality of Service (QoS) in lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in der Betriebsdokumentation.

  - Die Verwendung der Firewall des Betriebssystems wird unterstützt. Lync Server 2013 verwaltet die Firewall-Ausnahmen für die Betriebssystem Firewall, mit Ausnahme der Microsoft SQL Server-Datenbanksoftware. Details zu den Anforderungen der SQL Server-Firewall finden Sie in der SQL Server-Dokumentation.

  - Die externen Schnittstellen, die zum Implementieren der Unterstützung für den Zugriff durch externe Benutzer verwendet werden, müssen sich in einem separaten Subnetz befinden, *nicht* im gleichen Netzwerk wie die internen Schnittstellen.

  - Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.

  - Mit der Veröffentlichung von lync Server 2013 kumulativen Updates: Juli 2013 unterstützt lync Server 2013 jetzt die zweistufige Authentifizierung. Weitere Informationen finden Sie unter [zweistufige Authentifizierung in lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - Für die meisten internen Server ist ein Zertifikattyp erforderlich, der als **Open Authentication** (OAuth) definiert ist. Sie müssen während der **Anforderungs-, Installations-und** Zertifikat Phase des lync Server-Bereitstellungs-Assistenten ein OAuth-Zertifikat anfordern und zuweisen. Die Mindestgröße für einen OAuth-Zertifikatschlüssel lautet 1024-Bits. Eine Warnung wird möglicherweise angezeigt, wenn Sie ein Zertifikat mit einer Schlüssellänge von weniger als 2048 Bits anfordern. Um potenzielle Probleme zu vermeiden, falls eine Schlüssellänge von 2048 anstelle einer Warnung erzwungen wird, wird dringend empfohlen, immer eine Schlüssellänge von 2048 für OAuth-Zertifikate zu verwenden.

  - Lync Server 2013 und Microsoft Exchange Server 2010 Service Pack 1 (SP1) funktionieren mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server 2008 R2-Betriebssysteme so konfiguriert sind, dass Sie die FIPS 140-2-Algorithmen für Systemkryptografie. Zum Implementieren der FIPS-Unterstützung müssen Sie jeden Server mit lync Server 2013 so konfigurieren, dass er unterstützt wird. Ausführliche Informationen zu FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, "System Kryptographie: Verwenden von FIPS-kompatiblen Algorithmen für Verschlüsselung, Hashing und Signatur Sicherheit in Windows XP und späteren Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)-Versionen unter. Details zu FIPS 140-2-Unterstützung und Einschränkungen in Exchange 2010 finden Sie unter "Exchange 2010 SP1 und Unterstützung für FIPS- [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)konforme Algorithmen" unter.

Lync Server 2013 erfordert die Installation anderer Software auf bestimmten Komponenten vor oder während der Bereitstellung. Dazu gehören Software, die mit dem Betriebssystem, herunterladbarer Software und Software zur Verfügung steht, die während der Installation von lync Server 2013 automatisch installiert wird. Im folgenden finden Sie eine Liste zusätzlicher Software, die erforderlich sein kann:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4,5-Framework

  - Microsoft Visual C++ 2012 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable wird automatisch installiert, wenn Sie lync Server 2013 installieren. Sie sollten keine andere Version installieren und verwenden.

    
    </div>

  - URL-umschreibungs Modul, Version 2,0, verteilbare

  - Windows Media Format-Laufzeitkomponente

  - Windows PowerShell, Version 3,0

  - Microsoft Silverlight 4-Browser-Plug-in (Silverlight-4.0.50524.0 oder die neueste Version der lync Server-Systemsteuerung)

  - Tools für Active Directory-Domänendienste

Einige dieser Softwareanforderungen gelten nur für bestimmte Serverrollen oder Komponenten. Details zu diesen Softwareanforderungen finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

