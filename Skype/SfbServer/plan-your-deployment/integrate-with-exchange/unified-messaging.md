---
title: Planen der Integration von Exchange Unified Messaging in Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Zusammenfassung: Lesen Sie diesen Abschnitt beim Planen der Integration von Skype für Business Server 2015 mit Exchange 2013.'
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planen der Integration von Exchange Unified Messaging in Skype for Business
 
**Zusammenfassung:** Überprüfen Sie beim Planen der Integration von Skype für Business Server 2015 mit Exchange 2013 in diesem Thema.
  
Skype für Business Server 2015 unterstützt die Integration mit Exchange Unified Messaging (UM) zum Kombinieren von Voicemessaging und e-Mail-messaging in einer einzigen Messaginginfrastruktur. In Exchange ist Exchange Unified Messaging (UM) der mehrere Exchange-Serverrollen, die Sie installieren und konfigurieren können. 
  
In Microsoft Exchange Server 2013 führt Exchange UM als Dienst auf einem Exchange-Postfachserver. Für Skype für Business Server 2015 Enterprise-VoIP-Bereitstellungen kombiniert Unified Messaging Voicemessaging und e-Mail-messaging in einer einzelnen Informationsspeicher, den Benutzer über ein Telefon (Outlook Voice Access) oder einem Computer zugreifen können. Unified Messaging und Skype für Business Server 2015 arbeiten zusammen, um Benutzern von Enterprise-VoIP-Anrufbeantwortung, Outlook Voice Access und automatische Telefonzentrale bereitzustellen.
  
