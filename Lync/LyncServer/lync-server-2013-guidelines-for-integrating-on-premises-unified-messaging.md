---
title: 'Lync Server 2013: Richtlinien für die Integration lokaler Unified Messaging-Dienste'
TOCTitle: Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398656(v=OCS.15)
ms:contentKeyID: 49294590
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Im Folgenden sind Richtlinien und bewährte Methoden aufgeführt, die Sie beim Bereitstellen von Enterprise-VoIP berücksichtigen sollten:


> [!IMPORTANT]
> Exchange Unified Messaging (UM) unterstützt IPv6 nur dann, wenn Sie UCMA 4 verwenden.



  - Stellen Sie einen Lync Server 2013 Standard Edition-Server oder Front-End-Pool bereit. Ausführliche Informationen finden Sie unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

  - Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.

  - Stellen Sie in jeder Exchange Unified Messaging (UM)-Gesamtstruktur, in der Benutzer für Exchange UM aktiviert werden sollen, die Exchange-Postfach-Serverrolle bereit. Ausführliche Informationen zur Installation von Exchange-Serverrollen finden Sie in der Microsoft Exchange Server 2013-Dokumentation.
    

    > [!IMPORTANT]
    > Bei der Installation von Exchange Unified Messaging (UM) wird diese Komponente für die Verwendung eines selbstsignierten Zertifikats konfiguriert.<BR>Das selbstsignierte Zertifikat ermöglicht jedoch keine gegenseitige Vertrauensstellung zwischen Lync Server 2013 und Exchange UM. Daher muss ein separates Zertifikat von einer Zertifizierungsstelle angefordert werden, die beide Server als vertrauenswürdig einstufen.



  - Wenn Lync Server 2013 und Exchange UM in unterschiedlichen Gesamtstrukturen installiert werden, muss für jede Exchange-Gesamtstruktur eine Vertrauensbeziehung mit der Lync Server 2013-Gesamtstruktur und für die Lync Server 2013-Gesamtstruktur eine Vertrauensbeziehung mit der Exchange-Gesamtstruktur eingerichtet werden. Zudem müssen die Exchange UM-Einstellungen der Benutzer für die Benutzerobjekte in der Lync Server 2013-Gesamtstruktur festgelegt werden. Zu diesem Zweck wird typischerweise ein Skript oder ein gesamtstrukturübergreifendes Tool wie Identity Lifecycle Manager (ILM) verwendet.

  - Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.

  - Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.

  - Bei Verwendung einer früheren Exchange UM-Version als Microsoft Exchange Server 2010 Service Pack 1 (SP1) müssen Sie Namen für Exchange UM-SIP-URI-Wählpläne und Enterprise-VoIP-Wählpläne koordinieren.

## Bereitstellen redundanter Exchange UM-Server


> [!IMPORTANT]
> Microsoft empfiehlt die Bereitstellung von mindestens zwei Servern, auf denen die Exchange UM-Dienste ausgeführt werden, und zwar für jeden Satz mit Exchange UM-SIP-URI-Wähleinstellungen, den Sie für Ihre Organisation bereitstellen. Zusätzlich zu einer höheren Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit. Beim Ausfall eines Servers kann Lync Server 2013 für das Failover auf einen anderen Server konfiguriert werden.



Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.

**Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange UM – Beispiel 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM – Beispiel 1")

In Beispiel 1 sind die Exchange UM-Server 1 und 2 im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Bei einem Exchange UM-Ausfall in Tukwila sollten die DNS-A-Einträge für die Server 1 und 2 so konfiguriert sein, dass sie auf den Server 3 bzw. 4 zeigen. Bei einem Exchange UM-Ausfall in Dublin sollten die DNS-A-Einträge für die Server 3 und 4 so konfiguriert sein, dass sie auf den Server 1 bzw. 2 zeigen.


> [!NOTE]
> In Beispiel&nbsp;1 sollten Sie zudem auf jedem Exchange&nbsp;UM-Server eins der folgenden Zertifikate zuweisen: 
> <UL>
> <LI>
> <P>Verwenden Sie ein Zertifikat mit einem Platzhalter im alternativen Antragstellernamen.</P>
> <LI>
> <P>Tragen Sie die vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der einzelnen Exchange&nbsp;UM-Server als alternativen Antragstellernamen ein.</P></LI></UL>



**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange UM – Beispiel 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM – Beispiel 2")

In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.

Für ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging für Exchange 2013 lesen Sie "Microsoft Lync Server 2013" unter [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).

Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging für Microsoft Exchange Server 2010 finden Sie unter:

  - "Aktivieren von Unified Messaging in Exchange 2010" unter [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/?linkid=com/fwlink/p/?linkid=204418).

  - "Deaktivieren von Unified Messaging in Exchange 2010" unter [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/?linkid=com/fwlink/p/?linkid=204416).

## Siehe auch

#### Konzepte

[Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

