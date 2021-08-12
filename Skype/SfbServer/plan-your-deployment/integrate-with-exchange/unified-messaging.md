---
title: Planen der integration von Exchange Unified Messaging in Skype for Business
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
description: 'Zusammenfassung: Lesen Sie dieses Thema, während Sie planen, Skype for Business Server in Exchange 2013 oder 2016 zu integrieren.'
ms.openlocfilehash: 68ae17e7a7c5f3b427323f1ea571337de264529fbee954c61f40fb8afe20d1a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349937"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planen der integration von Exchange Unified Messaging in Skype for Business

**Zusammenfassung:** Lesen Sie dieses Thema, während Sie planen, Skype for Business Server in Exchange 2013 oder 2016 zu integrieren.

Skype for Business Server unterstützt die Integration in Exchange Unified Messaging (UM) zum Kombinieren von Sprachnachrichten und E-Mail-Nachrichten in einer einzigen Messaginginfrastruktur. In Exchange ist Exchange Unified Messaging (UM) eine von mehreren Exchange Serverrollen, die Sie installieren und konfigurieren können.

In Microsoft Exchange Server 2013 und 2016 wird Exchange UM als Dienst auf einem Exchange Postfachserver ausgeführt. Für Skype for Business Server Enterprise-VoIP Bereitstellungen kombiniert Unified Messaging Voice Messaging und E-Mail-Nachrichten in einem einzigen Speicher, auf den Benutzer über ein Telefon (Outlook Voice Access) oder einen Computer zugreifen können. Unified Messaging und Skype for Business Server zusammenarbeiten, um Benutzern von Enterprise-VoIP Dienste für die Anrufbeantwortung, Outlook VoIP-Zugriff und automatische Telefonzentralen bereitzustellen.