Weitere Informationen zu den architekturänderungen in Microsoft Exchange Server 2013 finden Sie unter [VoIP-Architekturänderungen](https://go.microsoft.com/fwlink/p/?LinkId=266730) in der Dokumentation zu Microsoft Exchange Server 2013.
  
Für diese Features in einer lokalen Exchange UM-Bereitstellung unterstützt werden müssen Sie eine der folgenden ausführen:
  
- Microsoft Exchange Server 2010 oder neuestes Servicepack
    
- Microsoft Exchange Server 2013
    
-  Microsoft Exchange Server 2016
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a>Features von integriertem Unified Messaging und Skype for Business Server 2015

Skype für Business Server 2015, Enterprise-VoIP verwendet die Infrastruktur für Exchange Unified Messaging (UM), um Anrufbeantwortung, anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und Dienste automatischer Telefonzentralen bereitzustellen.
  
- **Anrufbeantwortung** Bei der Anrufbeantwortung werden Sprachnachrichten für Benutzer entgegengenommen, die gerade nicht an ihrem Platz sind oder sich bereits in einem Gespräch befinden. Hierzu gehören die Wiedergabe einer persönlichen Begrüßung, die Aufzeichnung einer Nachricht sowie die Übermittlung der Nachricht, um sie in die Warteschlange für eine Übermittlung an das auf dem Exchange-Postfachserver gespeicherte Postfach des Benutzers einzureihen.
    
    Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.
    
- **Outlook Voice Access** Outlook Voice Access ermöglicht einen Enterprise-VoIP-Benutzer Zugriff auf Voicemail, sondern auch auf den Posteingang von Exchange, einschließlich e-Mail, Kalender und Kontakte aus einer Telefonie-Benutzeroberfläche. Die Teilnehmerzugriffsnummer wird von einem Exchange UM-Administrator zugewiesen.
    
- **Automatische Telefonzentrale** Automatische Telefonzentrale ist eine Exchange UM-Funktion, die verwendet werden kann, so konfigurieren Sie eine Telefonnummer ein, die externe Benutzer wählen können, um Unternehmensmitarbeiter zu erreichen. Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen. Die Liste der verfügbaren Optionen wird vom Exchange UM-Administrator auf dem Exchange UM-Server konfiguriert.
    
- **Faxdienste** Exchange UM umfasst faxfeatures, die damit Benutzer eingehende Faxe in ihren Exchange-Postfächern empfangen können. Weitere Informationen hierzu finden Sie in der Dokumentation zu Microsoft Exchange Server [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) .
    
    > [!NOTE]
    > Faxdienste des Exchange UM-Servers stehen nicht in Skype für Business Server-Bereitstellungen, die mit Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Servicepack oder Exchange 2013 integriert sind. 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a>Komponenten und Topologien für lokales Unified Messaging in Skype for Business Server 2015

### <a name="exchange-server-components"></a>Exchange Server-Komponenten

Um die Exchange UM beschriebenen Features und Dienste in [Features von integriertem Unified Messaging und Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx) Enterprise-VoIP-Benutzern in Ihrer Organisation zu ermöglichen, müssen Sie ein Microsoft Exchange-Postfachserver und Clientzugriffsserver bereitstellen, die Benutzerpostfächer hostet und bietet einen einzigen Speicherort für e-Mail und Voicemail. Exchange UM als ein Dienst auf Exchange-Postfach und Clientzugriffsservern ausgeführt.
  
Ausführliche Informationen zu Exchange UM-Komponenten in Microsoft Exchange Server 2010 finden Sie unter [Bereitstellen von lokalen Exchange UM für Lync Server 2013 Preview Voice Mail geben Sie](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) in der Bereitstellungsdokumentation.
  
### <a name="supported-topologies"></a>Unterstützte Topologien

Sie können Skype für Business Server 2015 und Exchange Unified Messaging (UM) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn die Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Exchange-Integrationsschritte für jede Gesamtstruktur Exchange UM ausführen. Darüber hinaus müssen Sie jede Microsoft Exchange-Gesamtstruktur als vertrauenswürdig, der Skype für Business Server 2015 Gesamtstruktur und der Skype für Business Server 2015 Gesamtstruktur, um jeden Exchange UM-Gesamtstruktur-Vertrauensstellung konfigurieren. Zusätzlich zu dieser Gesamtstruktur-Vertrauensstellung müssen die Exchange UM-Einstellungen für alle Benutzer auf die Benutzerobjekte in der Skype für Business Server 2015 Gesamtstruktur festgelegt werden. 
  
Skype für Business Server 2015 unterstützt die folgenden Topologien für Exchange UM-Integration:
  
- Einzelne Gesamtstruktur
    
- Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Skype für Business Server 2015, Microsoft Exchange und Benutzer befinden sich in derselben Domäne.
    
- Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Skype für Business Server 2015 und Microsoft Exchange Server werden in unterschiedlichen Domänen aus der Domäne, in dem Sie Benutzer erstellen, bereitgestellt. Exchange UM-Server können in anderen Domänen als der Skype für Business Server 2015 Pool bereitgestellt werden, die sie unterstützen.
    
- Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Skype für Business Server 2015 in einer einzigen Gesamtstruktur bereitgestellt wird, und klicken Sie dann die Benutzer über mehrere Gesamtstrukturen hinweg verteilt werden. Der Benutzer Exchange UM Attribute müssen über auf die Skype für Business Server 2015 Gesamtstruktur repliziert werden.
    
    > [!NOTE]
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange-Organisation Exchange UM für die Benutzer bereitstellen kann, oder können Exchange UM für Business Server 2015 in derselben Gesamtstruktur wie Skype bereitgestellt werden. 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a>Richtlinien für die Integration lokaler Unified Messaging-Dienste und Skype for Business Server 2015

Im Folgenden sind Richtlinien und bewährte Methoden aufgeführt, die Sie beim Bereitstellen von Enterprise-VoIP berücksichtigen sollten:
  
> [!IMPORTANT]
> Exchange Unified Messaging (UM) unterstützt IPv6 nur, wenn Sie UCMA 4 verwenden. 
  
- Bereitstellen einer Skype für Business Server 2015 Standard Edition-Server oder einen Front-End-Pool. Ausführliche Informationen zu Installation finden Sie unter [Bereitstellen von Skype für Business Server 2015](../../deploy/deploy.md) in der Bereitstellungsdokumentation.
    
- Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.
    
- Stellen Sie die Exchange-Postfach Server-Rollen in jeder Exchange Unified Messaging (UM) Gesamtstruktur, in der Sie Benutzer für Exchange UM aktivieren möchten. Weitere Informationen zum Installieren von Exchange-Serverrollen finden Sie unter der Dokumentation zu Microsoft Exchange Server 2013.
    
    > [!IMPORTANT]
    > Wenn Exchange Unified Messaging (UM) installiert ist, wird es so konfiguriert, dass ein selbstsigniertes Zertifikat verwenden. Das selbstsignierte Zertifikat ermöglicht keine Skype für Business Server 2015 und Exchange UM einander vertrauen aus diesem Grund ist es erforderlich, ein separates Zertifikat von einer Zertifizierungsstelle anfordern, die beide Server als vertrauenswürdig. 
  
- Wenn Skype für Business Server 2015 und Exchange UM in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur als vertrauenswürdig, der Skype für Business Server 2015 Gesamtstruktur und der Skype für Business Server 2015 Gesamtstruktur, um jede Exchange-Gesamtstruktur vertrauen. Legen Sie auch die Benutzer Exchange UM-Einstellungen für die Benutzerobjekte in der Skype für Business Server 2015 Gesamtstruktur, in der Regel mithilfe eines Skripts oder einer gesamtstrukturübergreifenden-Tool wie Identity Lifecycle Manager (ILM).
    
- Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.
    
- Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.
    
- Wenn Sie eine frühere Version von Exchange UM als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, wählen Sie Pläne und Enterprise-VoIP-Wählpläne koordinieren Sie die Namen für Exchange um-SIP-URI. 
    
### <a name="deploying-redundant-exchange-um-servers"></a>Bereitstellen redundanter Exchange UM-Server

> [!IMPORTANT]
> Es wird empfohlen, dass Sie mindestens zwei Server, auf dem Exchange UM Services ausgeführt wird, für jeden Exchange um-SIP-URI-Wählplan, die Sie für Ihre Organisation konfigurieren, bereitstellen. Zusätzlich zu einer höheren Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit. Ausfall eines Servers kann Skype für Business Server 2015 Failover auf einen anderen Server konfiguriert werden. 
  
Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.
  
**In Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange UM-Stabilitätsdiagramm](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
In Beispiel 1 sind die Exchange UM-Server 1 und 2 im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Bei einem Exchange UM-Ausfall in Tukwila sollten die DNS-A-Einträge für die Server 1 und 2 so konfiguriert sein, dass sie auf den Server 3 bzw. 4 zeigen. Bei einem Exchange UM-Ausfall in Dublin sollten die DNS-A-Einträge für die Server 3 und 4 so konfiguriert sein, dass sie auf den Server 1 bzw. 2 zeigen.
  
> [!NOTE]
> Beispiel 1, Sie sollten auch zuweisen für eins der folgenden Zertifikate auf jedem Exchange UM-Server: Verwenden Sie entweder ein Zertifikat mit einem Platzhalter im Subject Alternative Name (SAN) oder den vollqualifizierten Domänennamen (FQDN) der einzelnen Exchange UM-Server im SAN zu platzieren. 
  
**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange UM-Stabilitätsdiagramm](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.
  
Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging auf Exchange 2013 finden Sie unter [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Die Angaben gilt gleichermaßen für Skype für Business Server 2015.
  
Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging auf Microsoft Exchange Server 2010 finden Sie unter:
  
- [Aktivieren von Unified Messaging in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [Deaktivieren von Unified Messaging in Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a>Siehe auch

#### 

[Übersicht über den Bereitstellungsprozess für die Integration von lokalen Unified Messaging und Skype für Unternehmen](deployment-overview.md)

