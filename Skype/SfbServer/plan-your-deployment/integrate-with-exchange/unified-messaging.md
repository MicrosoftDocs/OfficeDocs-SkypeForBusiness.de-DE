---
title: Planen der Exchange Unified Messaging-Integration in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Zusammenfassung: Lesen Sie dieses Thema, während Sie die Integration von Skype for Business Server in Exchange 2013 oder 2016 planen.'
ms.openlocfilehash: 1ae93ebeda07fccf6c9019d5bb78c63f7c722192
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810115"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planen der Exchange Unified Messaging-Integration in Skype for Business

**Zusammenfassung:** Lesen Sie dieses Thema, während Sie die Integration von Skype for Business Server in Exchange 2013 oder 2016 planen.

Skype for Business Server unterstützt die Integration in Exchange Unified Messaging (UM) für die Kombination von Voice messaging und E-Mail-Nachrichten in einer einzigen Messaginginfrastruktur. In Exchange ist Exchange Unified Messaging (UM) eine von mehreren Exchange-Serverrollen, die Sie installieren und konfigurieren können.

In Microsoft Exchange Server 2013 und 2016 wird Exchange UM als Dienst auf einem Exchange-Postfachserver ausgeführt. Für Skype for Business Server Enterprise-VoIP-Bereitstellungen kombiniert Unified Messaging Voice messaging und E-Mail-Messaging in einem einzigen Speicher, auf den Benutzer über ein Telefon (Outlook Voice Access) oder einen Computer zugreifen können. Unified Messaging und Skype for Business Server arbeiten zusammen, um Anrufbeantwortungs-, Outlook Voice Access- und automatische Telefoniedienste für Benutzer von Enterprise-VoIP.

> [!NOTE]
> Exchange UM bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 in Exchange 2013 oder Exchange 2016 integrieren. Aufgrund von Änderungen bei der Unterstützung in Exchange 2019 wird die Exchange -UM-Integration zugunsten von Cloud Voicemail- und Cloud-automatische Telefonzentrale hervorgehoben.  Weitere Informationen finden Sie unter "Plan [Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration".](../../../sfbhybrid/hybrid/plan-um-migration.md)


Damit diese Features in einer lokalen Exchange -UM-Bereitstellung unterstützt werden, müssen Sie eine der folgenden Schritte ausführen:

