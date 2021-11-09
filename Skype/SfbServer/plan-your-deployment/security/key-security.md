---
title: Wichtige Sicherheitsfeatures in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server umfasst mehrere Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierter Zugriffssteuerung und zentraler Speicherung von Konfigurationsdaten.
ms.openlocfilehash: c70d997dc29166b05376bbd6c1bcd7886d1c176b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848388"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Wichtige Sicherheitsfeatures in Skype for Business Server
 
Skype for Business Server umfasst mehrere Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierter Zugriffssteuerung und zentraler Speicherung von Konfigurationsdaten. 
  
Dieser Artikel bietet eine allgemeine Übersicht über Skype for Business Server Sicherheit. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Wichtige Sicherheitsfeatures in Skype for Business Server

Sicherheit ist ein sehr breites Thema. Sicherheit erreicht alle Funktionen von Skype for Business Server sowie Datenbanken, Diensten und Hardware, die ein Skype for Business Server Ökosystem bilden. In diesem Artikel werden einige der Features in Skype for Business Server beschrieben, insbesondere für die Sicherheit.
  
### <a name="planning-and-design-tools"></a>Planungs- und Entwurfstools

Skype for Business Server bietet zwei Tools, um die Planung und das Design zu vereinfachen und die Wahrscheinlichkeit zu verringern, dass Skype for Business Server Komponenten falsch konfiguriert werden. 
  
- Das **Topologieplanungstool** automatisiert einen Großteil des Topologieentwurfsprozesses. Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren. Dies ist das Tool, das erforderlich ist, um jeden Server zu installieren, auf dem Skype for Business Server ausgeführt wird.
    
- **Der Topologie-Generator** speichert alle Konfigurationsinformationen im zentralen Verwaltungsspeicher.
    
Ausführliche Informationen zu diesen Tools finden Sie unter [Skype for Business Server Management Tools](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Zentraler Verwaltungsspeicher

In Skype for Business Server sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher bietet einen stabilen, schematisierten Speicher der Daten, die zum Definieren, Einrichten, Verwalten, Verwalten, Beschreiben und Ausführen einer Skype for Business Server Bereitstellung erforderlich sind. Darüber hinaus werden die Daten überprüft, um eine konsistente Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, sodass Synchronisierungsprobleme vermieden werden. 
  
Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig im Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden. 
  
### <a name="server-to-server-authentication"></a>Server-zu-Server-Authentifizierung

In Skype for Business Server kann die Authentifizierung zwischen Servern mithilfe des OAuth-Protokolls (Open Authorization) konfiguriert werden. Beispielsweise können Sie Skype for Business Server so konfigurieren, dass sie sich bei einem Server authentifizieren, auf dem Microsoft Exchange Server 2016 ausgeführt wird. Mithilfe des OAuth-Protokolls können sich die Skype for Business Server und die Microsoft Exchange Server gegenseitig vertrauen. Dies bietet die Möglichkeit, die Produkte nahtlos zu integrieren. Ausführliche Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server.](../../manage/authentication/server-to-server-and-partner-applications.md)
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell-basierte Verwaltung und webbasierte Verwaltungsschnittstelle

Skype for Business Server bietet eine leistungsstarke Verwaltungsschnittstelle, die auf der Windows PowerShell Befehlszeilenschnittstelle basiert. Sie enthält Cmdlets für die Verwaltung der Sicherheit, und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Benutzern nicht versehentlich oder unwissentlich ausgeführt werden können. Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden. Ausführliche Informationen zur Windows PowerShell-Verwaltungsunterstützung in Skype for Business Server finden Sie unter [Skype for Business Server Verwaltungsshell.](../../manage/management-shell.md) 
  
### <a name="role-based-access-control-rbac"></a>Role-Based-Zugriffssteuerung (RBAC)

Skype for Business Server bietet eine rollenbasierte Zugriffssteuerung (RBAC), mit der Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards einhalten können. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Benutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen. Skype for Business Server bietet die Möglichkeit, eine neue Rolle zu erstellen und auch eine vorhandene Rolle zu ändern. 
  