> [!NOTE]
> Exchange UM bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 mit Exchange 2013 oder Exchange 2016 integrieren. Aufgrund von Änderungen bei der Unterstützung in Exchange 2019 wird Exchange UM-Integration zugunsten Cloud-Voicemail- und Cloud-Funktionen für die automatische Telefonzentrale deaktiviert.  Weitere Informationen finden Sie unter [Plan Cloud-Voicemail Service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and Plan for Skype for Business Server and Exchange Server [migration.](../../../sfbhybrid/hybrid/plan-um-migration.md)


Damit diese Features in einer lokalen Exchange UM-Bereitstellung unterstützt werden, müssen Sie eine der folgenden Funktionen ausführen:

- Microsoft Exchange Server 2010 oder neuestes Service Pack (nur Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Exchange Unified Messaging wie zuvor bekannt ist in Skype for Business Server 2019 nicht mehr verfügbar, das Telefonsystem verwendet, um Voicemailnachrichten aufzuzeichnen und die Aufzeichnung dann im Exchange Postfach eines Benutzers zu belassen. Weitere Informationen finden Sie [unter Plan Cloud-Voicemail Service.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Features von integriertem Unified Messaging und Skype for Business Server

Skype for Business Server verwendet Enterprise-VoIP die Exchange Unified Messaging (UM)-Infrastruktur, um Anrufbeantwortung, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und Dienste für die automatische Telefonzentrale bereitzustellen.

- **Anrufbeantwortung** Die Anrufbeantwortung ist das Empfangen von Sprachnachrichten im Namen von Benutzern, deren Anrufe nicht beantwortet werden oder beschäftigt sind. Dazu gehört das Wiedergeben einer persönlichen Begrüßung, das Aufzeichnen einer Nachricht und das Senden der Nachricht, die zur Übermittlung an das Postfach des Benutzers in die Warteschlange eingereiht werden soll, das auf dem Exchange Postfachserver gespeichert ist.

    Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.

- **Outlook Voice Access** Outlook Voice Access ermöglicht einem Enterprise-VoIP Benutzer nicht nur den Zugriff auf Voicemail, sondern auch den Exchange Posteingang, einschließlich E-Mail, Kalender und Kontakten über eine Telefonieschnittstelle. Die Abonnentenzugriffsnummer wird von einem Exchange UM-Administrator zugewiesen.

- **Automatische Telefonzentrale** Die automatische Telefonzentrale ist eine Exchange UM-Funktion, die verwendet werden kann, um eine Telefonnummer zu konfigurieren, die externe Benutzer wählen können, um Unternehmensvertreter zu erreichen. Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen. Die Liste der verfügbaren Optionen wird vom Exchange UM-Administrator auf dem Exchange UM-Server konfiguriert.

- **Faxdienste** Exchange UM umfasst Faxfunktionen, mit denen Benutzer eingehende Faxe in ihren Exchange Postfächern empfangen können. Ausführliche Informationen finden Sie in der Dokumentation zu [Unified Messaging](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) in der Microsoft Exchange Server.

    > [!NOTE]
    > Vom Exchange UM-Server bereitgestellte Faxdienste sind in Skype for Business Server Bereitstellungen, die in Microsoft Exchange Server 2010 integriert sind, Exchange 2010 mit dem neuesten Service Pack, Exchange 2013 oder Exchange 2016 nicht verfügbar.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Komponenten und Topologien für lokales Unified Messaging in Skype for Business Server

### <a name="exchange-server-components"></a>Exchange Server-Komponenten

Um die Exchange UM-Features und -Dienste bereitzustellen, die unter [Features von integriertem Unified Messaging und Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) für Enterprise-VoIP Benutzer in Ihrer Organisation beschrieben sind, müssen Sie einen Microsoft Exchange Postfachserver und Clientzugriffsserver bereitstellen, der Benutzerpostfächer hostet und einen einzigen Speicherort für E-Mails und Voicemail bereitstellt. Exchange UM wird als Dienst auf Exchange Postfach- und Clientzugriffsservern ausgeführt.

Ausführliche Informationen zu Exchange UM-Komponenten in Microsoft Exchange Server 2010 finden Sie unter [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .

### <a name="supported-topologies"></a>Unterstützte Topologien

Sie können Skype for Business Server und Exchange Unified Messaging (UM) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn die Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Exchange Integrationsschritte für jede Exchange UM-Gesamtstruktur ausführen. Darüber hinaus müssen Sie jede Microsoft Exchange-Gesamtstruktur so konfigurieren, dass sie der Skype for Business Server Gesamtstruktur und der Skype for Business Server-Gesamtstruktur vertraut, damit jeder Exchange UM-Gesamtstruktur vertraut wird. Zusätzlich zu dieser Gesamtstrukturvertrauensstellung müssen die Exchange UM-Einstellungen für alle Benutzer für die Benutzerobjekte in der Skype for Business Server Gesamtstruktur festgelegt werden.

Skype for Business Server unterstützt die folgenden Topologien für die Exchange UM-Integration:

- Einzelne Gesamtstruktur

- Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Skype for Business Server, Microsoft Exchange und Benutzer befinden sich alle in derselben Domäne.

- Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Skype for Business Server und Microsoft Exchange Server werden in verschiedenen Domänen bereitgestellt als in der Domäne, in der Sie Benutzer erstellen. Exchange UM-Server können in verschiedenen Domänen bereitgestellt werden als der Skype for Business Server-Pool, den sie unterstützen.

- Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Skype for Business Server wird in einer einzigen Gesamtstruktur bereitgestellt, und die Benutzer werden dann über mehrere Gesamtstrukturen verteilt. Die Exchange UM-Attribute der Benutzer müssen in die Skype for Business Server Gesamtstruktur repliziert werden.

    > [!NOTE]
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange Organisation kann ihren Benutzern Exchange UM bereitstellen, oder Exchange UM kann in derselben Gesamtstruktur wie Skype for Business Server bereitgestellt werden.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Richtlinien für die Integration lokaler Unified Messaging- und Skype for Business Server

Es folgen Richtlinien und bewährte Methoden, die Sie beim Bereitstellen von Enterprise-VoIP berücksichtigen sollten:

> [!IMPORTANT]
> Exchange Unified Messaging (UM) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.

- Stellen Sie einen Skype for Business Server Standard Edition-Server oder einen Front-End-Pool bereit.

- Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.

- Stellen Sie die Exchange Postfachserverrollen in jeder Exchange Unified Messaging (UM)-Gesamtstruktur bereit, in der Sie Benutzer für Exchange UM aktivieren möchten. Ausführliche Informationen zum Installieren Exchange Serverrollen finden Sie in der Dokumentation Microsoft Exchange Server.

    > [!IMPORTANT]
    > Wenn Exchange Unified Messaging (UM) installiert ist, ist es für die Verwendung eines selbstsignierten Zertifikats konfiguriert. Das selbstsignate Zertifikat ermöglicht Skype for Business Server und Exchange UM nicht, sich gegenseitig zu vertrauen. Aus diesem Grund ist es erforderlich, ein separates Zertifikat von einer Zertifizierungsstelle anzufordern, der beide Server vertrauen.

- Wenn Skype for Business Server und Exchange UM in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange Gesamtstruktur so, dass sie der Skype for Business Server Gesamtstruktur vertraut, und die Skype for Business Server Gesamtstruktur jeder Exchange Gesamtstruktur vertraut. Legen Sie außerdem die Exchange UM-Einstellungen der Benutzer für die Benutzerobjekte in der Skype for Business Server Gesamtstruktur fest, in der Regel mithilfe eines Skripts oder eines gesamtstrukturübergreifenden Tools, z. B. Identity Lifecycle Manager (ILM).

- Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.

- Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.

- Wenn Sie eine frühere Version von Exchange UM als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, koordinieren Sie die Namen für Exchange UM-SIP-URI-Wählpläne und Enterprise-VoIP Wählpläne.

### <a name="deploying-redundant-exchange-um-servers"></a>Bereitstellen redundanter Exchange UM-Server

> [!IMPORTANT]
> Es wird empfohlen, mindestens zwei Server bereitzustellen, auf denen Exchange UM-Dienste für jeden Exchange UM-SIP-URI-Wählplan ausgeführt werden, den Sie für Ihre Organisation konfigurieren. Zusätzlich zur Bereitstellung erweiterter Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit. Im Falle eines Serverfehlers kann Skype for Business Server so konfiguriert werden, dass ein Failover auf einen anderen Server ausgeführt wird.

Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.

**Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange UM-Resilienzdiagramm](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

In Beispiel 1 sind Exchange UM-Server 1 und 2 im Rechenzentrum VonZwila aktiviert, und Exchange UM-Server 3 und 4 sind im Rechenzentrum Dublin aktiviert. Im Falle eines Exchange UM-Ausfalls in Cortanawila sollten die DNS-Einträge (Domain Name System) für die Server 1 und 2 so konfiguriert werden, dass sie auf die Server 3 bzw. 4 verweisen. Im Falle eines Exchange UM-Ausfalls in Dublin sollten die DNS A-Einträge für die Server 3 und 4 so konfiguriert werden, dass sie auf die Server 1 bzw. 2 verweisen.

> [!NOTE]
> For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.

**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange UM-Resilienzdiagramm](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.

Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging in Exchange 2013 finden Sie unter [Integrieren von Exchange 2013 UM in Lync Server.](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help) Die bereitgestellten Informationen gelten gleichermaßen für Skype for Business Server.

Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging in Microsoft Exchange Server 2010 finden Sie unter:

- [Aktivieren von Unified Messaging auf Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Deaktivieren von Unified Messaging in Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange Unified Messaging ist in Exchange 2019 nicht mehr vorhanden, wenn Sie über Exchange 2019 verfügen und entsprechende Funktionen benötigen, müssen Sie den in [Plan Cloud-Voicemail Service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)beschriebenen Cloud-Voicemail Dienst verwenden.


## <a name="see-also"></a>Siehe auch

[Übersicht über den Bereitstellungsprozess für die Integration von lokalem Unified Messaging und Skype for Business](deployment-overview.md)