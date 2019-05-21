---
title: Planen von Sofortnachrichten und Anwesenheitsinformationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Sofortnachrichten und Anwesenheitsinformationen in Skype for Business Server planen.'
ms.openlocfilehash: 29026a0b4ef7cce55f155f024efc9ccc84457906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297379"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planen von Sofortnachrichten und Anwesenheitsinformationen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Instant Messaging und Anwesenheit in Skype for Business Server planen.
  
Planen Sie Sofortnachrichten und Anwesenheitsinformationen in Skype for Business Server. Informationen zu bestimmten Bereitstellungsoptionen, wie das Aktivieren oder Deaktivieren von Instant Messaging (im), finden Sie unter [Bereitstellen von Instant Messaging und Anwesenheit in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planen von Sofortnachrichten und Anwesenheitsinformationen in Skype for Business Server

Front-End-Server bieten die Kernfunktionen von Skype for Business Server wie Chats (Sofortnachrichten) und Anwesenheitsinformationen und sind in jeder Skype for Business Server-Bereitstellung enthalten. Es stehen zwei Versionen zur Verfügung: Skype for Business Server Enterprise Edition, das in erster Linie für größere Organisationen konzipiert ist, und Skype for Business Server Standard Edition, das in erster Linie für kleinere Organisationen konzipiert ist, die eine kleinere Hardwareinvestition und erfordert keine vollständigen Optionen für die Hochverfügbarkeit. Beide Editionen unterstützen alle Skype for Business Server-Arbeitsauslastungen, einschließlich Chat, Anwesenheit, Konferenz und Enterprise-VoIP.
  
Mit der Chatfunktion können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Chatsitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Chatsitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.
  
Die Anwesenheitsfunktion liefert Nutzern Informationen zum Status anderer Nutzer im Netzwerk. Der Anwesenheitsstatus eines Benutzers bietet Informationen, um anderen zu helfen, zu entscheiden, ob er versuchen soll, den Benutzer zu kontaktieren, und ob er Sofortnachrichten, Telefone oder e-Mails verwenden soll. Anwesenheitsinformationen unterstützt die sofortige Kommunikation, wenn möglich, bietet aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder außerhalb des Büros befindet, was darauf hinweist, dass eine sofortige Kommunikation nicht möglich ist. Dieser Anwesenheitsstatus wird in Skype for Business und anderen Anwendungen mit Anwesenheitserkennung als Anwesenheitssymbol angezeigt, einschließlich des Microsoft Outlook-Messaging-und-Zusammenarbeits Clients, Microsoft SharePoint-Technologien und Microsoft Office. Das Anwesenheitssymbol steht für die aktuelle Verfügbarkeit und Kommunikationsbereitschaft des Benutzers. 
  
### <a name="technical-requirements"></a>Technische Anforderungen

Chat und Anwesenheit werden in der Enterprise Edition immer auf Front-End-Pools und auf Standard Edition-Servern ausgeführt. Informationen zu unterstützten Hardware, Betriebssystemen und Datenbanksoftware finden Sie unter [zertifizierte Gateways](../../SfbPartnerCertification/certification/infra-gateways.md), [Anforderungen für Ihre Skype for Business 2015-Umgebung](requirements-for-your-environment/requirements-for-your-environment.md)und [Infrastrukturanforderungen für Skype for Business Server 2019 ](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Aktivieren der Kommunikation mit externen Benutzern

Sie können die Vorteile Ihrer Investition in Skype for Business Server erheblich steigern, indem Sie Ihren Benutzern die Kommunikation mit externen Benutzern ermöglichen. Bei externen Benutzern sind unter anderem folgende Kategorien möglich:
  
- Remote Benutzer: die eigenen Benutzer Ihrer Organisation, wenn Sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere Skype for Business Server-Geräte verwenden.
    
- Federated-Benutzer: Benutzer von Unternehmen, mit denen Sie zusammenarbeiten, die auch Skype for Business Server ausführen. Damit Ihre Benutzer problemlos Kontakt zu diesen Benutzern aufnehmen können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen. 
    
- Skype-Benutzer: Skype for Business-Benutzer können mehrere hundert Millionen Benutzer auf Skype mit Chat, VoIP und Video erreichen.
    
> [!NOTE]
> AOL, Yahoo und Google Talk werden nicht mehr unterstützt. 
  
> [!NOTE]
> Wenn Sie ein oder alle dieser Szenarien aktivieren möchten, müssen Sie einen Edgeserver bereitstellen, um die sichere Kommunikation zwischen Ihrer Skype for Business Server-Bereitstellung und externen Benutzern zu ermöglichen. Die Remotebenutzer und Benutzer Ihrer Organisation in Verbundorganisationen können sich gegenseitig die Anwesenheitsinformationen anzeigen und über Chatnachrichten kommunizieren. 
  
> [!NOTE]
> Extensible Messaging and Presence Protocol (XMPP) wird nur für Zertifizierungsszenarien auf der Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) unterstützt. 
  
### <a name="archiving-im-content"></a>Archivieren von Chatinhalten

Skype for Business Server bietet Funktionen, die Sie verwenden können, wenn Ihre Organisation Konformitätsrichtlinien beachten muss. Mithilfe der Archivierung können Sie Chatinhalte für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer archivieren. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Skype for Business Server](archiving/archiving.md). 
  
Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange-Daten mit der Archivierung von Skype for Business Server-Daten integrieren und ein einzelnes Tool verwenden, um beide Arten von archivierten Daten zu durchsuchen. Weitere Informationen finden Sie unter [Konfigurieren von Skype for Business Server für die Verwendung der Exchange Server-Archivierung](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologien und Komponenten

Für Chat und Anwesenheit sind nur diese Komponenten erforderlich:
  
- Die Front-End-Server Ihrer Organisation (als Pool bezeichnet) oder ein Standard Edition-Server. Chat und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert. Weitere Informationen zu Front-End-Pool Topologien und-Verwaltung finden Sie unter [Verfügbarkeit und Verwaltung von Front-End-Pools](high-availability-and-disaster-recovery/high-availability.md).
    
- Ein Lastenausgleich, wenn Sie einen Enterprise Edition-Front-End-Pool haben.
    
### <a name="supported-collocation"></a>Unterstützte Kollokation

Kollokation bedeutet, dass ein einzelner Server oder eine Gruppe von Servern mit mehreren installierten Rollen vorhanden ist. Einzelheiten zur über Einsicht finden Sie unter [Topologie-Grundlagen für Skype for Business Server](topology-basics/topology-basics.md). 
  