## <a name="network-address-translation-nat"></a>Netzwerkadressübersetzung (Network Address Translation, NAT)

Skype for Business Server unterstützt nicht die Verwendung der Netzwerkadressübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edgeservers, unterstützt jedoch das Platzieren der externen Schnittstelle des Zugriffs-Edgediensts, des Webkonferenz-Edgediensts und des A/V-Edgediensts hinter einem Router oder einer Firewall, der die Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeservertopologien durchführt. Mehrere Edgeserver hinter einem Hardwaregerät zum Lastenausgleich können keine NAT verwenden. Wenn mehrere Edgeserver NAT für ihre externen Schnittstellen verwenden, ist ein DNS-Lastenausgleich (Domain Name System) erforderlich. Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserverpool reduzieren. Ausführliche Informationen finden Sie [unter Edgeserverszenarien in Skype for Business Server.](../../plan-your-deployment/edge-server-deployments/scenarios.md)
  
> [!NOTE]
> Wenn Sie mit Unternehmen zusammenarbeiten, die über eine Microsoft Office Communications Server 2007-Bereitstellung verfügen und Audio/Video zwischen Ihrem Unternehmen und dem Verbundunternehmen verwenden müssen, gelten die Portanforderungen für die ältere Version der bereitgestellten Edgeserver. Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Verbundpartner seine Edgeserver auf Skype for Business Server aktualisiert. Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Vereinfachte Zertifikate für Edgeserver

Der Bereitstellungs-Assistent kann Automatisch Antragstellernamen (SNs) und alternative Antragstellernamen (SUBJECT Alternative Names, SANs) auffüllen, wodurch die Möglichkeit reduziert wird, unnötige und potenziell unsichere Einträge einzublenden.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Trustworthy Computing Security Development Lifecycle (SDL)

Skype for Business Server wurde in Übereinstimmung mit dem [Microsoft Trustworthy Computing Security Development Lifecycle](/previous-versions/ms995349(v=msdn.10)) (SDL) entworfen und entwickelt.
  
- **Vertrauenswürdig durch Design** Der erste Schritt beim Erstellen eines sichereren Unified Communications-Systems bestand darin, Bedrohungsmodelle zu entwerfen und jedes Feature so zu testen, wie es entworfen wurde. Darüber hinaus führt Microsoft Tests außerhalb des entworfenen Verhaltens durch, um Sicherheitsrisiken zu finden, die durch unerwartetes Produktverhalten entstehen. Mehrere sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt aufgenommen wird. Natürlich ist es nicht möglich, alle unbekannten Sicherheitsbedrohungen vorherzusehen. Es gibt kein System ohne Sicherheitslücken. Da bei der Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien verwendet wurden, Skype for Business Server branchenübliche Sicherheitstechnologien als grundlegenden Bestandteil ihrer Architektur integriert.
    
- **Standardmäßig vertrauenswürdig** Standardmäßig ist die Netzwerkkommunikation in Skype for Business Server verschlüsselt. Da alle Server Zertifikate und Kerberos-Authentifizierung, TLS, SRTP (Secure Real-Time Transport Protocol) und andere Verschlüsselungstechniken nach Branchenstandard verwenden, einschließlich der 128-Bit Advanced Encryption Standard (AES)-Verschlüsselung, werden praktisch alle Skype for Business Server Daten im Netzwerk geschützt. Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern, die Skype for Business Server ausgeführt werden, sodass jede Serverrolle nur die Dienste ausführt und nur über die Berechtigungen im Zusammenhang mit diesen Diensten verfügt, die für die Serverrolle geeignet sind.
    
- **Vertrauenswürdig durch Bereitstellung** Alle Skype for Business Server Dokumentation enthält bewährte Methoden und Empfehlungen, mit denen Sie die optimalen Sicherheitsstufen für Ihre Bereitstellung ermitteln und konfigurieren und die Sicherheitsrisiken der Aktivierung nicht standardmäßiger Optionen bewerten können.
