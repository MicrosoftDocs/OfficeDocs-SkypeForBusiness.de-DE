---
title: 'Lync Server 2013: Zusätzliche Serverunterstützung und Anforderungen'
TOCTitle: Zusätzliche Serverunterstützung und Anforderungen
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398577(v=OCS.15)
ms:contentKeyID: 49294451
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Neben der in anderen Abschnitten dieser Dokumentation beschriebenen Softwareunterstützung gelten für Lync Server 2013 die folgenden Einschränkungen hinsichtlich der Unterstützung:

  - Lync Server 2013 unterstützt DNS (Domain Name System) und Hardwaregeräte zum Lastenausgleich für bestimmte Serverrollen. Außerdem wird der Anwendungslastenausgleich für Vermittlungsserver nach Bedarf unterstützt. Ausführliche Informationen dazu, in welchen Fällen welcher Lastenausgleich eingesetzt wird, finden Sie in der Planungsdokumentation.

  - Lync Server 2013 verwendet das DLX-Protokoll (Distribution List Expansion) zur Verteilerlistenerweiterung. Dieses Protokoll legt außerdem die Webdienstmethode fest, die zum Erhalten der Mitgliedschaft in einer Verteilerliste verwendet wird. Microsoft Exchange Server unterstützt dynamische Gruppen, deren Mitglieder nicht statisch zugewiesen werden. Stattdessen werden darin Abfragen gespeichert, die beim Erweitern der Gruppe ausgewertet werden. DLX unterstützt keine dynamischen Verteilerlisten.

  - Der Assistent zum Aktivieren von Benutzern unterstützt nicht die automatische Konvertierung nicht-englischer Zeichen in einen SIP-kompatiblen URI, daher müssen Sie die SIP-Adresse manuell ändern.

  - Lesen Sie bei Servern, auf denen ein Virenschutzprogramm ausgeführt wird, den folgenden Artikel, in dem Sie Vorschläge für Bereiche, die von der Virenüberprüfung ausgenommen werden sollten, und weitere sicherheitsbezogene Empfehlungen finden: [Ausnahmen in Virenschutzprogrammen für Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.

  - Wenn Sie IPsec verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von Audio- und Videodaten verwendet werden. Ausführliche Informationen finden Sie unter [IPSec-Ausnahmen](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.

  - Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt. Ausführliche Informationen zur Implementierung von QoS finden Sie unter [Verwalten der Dienstqualität (Quality of Service, QoS)](lync-server-2013-managing-quality-of-service-qos.md) in der Betriebsdokumentation.

  - Die Verwendung der Betriebssystemfirewall wird unterstützt. Lync Server 2013 verwaltet die Firewallausnahmen für die Betriebssystemfirewall (ausgenommen bei der Microsoft SQL Server-Datenbanksoftware). Ausführliche Informationen zu den Anforderungen hinsichtlich der Firewall für SQL Server finden Sie in der SQL Server-Dokumentation.

  - Die zum Implementieren der Unterstützung für den externen Benutzerzugriff verwendeten externen Schnittstellen müssen sich in einem separaten Subnetz befinden, *nicht* in demselben Netzwerk wie die internen Schnittstellen.

  - Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.

  - Mit der Veröffentlichung der kumulativen Updates für Lync Server 2013 im Juli 2013 unterstützt Lync Server 2013 nun die zweistufige Authentifizierung. Weitere Informationen finden Sie unter [Planen für und Bereitstellen von zweistufiger Authentifizierung](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - Für die meisten internen Server ist ein Zertifikattyp erforderlich, der als **Open Authentication** (OAuth) definiert ist. Sie müssen in der Phase **Zertifikate anfordern, installieren oder zuweisen** des Lync Server-Bereitstellungs-Assistenten ein OAuth-Zertifikat anfordern und zuweisen. Die Mindestgröße eines OAuth-Zertifikatsschlüssels beträgt 1024 Bit. Es wird möglicherweise eine Warnung angezeigt, wenn Sie ein Zertifikat mit einer Schlüssellänge von weniger als 2048 Bit anfordern. Falls keine Warnung erfolgt, sondern eine Schlüssellänge von 2048 Bit erzwungen wird, können Sie potenzielle Probleme vermeiden, indem Sie, wie empfohlen, immer eine Schlüssellänge von 2048 Bit für OAuth-Zertifikate verwenden.

  - Lync Server 2013 und Microsoft Exchange Server 2010 Service Pack 1 (SP1) unterstützen FIPS 140-2-Algorithmen (Federal Information Processing Standard), wenn die Betriebssysteme Windows Server 2008 R2 für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert wurden. Um FIPS-Unterstützung zu implementieren, müssen Sie jeden Server mit Lync Server 2013 so konfigurieren, dass er FIPS unterstützt. Ausführliche Informationen zu FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, "Auswirkungen der Sicherheitseinstellung 'Systemkryptografie: FIPS-konformen Algorithmus für Verschlüsselung, Hashing und Signatur verwenden' unter Windows XP und neueren Version von Windows" unter <http://support.microsoft.com/kb/811833>. Ausführliche Informationen zur Unterstützung von FIPS 140-2 in Exchange 2010 und den dafür geltenden Beschränkungen finden Sie im Blogbeitrag "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" unter <http://go.microsoft.com/fwlink/?linkid=205335>.

Für Lync Server 2013 ist die Installation weiterer Software auf bestimmten Komponenten vor oder während der Bereitstellung erforderlich. Hierzu gehört Software, die mit dem Betriebssystem verfügbar ist, zum Download bereitstehende Software oder Software, die automatisch während der Installation von Lync Server 2013 installiert wird. In der folgenden Liste wird zusätzliche Software aufgeführt, die möglicherweise erforderlich ist:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET Framework 4.5

  - Microsoft Visual C++ 2012 Redistributable
    

    > [!NOTE]
    > Microsoft Visual C++ 2012 Redistributable wird bei der Installation von Lync Server 2013 automatisch installiert. Installieren und verwenden Sie keine andere Version.



  - URL Rewrite Module Version 2.0 Redistributable

  - Windows Media Format-Laufzeitkomponente

  - Windows PowerShell, Version 3.0

  - Microsoft Silverlight 4-Browser-Plug-In (Silverlight 4.0.50524.0 oder neueste Version für die Lync Server-Systemsteuerung)

  - Tools in Active Directory-Domänendienste

Einige dieser Softwareanforderungen gelten nur für bestimmte Serverrollen oder Komponenten. Ausführliche Informationen zu diesen Softwareanforderungen finden Sie unter [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

