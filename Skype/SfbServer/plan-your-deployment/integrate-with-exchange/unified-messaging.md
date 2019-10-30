---
title: Planen der Integration von Exchange Unified Messaging in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Zusammenfassung: Lesen Sie dieses Thema, während Sie planen, Skype for Business Server mit Exchange 2013 oder 2016 zu integrieren.'
ms.openlocfilehash: bed73151b1010dd287c21ea55372e4eb18117665
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772618"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planen der Integration von Exchange Unified Messaging in Skype for Business

**Zusammenfassung:** Lesen Sie dieses Thema, während Sie planen, Skype for Business Server mit Exchange 2013 oder 2016 zu integrieren.

Skype for Business Server unterstützt die Integration in Exchange Unified Messaging (um) für die Kombination von Voicemail und e-Mail-Messaging in einer einzelnen Messaginginfrastruktur. In Exchange ist Exchange Unified Messaging (um) eine von mehreren Exchange-Serverfunktionen, die Sie installieren und konfigurieren können.

In Microsoft Exchange Server 2013 und 2016 wird Exchange um als Dienst auf einem Exchange-Post Fach Server ausgeführt. Für Skype for Business Server Enterprise-VoIP-Bereitstellungen kombiniert Unified Messaging Voicemail und e-Mail-Nachrichten in einem einzigen Speicher, auf den Benutzer von einem Telefon (Outlook Voice Access) oder einem Computer aus zugreifen können. Unified Messaging und Skype for Business Server arbeiten zusammen, um die Anrufannahme, den Outlook Voice Access und die automatische Telefonzentrale für Benutzer von Enterprise-VoIP bereitzustellen.

> [!NOTE]
> Exchange um bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 mit Exchange 2013 oder Exchange 2016 integrieren. Aufgrund von Änderungen an der Unterstützung in Exchange 2019 wird die Exchange um-Integration zu Gunsten der Features Cloud Voicemail und Cloud-automatische Telefonzentrale de-hervorgehoben.  Weitere Informationen finden Sie unter [Planen des Cloud Voicemail-Diensts](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) und [Planen der Skype for Business Server-und Exchange Server-Migration](../../../sfbhybrid/hybrid/plan-um-migration.md) .


Damit diese Features in einer lokalen Exchange um-Bereitstellung unterstützt werden, müssen Sie eine der folgenden Aktionen ausführen:

