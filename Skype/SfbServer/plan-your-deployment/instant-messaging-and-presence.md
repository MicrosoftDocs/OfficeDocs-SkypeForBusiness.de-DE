---
title: Planen von Chat und Anwesenheit in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Zusammenfassung: Informationen zum Planen von Chat und Anwesenheit in Skype for Business Server.'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816275"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planen von Chat und Anwesenheit in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Instant Messaging und Anwesenheit in Skype for Business Server planen.
  
Planen von Chat und Anwesenheit in Skype for Business Server. Informationen zu bestimmten Bereitstellungsoptionen, z. B. zum Aktivieren oder Deaktivieren von Offline instant Messaging (IM), finden Sie unter Bereitstellen von Chat und Anwesenheit [in Skype for Business Server.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planen von Chat und Anwesenheit in Skype for Business Server

Front-End-Server bieten zentrale Skype for Business Server-Funktionen wie Chat und Anwesenheit und sind in jeder Skype for Business Server-Bereitstellung enthalten. Es stehen zwei Editionen zur Verfügung: Skype for Business Server Enterprise Edition, die in erster Linie für größere Organisationen entwickelt wurde, und Skype for Business Server Standard Edition, die in erster Linie für kleinere Organisationen konzipiert ist, die eine kleinere Hardwareinvestitionen benötigen und keine vollständigen Hochverfügbarkeitsoptionen benötigen. Beide Editionen unterstützen alle Skype for Business Server-Workloads, einschließlich Chat, Anwesenheit, Konferenzen und Enterprise-VoIP.
  
Mit der Sofortnachrichtenfunktion (Instant Messaging, IM) können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Sofortnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Sofortnachrichtensitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.
  
Anwesenheitsinformationen bieten Benutzern Informationen über den Status anderer Benutzer im Netzwerk. Der Anwesenheitsstatus eines Benutzers enthält Informationen, mit deren Hilfe andere Personen entscheiden können, ob sie versuchen sollen, den Benutzer zu kontaktieren und ob Sie Chatnachrichten, Telefone oder E-Mails verwenden möchten. Anwesenheit fördert nach Möglichkeit die sofortige Kommunikation, bietet aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder nicht im Büro befindet, was darauf hinweist, dass eine sofortige Kommunikation nicht möglich ist. Dieser Anwesenheitsstatus wird als Anwesenheitssymbol in Skype for Business und anderen Anwendungen mit Anwesenheitsinformationen angezeigt, einschließlich des Microsoft Outlook-Clients für Messaging und Zusammenarbeit, Microsoft SharePoint-Technologien und Microsoft Office. Das Anwesenheitssymbol stellt die aktuelle Verfügbarkeit des Benutzers und die Bereitschaft zur Kommunikation dar. 
  
### <a name="technical-requirements"></a>Technische Anforderungen

Sofortnachrichten und Anwesenheitsnachrichten werden immer auf Front-End-Pools und Standard Edition-Servern der Enterprise Edition ausgeführt. Informationen zu unterstützter Hardware, Betriebssystemen und Datenbanksoftware finden Sie unter  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and Infrastructure requirements for Skype for Business Server [2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Aktivieren der Kommunikation mit externen Benutzern

Sie können die Vorteile Ihrer Investition in Skype for Business Server erheblich erhöhen, indem Sie Ihren Benutzern die Kommunikation mit externen Benutzern ermöglichen. Externe Benutzer können Folgendes umfassen:
  
- Remotebenutzer: Die eigenen Benutzer Ihrer Organisation, wenn sie außerhalb Ihrer Firewalls arbeiten und laptops oder andere Skype for Business Server-Geräte verwenden.
    
- Partnerbenutzer: Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten, die auch Skype for Business Server ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen. 
    
- Skype-Benutzer: Skype for Business-Benutzer können hunderte Millionen von Benutzern über Skype mit Chat, Sprache und Video erreichen.
    
> [!NOTE]
> AOL, Yahoo und Google Talk werden nicht mehr unterstützt. 
  
> [!NOTE]
> Um eines oder alle dieser Szenarien zu aktivieren, müssen Sie einen Edgeserver bereitstellen, um die sichere Kommunikation zwischen Ihrer Skype for Business Server-Bereitstellung und externen Benutzern zu ermöglichen. Die Remotebenutzer und Benutzer ihrer Organisation in Verbundorganisationen können die Anwesenheits- und Kommunikationspräsenz der anderen Benutzer mithilfe von Imiten sehen. 
  
> [!NOTE]
> XMPP (Extensible Messaging and Presence Protocol) wird nur für Zertifizierungsszenarien der Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) unterstützt. 
  
### <a name="archiving-im-content"></a>Archivieren von Inhalten für Imitierung

Skype for Business Server bietet Funktionen, die Sie verwenden können, wenn Ihre Organisation die Compliancebestimmungen einhalten muss. Sie können die Archivierung verwenden, um den Inhalt von Nachrichten im Nachrichtennachrichten für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer zu archivieren, die Sie angeben. Weitere Informationen finden Sie unter ["Planen der Archivierung in Skype for Business Server".](archiving/archiving.md) 
  
Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange-Daten in die Archivierung von Skype for Business Server-Daten integrieren und mit einem einzigen Tool beide Arten archivierter Daten durchsuchen. Weitere Informationen finden Sie unter [Konfigurieren von Skype for Business Server für die Verwendung Exchange Server Archivierung.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)
  
### <a name="topologies-and-components"></a>Topologien und Komponenten

Für Instant Messaging (IM) und Anwesenheit sind nur diese Komponenten erforderlich:
  
- Die Front-End-Server Ihrer Organisation (auch als Pool bezeichnet) oder ein Standard Edition-Server. Instant Messaging- und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert. Weitere Informationen zu Front-End-Pooltopologien und -verwaltung finden Sie unter "Hohe Verfügbarkeit und Verwaltung [des Front-End-Pools".](high-availability-and-disaster-recovery/high-availability.md)
    
- Ein Lastenausgleich, wenn Sie über einen Front-End-Pool der Enterprise Edition verfügen.
    
### <a name="supported-collocation"></a>Unterstützte Kollokation

Kollokation ist definiert als ein einzelner Server oder eine Gruppe von Servern mit mehreren installierten Rollen. Weitere Informationen zur Kollokation finden Sie unter ["Topology Basics for Skype for Business Server".](topology-basics/topology-basics.md) 
  