- Microsoft Exchange Server 2010 oder neuestes Service Pack (nur Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Exchange Unified Messaging, wie zuvor bekannt, ist in Skype for Business Server 2019 nicht mehr verfügbar, das telefonsystem verwendet, um Voicemailnachrichten zu erfassen und die Aufzeichnung dann im Exchange-Postfach eines Benutzers zu be lassen. Weitere Informationen finden Sie unter ["Planen des Cloud-Voicemaildiensts".](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Features von integriertem Unified Messaging und Skype for Business Server

Skype for Business Server, Enterprise-VoIP verwendet die Exchange Unified Messaging (UM)-Infrastruktur, um Anrufbeantwortung, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und Dienste der automatischen Telefon attendant zur Verfügung zu stellen.

- **Anrufbeantwortung** Bei der Anrufbeantwortung handelt es sich um den Empfang von Sprachnachrichten im Namen von Benutzern, deren Anrufe nicht beantwortet werden oder besetzt sind. Dazu gehören die Wiedergabe einer persönlichen Begrüßung, das Aufzeichnen einer Nachricht und das Senden der Nachricht, die zur Zustellung an das Postfach des Benutzers in der Warteschlange eingereiht werden soll, das auf dem Exchange-Postfachserver gespeichert ist.

    Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.

- **Outlook Voice Access** Outlook Voice Access ermöglicht es einem Enterprise-VoIP, nicht nur auf Voicemail, sondern auch auf den Posteingang von Exchange zu zugreifen, einschließlich E-Mail, Kalender und Kontakte über eine Telefonieschnittstelle. Die Teilnehmerzugriffsnummer wird von einem Exchange -UM-Administrator zugewiesen.

- **Automatische Attendant** Die automatische Telefon attendant ist eine Exchange UM-Funktion, die zum Konfigurieren einer Telefonnummer verwendet werden kann, die externe Benutzer wählen können, um Unternehmensmitarbeiter zu erreichen. Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen. Die Liste der verfügbaren Optionen wird vom Exchange -UM-Administrator auf dem Exchange -Server konfiguriert.

- **Faxdienste** Exchange UM enthält Faxfunktionen, mit denen Benutzer eingehende Faxnachrichten in ihren Exchange-Postfächern empfangen können. Ausführliche Informationen finden Sie unter [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in der Microsoft Exchange Server Dokumentation.

    > [!NOTE]
    > Faxdienste, die vom Exchange -UM-Server bereitgestellt werden, stehen in Skype for Business Server-Bereitstellungen, die in Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Service Pack, Exchange 2013 oder Exchange 2016 integriert sind, nicht zur Verfügung.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Komponenten und Topologien für lokales Unified Messaging in Skype for Business Server

### <a name="exchange-server-components"></a>Exchange Server-Komponenten

Zum Bereitstellen der Exchange UM-Features und -Dienste, die in den Features von integriertem Unified Messaging und [Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) für Enterprise-VoIP-Benutzer in Ihrer Organisation beschrieben sind, müssen Sie einen Microsoft Exchange-Postfachserver und Clientzugriffsserver bereitstellen, der Benutzerpostfächer hostet und einen einzigen Speicherort für E-Mail und Voicemail bietet. Exchange UM wird als Dienst auf Exchange-Postfach- und Clientzugriffsservern ausgeführt.

Weitere Informationen zu Exchange -UM-Komponenten in Microsoft Exchange Server 2010 finden Sie unter [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Unterstützte Topologien

Sie können Skype for Business Server und Exchange Unified Messaging (UM) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn sich die Bereitstellung über mehrere Gesamtstrukturen erstreckt, müssen Sie die Schritte zur Integration von Exchange für jede Exchange -UM-Gesamtstruktur ausführen. Darüber hinaus müssen Sie jede Microsoft Exchange-Gesamtstruktur so konfigurieren, dass sie der Skype for Business Server-Gesamtstruktur und der Skype for Business Server-Gesamtstruktur vertraut, um jeder Exchange -UM-Gesamtstruktur zu vertrauen. Zusätzlich zu dieser Gesamtstrukturvertrauensstellung müssen die Exchange -UM-Einstellungen für alle Benutzer für die Benutzerobjekte in der Skype for Business Server-Gesamtstruktur festgelegt werden.

Skype for Business Server unterstützt die folgenden Topologien für die Exchange UM-Integration:

- Einzelne Gesamtstruktur

- Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Skype for Business Server, Microsoft Exchange und Benutzer befinden sich alle in derselben Domäne.

- Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Skype for Business Server- und Microsoft Exchange-Server werden in anderen Domänen bereitgestellt als in der Domäne, in der Sie Benutzer erstellen. Exchange -UM-Server können in verschiedenen Domänen als der skype for Business Server-Pool bereitgestellt werden, den sie unterstützen.

- Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Skype for Business Server wird in einer einzelnen Gesamtstruktur bereitgestellt, und die Benutzer werden dann auf mehrere Gesamtstrukturen verteilt. Die Exchange -UM-Attribute der Benutzer müssen in die Skype for Business Server-Gesamtstruktur repliziert werden.

    > [!NOTE]
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange-Organisation kann Exchange UM für ihre Benutzer bereitstellen, oder Exchange UM kann in derselben Gesamtstruktur wie Skype for Business Server bereitgestellt werden.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Richtlinien für die Integration von lokalem Unified Messaging und Skype for Business Server

Im Folgenden finden Sie Richtlinien und bewährte Methoden, die Sie bei der Bereitstellung von Enterprise-VoIP:

> [!IMPORTANT]
> Exchange Unified Messaging (UM) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.

- Bereitstellen eines Skype for Business Server Standard Edition-Servers oder eines Front-End-Pools.

- Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.

- Stellen Sie die Exchange -Postfachserverrollen in jeder Exchange Unified Messaging (UM)-Gesamtstruktur, in der Sie Benutzer für Exchange UM aktivieren möchten. Ausführliche Informationen zum Installieren von Exchange-Serverrollen finden Sie in Microsoft Exchange Server Dokumentation.

    > [!IMPORTANT]
    > Wenn Exchange Unified Messaging (UM) installiert ist, wird es für die Verwendung eines selbst signierten Zertifikats konfiguriert. Das selbst signierte Zertifikat ermöglicht es Skype for Business Server und Exchange UM nicht, sich gegenseitig zu vertrauen, weshalb es erforderlich ist, ein separates Zertifikat von einer Zertifizierungsstelle an fordern, der beide Server vertrauen.

- Wenn Skype for Business Server und Exchange UM in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass sie der Skype for Business Server-Gesamtstruktur und der Skype for Business Server-Gesamtstruktur vertraut, um jeder Exchange-Gesamtstruktur zu vertrauen. Legen Sie außerdem die Exchange -UM-Einstellungen der Benutzer für die Benutzerobjekte in der Skype for Business Server-Gesamtstruktur, in der Regel mithilfe eines Skripts oder eines gesamtstrukturübergreifenden Tools, z. B. Identity Lifecycle Manager (ILM), ein.

- Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.

- Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.

- Wenn Sie eine Frühere Version von Exchange UM als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, müssen Sie die Koordinatennamen für Exchange UM-SIP-URI-Wählpläne und Enterprise-VoIP verwenden.

### <a name="deploying-redundant-exchange-um-servers"></a>Bereitstellen redundanter Exchange UM-Server

> [!IMPORTANT]
> Es wird empfohlen, mindestens zwei Server für jeden Exchange UM-SIP-URI-Wählplan, den Sie für Ihre Organisation konfigurieren, auf den Exchange -UM-Diensten ausgeführt werden. Die Bereitstellung redundanter Server bietet nicht nur erweiterte Kapazität, sondern bietet auch hohe Verfügbarkeit. Bei einem Serverausfall kann Skype for Business Server so konfiguriert werden, dass ein Failover auf einen anderen Server ausgeführt wird.

Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.

**Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange -UM-Ausfallsicherheitsdiagramm](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

In Beispiel 1 werden die Exchange -UM-Server 1 und 2 im Rechenzentrum "Tukwila" und die Exchange -UM-Server 3 und 4 im Rechenzentrum "Dublin" aktiviert. Bei einem Ausfall von Exchange UM in Tukwila sollten die DNS-A-Einträge (Domain Name System) für die Server 1 und 2 so konfiguriert werden, dass sie auf die Server 3 bzw. 4 verweisen. Bei einem Ausfall von Exchange UM in Dublin sollten die DNS-A-Einträge für die Server 3 und 4 so konfiguriert werden, dass sie auf die Server 1 bzw. 2 verweisen.

> [!NOTE]
> In Beispiel 1 sollten Sie auch eines der folgenden Zertifikate auf jedem Exchange -UM-Server zuweisen: Verwenden Sie entweder ein Zertifikat mit einem Platzhalter im alternativen Subject Name (SAN) oder geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der vier Exchange -Server im SAN ein.

**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange -UM-Ausfallsicherheitsdiagramm](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.

Weitere Informationen zum Aktivieren oder Deaktivieren von Unified Messaging in Exchange 2013 finden Sie unter Integrieren von  [Exchange 2013 UM in Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Die bereitgestellten Informationen gelten gleichermaßen für Skype for Business Server.

Weitere Informationen zum Aktivieren oder Deaktivieren von Unified Messaging in Microsoft Exchange Server 2010 finden Sie unter:

- [Aktivieren von Unified Messaging in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Deaktivieren von Unified Messaging in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange Unified Messaging ist in Exchange 2019 nicht mehr vorhanden, wenn Sie über Exchange 2019 verfügen und eine entsprechende Funktionalität benötigen, müssen Sie den cloudbasierten Voicemaildienst verwenden, der unter [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)beschrieben wird.


## <a name="see-also"></a>Siehe auch

[Übersicht über den Bereitstellungsprozess für die Integration von lokalem Unified Messaging und Skype for Business](deployment-overview.md)