- Microsoft Exchange Server 2010 oder neuestes Service Pack (nur Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Exchange Unified Messaging, wie zuvor bekannt, ist in Skype for Business Server 2019 nicht mehr verfügbar, das Telefon System zum Aufzeichnen von Sprachnachrichten verwendet und die Aufzeichnung dann im Exchange-Postfach eines Benutzers belassen. Weitere Informationen finden Sie unter [Planen des Cloud Voicemail-Diensts](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Features von Integrated Unified Messaging und Skype for Business Server

Skype for Business Server, Enterprise-VoIP verwendet die Exchange Unified Messaging (um)-Infrastruktur, um Anrufannahme, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und automatische Telefonzentralendienste bereitzustellen.

- **Anrufbeantwortung** Bei der Anrufbeantwortung werden Sprachnachrichten für Benutzer entgegengenommen, die gerade nicht an ihrem Platz sind oder sich bereits in einem Gespräch befinden. Hierzu gehören die Wiedergabe einer persönlichen Begrüßung, die Aufzeichnung einer Nachricht sowie die Übermittlung der Nachricht, um sie in die Warteschlange für eine Übermittlung an das auf dem Exchange-Postfachserver gespeicherte Postfach des Benutzers einzureihen.

    Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.

- **Outlook Voice Access** Outlook Voice Access ermöglicht einem Enterprise-VoIP-Benutzer den Zugriff auf nicht nur Voicemail, sondern auch den Exchange-Posteingang, einschließlich e-Mail, Kalender und Kontakte über eine Telefonschnittstelle. Die Teilnehmerzugriffsnummer wird von einem Exchange um-Administrator zugewiesen.

- **Automatische Telefonzentrale** Bei der automatischen Telefonzentrale handelt es sich um ein Exchange um-Feature, das verwendet werden kann, um eine Telefonnummer zu konfigurieren, die externe Benutzer anrufen können, um Unternehmensvertreter zu erreichen. Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen. Die Liste der verfügbaren Optionen wird vom Exchange um-Administrator auf dem Exchange um-Server konfiguriert.

- **Fax-Dienste** Exchange um umfasst Fax-Features, mit denen Benutzer eingehende Faxe in Ihren Exchange-Postfächern empfangen können. Ausführliche Informationen finden Sie unter [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in der Microsoft Exchange Server-Dokumentation.

    > [!NOTE]
    > Die vom Exchange um-Server bereitgestellten Faxdienst sind in den Skype for Business Server-Bereitstellungen, die in Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Service Pack, Exchange 2013 oder Exchange 2016 integriert sind, nicht verfügbar.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Komponenten und Topologien für lokales Unified Messaging in Skype for Business Server

### <a name="exchange-server-components"></a>Exchange Server-Komponenten

Um die Exchange um-Features und-Dienste bereitzustellen, die unter [Features von Integrated Unified Messaging und Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) für Enterprise-VoIP-Benutzer in Ihrer Organisation beschrieben sind, müssen Sie einen Microsoft Exchange-Post Fach Server und Client Zugriff bereitstellen. Server, der Benutzerpostfächer hostet und einen einzelnen Speicherort für e-Mail und Voicemail bereitstellt. Exchange um wird als Dienst auf Exchange-Postfach-und-Client Zugriffsservern ausgeführt.

Details zu den Exchange um-Komponenten in Microsoft Exchange Server 2010 finden Sie unter [Bereitstellen von lokalen Exchange um, um lync Server 2013 Preview-Voicemail bereitzustellen](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Unterstützte Topologien

Sie können Skype for Business Server und Exchange Unified Messaging (um) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn die Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Exchange-Integrationsschritte für jede Exchange um-Gesamtstruktur ausführen. Darüber hinaus müssen Sie die einzelnen Microsoft Exchange-Gesamtstrukturen so konfigurieren, dass Sie der Skype for Business Server-Gesamtstruktur und der Skype for Business Server-Gesamtstruktur vertrauen, um jeder Exchange um-Gesamtstruktur zu vertrauen. Zusätzlich zu dieser Gesamtstrukturvertrauensstellung müssen die Exchange um-Einstellungen für alle Benutzer für die Benutzerobjekte in der Skype for Business Server-Gesamtstruktur eingerichtet werden.

Skype for Business Server unterstützt die folgenden Topologien für die Exchange um-Integration:

- Einzelne Gesamtstruktur

- Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Skype for Business Server, Microsoft Exchange und Benutzer befinden sich alle in der gleichen Domäne.

- Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Skype for Business Server und Microsoft Exchange-Server werden in verschiedenen Domänen von der Domäne bereitgestellt, in der Sie Benutzer erstellen. Exchange um-Server können in verschiedenen Domänen des von Ihnen unterstützten Skype for Business Server-Pools bereitgestellt werden.

- Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Skype for Business Server wird in einer einzigen Gesamtstruktur bereitgestellt, und dann werden Benutzer über mehrere Gesamtstrukturen verteilt. Die Exchange um-Attribute der Benutzer müssen in die Skype for Business Server-Gesamtstruktur repliziert werden.

    > [!NOTE]
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange-Organisation kann Exchange um für Ihre Benutzer bereitstellen, oder Exchange um kann in derselben Gesamtstruktur wie Skype for Business Server bereitgestellt werden.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Richtlinien für die Integration von lokalen Unified Messaging-und Skype for Business-Servern

Im Folgenden sind Richtlinien und bewährte Methoden aufgeführt, die Sie beim Bereitstellen von Enterprise-VoIP berücksichtigen sollten:

> [!IMPORTANT]
> Exchange Unified Messaging (um) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.

- Bereitstellen eines Skype for Business Server Standard Edition-Servers oder eines Front-End-Pools.

- Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.

- Stellen Sie die Exchange-Postfachserverrollen in jeder Exchange Unified Messaging (um)-Gesamtstruktur bereit, in der Sie die Benutzer für Exchange um aktivieren möchten. Details zum Installieren von Exchange-Serverrollen finden Sie in der Dokumentation zu Microsoft Exchange Server.

    > [!IMPORTANT]
    > Wenn Exchange Unified Messaging (um) installiert ist, ist es für die Verwendung eines selbstsignierten Zertifikats konfiguriert. Durch das selbstsignierte Zertifikat ist Skype for Business Server und Exchange um nicht in der Lage, sich gegenseitig zu vertrauen, weshalb es notwendig ist, ein separates Zertifikat von einer Zertifizierungsstelle anzufordern, der beide Server Vertrauen.

- Wenn Skype for Business Server und Exchange um in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der Skype for Business Server-Gesamtstruktur und der Skype for Business Server-Gesamtstruktur vertrauen, um jeder Exchange-Gesamtstruktur zu vertrauen. Darüber hinaus können Sie die Exchange um-Einstellungen der Benutzer für die Benutzerobjekte in der Skype for Business Server-Gesamtstruktur festlegen, in der Regel mithilfe eines Skripts oder eines gesamtstrukturübergreifenden Tools wie Identity Lifecycle Manager (ILM).

- Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.

- Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.

- Wenn Sie eine frühere Exchange-Version als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, koordinieren Sie die Namen für Exchange um SIP-URI-Wählpläne und Enterprise-VoIP-Wählpläne.

### <a name="deploying-redundant-exchange-um-servers"></a>Bereitstellen redundanter Exchange UM-Server

> [!IMPORTANT]
> Wir empfehlen, dass Sie mindestens zwei Server bereitstellen, auf denen Exchange um-Dienste für jeden Exchange um-SIP-URI-Wählplan ausgeführt wird, den Sie für Ihre Organisation konfigurieren. Zusätzlich zu einer höheren Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit. Bei einem Serverfehler kann Skype for Business Server so konfiguriert werden, dass ein Failover zu einem anderen Server ausgeführt wird.

Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.

**Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange UM-Stabilitätsdiagramm](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

In Beispiel 1 sind die Exchange UM-Server 1 und 2 im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Bei einem Exchange UM-Ausfall in Tukwila sollten die DNS-A-Einträge für die Server 1 und 2 so konfiguriert sein, dass sie auf den Server 3 bzw. 4 zeigen. Bei einem Exchange UM-Ausfall in Dublin sollten die DNS-A-Einträge für die Server 3 und 4 so konfiguriert sein, dass sie auf den Server 1 bzw. 2 zeigen.

> [!NOTE]
> Für Beispiel 1 sollten Sie auch eines der folgenden Zertifikate auf jedem Exchange um-Server zuweisen: Verwenden Sie entweder ein Zertifikat mit einem Platzhalter im alternativen Betreff (Subject Alternative Name, San), oder setzen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes der vier Exchange um-Server im San.

**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange UM-Stabilitätsdiagramm](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.

Details zum Aktivieren oder Deaktivieren von Unified Messaging auf Exchange 2013 finden Sie unter [integrieren von Exchange 2013 um in lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Die bereitgestellten Informationen gelten gleichermaßen für Skype for Business Server.

Details zum Aktivieren oder Deaktivieren von Unified Messaging auf Microsoft Exchange Server 2010 finden Sie unter:

- [Aktivieren von Unified Messaging auf Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Deaktivieren von Unified Messaging auf Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange Unified Messaging ist in Exchange 2019 nicht mehr vorhanden, wenn Sie Exchange 2019 haben und entsprechende Funktionen benötigen, müssen Sie den in [Plan Cloud Voicemail-Dienst](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)beschriebenen Cloud-Voicemaildienst verwenden.


## <a name="see-also"></a>Siehe auch

[Übersicht zum Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Skype for Business](deployment-overview.md)
