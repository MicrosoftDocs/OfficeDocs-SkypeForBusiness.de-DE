---
title: Planen der Bereitstellung von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Zusammenfassung: Erfahren Sie, wie Business Server 2015 für instant messaging und Anwesenheit in Skype planen.'
ms.openlocfilehash: 1934f0308cda59b52073c47d1652ad2286bd6977
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planen der Bereitstellung von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie mehr über das Planen der Bereitstellung von Chatnachrichten und Anwesenheitsfunktionen in Skype for Business Server 2015.
  
Planen der Bereitstellung von Chatnachrichten und Anwesenheitsfunktionen in Skype for Business Server 2015 Weitere Informationen zu bestimmten Bereitstellungsoptionen wie aktivieren oder deaktivieren Offline Instant Messaging (IM), finden Sie unter [Deploy instant messaging und Anwesenheit in Skype für Business Server 2015](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planen der Bereitstellung von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server 2015

Front-End-Server core Skype Business Server-Funktionen, beispielsweise Sofortnachrichten (IM) und Anwesenheit und sind in jeder Skype für Business Server-Bereitstellung enthalten sind. Es gibt zwei Editionen: Skype für Business Server Enterprise Edition, in erster Linie für größere Organisationen entwickelt wurde, und Skype für Business Server Standard Edition, die in erster Linie für kleinere Unternehmen entwickelt wurde, eine kleinere wollen, Hardwareinvestitionen und erfordern keine vollständige Hochverfügbarkeits-Optionen. Beide Editionen unterstützen alle Skype für Business Server Arbeitslasten, einschließlich Sofortnachrichten, Anwesenheitsinformationen, Konferenzen und Enterprise-VoIP.
  
Mit der Chatfunktion können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Chatsitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Chatsitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.
  
Die Anwesenheitsfunktion liefert Nutzern Informationen zum Status anderer Nutzer im Netzwerk. Anwesenheitsstatus eines Benutzers enthält Informationen, mit denen andere Benutzer entscheiden können, ob sie versuchen sollen, den Benutzer zu kontaktieren und ob instant messaging, Telefon oder e-Mail verwenden. Anwesenheit fördert instant Kommunikation, wenn möglich, aber es enthält auch Informationen dazu, ob ein Benutzer in einer Besprechung oder nicht im Büro, was bedeutet, dass keine Sofortnachrichten Kommunikation möglich ist. Dieser Anwesenheitsstatus wird als ein Anwesenheitssymbol in Skype für Unternehmen und andere Anwesenheit unterstützende Anwendungen, einschließlich Microsoft Outlook messaging und Client für die Zusammenarbeit, Microsoft SharePoint-Technologien, und Microsoft Office angezeigt. Das Anwesenheitssymbol stellt die aktuelle Verfügbarkeit und Bereitschaft zur Kommunikation des Benutzers. 
  
### <a name="technical-requirements"></a>Technische Anforderungen

Chat und Anwesenheit werden in der Enterprise Edition immer auf Front-End-Pools und auf Standard Edition-Servern ausgeführt. Informationen zu unterstützten Hardware, Betriebssysteme und Datenbank-Software finden Sie unter [Infrastruktur für Skype für Unternehmen](https://technet.microsoft.com/en-us/office/dn947483) und [Anforderungen für Ihre Skype für Business-Umgebung](requirements-for-your-environment/requirements-for-your-environment.md).
  
### <a name="enabling-communication-with-external-users"></a>Aktivieren der Kommunikation mit externen Benutzern

Um zusätzlich von Ihrer Investition in Skype for Business Server zu profitieren, können Sie Ihre Benutzer für die Kommunikation mit externen Benutzern aktivieren. Bei externen Benutzern handelt es sich u. a. um folgende Benutzertypen:
  
- Remotebenutzer: die organisationseigenen Benutzer, wenn außerhalb der Organisationsfirewalls arbeiten und Laptops oder andere Skype für Business Server-Geräte verwenden.
    
- Verbundene Benutzer: Benutzer von Unternehmen mit denen Sie arbeiten, die auch Skype für Business Server ausführen. Damit Ihre Benutzer problemlos Kontakt zu diesen Benutzern aufnehmen können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen. 
    
- Skype-Benutzer: Skype for Business-Benutzer können mehrere hundert Millionen Benutzer auf Skype mit Chat, VoIP und Video erreichen.
    
> [!NOTE]
> AOL, Yahoo und Google Talk werden nicht mehr unterstützt. 
  
> [!NOTE]
> Zum Aktivieren eines oder aller dieser Szenarien müssen Sie einen Edgeserver für die sichere Kommunikation zwischen Ihrer Skype for Business Server-Bereitstellung und externen Benutzern bereitstellen. Remotebenutzer und Benutzern am Partnerorganisationen Ihrer Organisation können finden Sie unter die Anwesenheitsinformationen des anderen und über Sofortnachrichten kommunizieren können. 
  
> [!NOTE]
> Extensible Messaging and Presence Protocol (XMPP) wird nur für Zertifizierungsszenarien auf der Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) unterstützt. 
  
### <a name="archiving-im-content"></a>Archivieren von Chatinhalten

Skype for Business Server bietet Funktionen, die Sie bei der Einhaltung rechtlicher Vorschriften unterstützen. Mithilfe der Archivierung können Sie Chatinhalte für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer archivieren. Ausführliche Informationen finden Sie n der Planungsdokumentation unter „Planung der Archivierungsbereitstellung in Skype for Business Server 2015“. 
  
Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange-Daten in die Archivierung von Skype for Business Server-Daten integrieren und mithilfe eines einzigen Tools beide archivierten Datentypen durchsuchen. Weitere Informationen finden Sie unter Konfigurieren von Skype für Business Server 2015 zu Microsoft Exchange Server 2013-Archivierung verwenden.
  
### <a name="topologies-and-components"></a>Topologien und Komponenten

Nur diese Komponenten für Sofortnachrichten (IM) und Anwesenheit erforderlich sind:
  
- Front-End-Webservern Ihrer Organisation (bekannt als Pool) oder einem Standard Edition-Server. Chat und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert. Weitere Informationen zu Front-End-Pool-Topologien und Management finden Sie unter [Front-End-Pool hohe Verfügbarkeit und Management](high-availability-and-disaster-recovery/high-availability.md).
    
- Ein Lastenausgleich, wenn Sie einen Enterprise Edition-Front-End-Pool haben.
    
### <a name="supported-collocation"></a>Unterstützte Kollokation

Kollokation bedeutet, dass ein einzelner Server oder eine Gruppe von Servern mit mehreren installierten Rollen vorhanden ist. Ausführliche Informationen zum Verbinden finden Sie unter [Grundlagen der Topologie Skype für Business Server 2015](topology-basics/topology-basics.md). 
  

