---
title: Planen von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Zusammenfassung: Erfahren Sie, wie Sie Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server planen.'
ms.openlocfilehash: 20de382c034e2049bdb7bb2b36f2da9bc847b876
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737661"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planen von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server planen.
  
Planen von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server. Informationen zu bestimmten Bereitstellungsoptionen, z. B. Aktivieren oder Deaktivieren von Offline-Chatdiensten, finden Sie unter [Bereitstellen von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planen von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server

Front-End-Server bieten Skype for Business Server Kernfunktionen wie Chatnachrichten und Anwesenheitsinformationen und sind in jeder Skype for Business Server Bereitstellung enthalten. Es stehen zwei Editionen zur Verfügung: Skype for Business Server Enterprise Edition, die in erster Linie für größere Organisationen entwickelt wurde, und Skype for Business Server Standard Edition, das in erster Linie für kleinere Organisationen entwickelt wurde, die eine geringere Hardwareinvestitionen und erfordern keine vollständigen Hochverfügbarkeitsoptionen. Beide Editionen unterstützen alle Skype for Business Server Workloads, einschließlich Chatnachrichten, Anwesenheitsinformationen, Konferenzen und Enterprise-VoIP.
  
Mit der Sofortnachrichtenfunktion (Instant Messaging, IM) können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Sofortnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Sofortnachrichtensitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.
  
Anwesenheit stellt Benutzern Informationen über den Status anderer Personen im Netzwerk bereit. Der Anwesenheitsstatus eines Benutzers enthält Informationen, mit denen andere entscheiden können, ob sie versuchen sollen, den Benutzer zu kontaktieren und ob Chat, Telefon oder E-Mail verwendet werden soll. Die Anwesenheit fördert nach Möglichkeit eine sofortige Kommunikation, liefert aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder außerhalb des Büros befindet, was darauf hinweist, dass eine sofortige Kommunikation nicht möglich ist. Dieser Anwesenheitsstatus wird als Anwesenheitssymbol in Skype for Business und anderen Anwesenheitsanwendungen angezeigt, einschließlich des Microsoft Outlook Messaging- und Zusammenarbeitsclients, von Microsoft SharePoint-Technologien und Microsoft Office. Das Anwesenheitssymbol stellt die aktuelle Verfügbarkeit des Benutzers und die Bereitschaft zur Kommunikation dar. 
  
### <a name="technical-requirements"></a>Technische Anforderungen

Chatnachrichten und Anwesenheitsinformationen werden immer auf Enterprise Edition Front-End-Pools und Standard Edition Servern ausgeführt. Informationen zu unterstützter Hardware, Betriebssystemen und Datenbanksoftware finden Sie unter [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md), [Requirements for your Skype for Business 2015 environment,](requirements-for-your-environment/requirements-for-your-environment.md)and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Aktivieren der Kommunikation mit externen Benutzern

Sie können die Vorteile Ihrer Investition in Skype for Business Server erheblich steigern, indem Sie Ihren Benutzern die Kommunikation mit externen Benutzern ermöglichen. Externe Benutzer können Folgendes umfassen:
  
- Remotebenutzer: Die eigenen Benutzer Ihrer Organisation, wenn sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere Skype for Business Server-Geräte verwenden.
    
- Verbundbenutzer: Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten, die auch Skype for Business Server ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen. 
    
- Skype Benutzer: Skype for Business Benutzer können hunderte Millionen Von Benutzern auf Skype mit Chat, Sprache und Video erreichen.
    
> [!NOTE]
> AOL, Yahoo und Google Talk werden nicht mehr unterstützt. 
  
> [!NOTE]
> Um eines oder alle dieser Szenarien zu aktivieren, müssen Sie einen Edgeserver bereitstellen, um eine sichere Kommunikation zwischen Ihrer Skype for Business Server-Bereitstellung und externen Benutzern zu ermöglichen. Die Remotebenutzer und Benutzer Ihrer Organisation in Verbundorganisationen können die Anwesenheit der anderen Benutzer sehen und über Chatnachrichten kommunizieren. 
  
> [!NOTE]
> Extensible Messaging and Presence Protocol (XMPP) wird nur für JITC-Zertifizierungsszenarien (Joint Interoperability Test Command) der Unified Capabilities Collaboration Platform (UCCP) unterstützt. 
  
### <a name="archiving-im-content"></a>Archivierung von Chatinhalten

Skype for Business Server bietet Features, die Sie verwenden können, wenn Ihre Organisation Compliance-Vorschriften einhalten muss. Sie können die Archivierung verwenden, um den Inhalt von Chatnachrichten für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer zu archivieren, die Sie angeben. Ausführliche Informationen finden Sie unter [Plan for archiving in Skype for Business Server](archiving/archiving.md). 
  
Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange Daten in die Archivierung von Skype for Business Server Daten integrieren und ein einzelnes Tool verwenden, um beide Arten archivierter Daten zu durchsuchen. Weitere Informationen finden Sie unter [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologien und Komponenten

Für Instant Messaging (IM) und Anwesenheit sind nur diese Komponenten erforderlich:
  
- Die Front-End-Server Ihrer Organisation (auch als Pool bezeichnet) oder ein Standard Edition Server. Instant Messaging- und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert. Weitere Informationen zu Front-End-Pooltopologien und -verwaltung finden Sie unter "Hohe Verfügbarkeit und Verwaltung von [Front-End-Pools".](high-availability-and-disaster-recovery/high-availability.md)
    
- Ein Lastenausgleich, wenn Sie über einen Enterprise Edition Front-End-Pool verfügen.
    
### <a name="supported-collocation"></a>Unterstützte Kollokation

Kollokation ist definiert als ein einzelner Server oder eine Gruppe von Servern, auf dem mehrere Rollen installiert sind. Ausführliche Informationen zur Kollokation finden Sie unter [Topologiegrundlagen für Skype for Business Server](topology-basics/topology-basics.md). 
  

