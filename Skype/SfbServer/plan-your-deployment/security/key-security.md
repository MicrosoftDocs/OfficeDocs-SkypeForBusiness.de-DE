---
title: Wichtige Sicherheitsfunktionen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server umfasst verschiedene Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentralisierte Speicherung von Konfigurationsdaten.
ms.openlocfilehash: cd86d1ac404cd2fe487f6f9369cc73df0d72c52f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296889"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Wichtige Sicherheitsfunktionen in Skype for Business Server
 
Skype for Business Server umfasst verschiedene Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentralisierte Speicherung von Konfigurationsdaten. 
  
Dieser Artikel bietet eine allgemeine Übersicht über die Sicherheit von Skype for Business Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Wichtige Sicherheitsfunktionen in Skype for Business Server

Sicherheit ist ein äußerst umfangreiches Thema. Sicherheit erreicht alle Funktionen von Skype for Business Server sowie Datenbanken, Dienste und Hardware, die ein Skype for Business Server-Ökosystem ausmachen. In diesem Artikel werden einige der Features in Skype for Business Server erläutert, die speziell auf Sicherheit ausgelegt sind.
  
### <a name="planning-and-design-tools"></a>Planungs- und Entwurfstools

Skype for Business Server bietet zwei Tools, um die Planung und das Design zu vereinfachen und die Möglichkeit der MIS-Konfiguration von Skype for Business Server-Komponenten zu verringern. 
  
- Das **Topologie-Planungs Tool** automatisiert einen Großteil des Topologie-Entwurfsprozesses. Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren, der das Tool ist, das zum Installieren der einzelnen Server mit Skype for Business Server erforderlich ist.
    
- Der **Topologie-Generator** speichert alle Konfigurationsinformationen im zentralen Verwaltungsspeicher.
    
Details zu diesen Tools finden Sie unter [Skype for Business Server-Verwaltungstools](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Zentraler Verwaltungsspeicher (Central Management Store, CMS)

In Skype for Business Server sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die zum definieren, einrichten, verwalten, verwalten, beschreiben und betreiben einer Skype for Business Server-Bereitstellung erforderlich sind. Darüber hinaus überprüft er die Daten, um eine konsistente Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch "nicht synchrone" Probleme beseitigt werden. 
  
Schreibgeschützte Kopien der Daten werden an alle Server in der Topologie repliziert, Edgeserver und Survivable Branch Appliances eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig unter dem Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden. 
  
### <a name="server-to-server-authentication"></a>Server-zu-Server-Authentifizierung

In Skype for Business Server kann die Authentifizierung zwischen Servern mithilfe des Open Authorization (OAuth)-Protokolls konfiguriert werden. So können Sie beispielsweise Skype for Business Server für die Authentifizierung bei einem Server konfigurieren, auf dem Microsoft Exchange Server 2016 ausgeführt wird. Mit dem OAuth-Protokoll können sich der Skype for Business-Server und der Microsoft Exchange-Server gegenseitig vertrauen. Auf diese Weise können die Produkte nahtlos integriert werden. Ausführliche Informationen finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell-basierte und webbasierte Verwaltungsschnittstelle

Skype for Business Server bietet eine leistungsfähige Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Sie enthält Cmdlets für die Verwaltung der Sicherheit und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Nutzern nicht versehentlich oder unwissentlich ausgeführt werden können. Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden. Details zur Unterstützung der Windows PowerShell-Verwaltung in Skype for Business Server finden Sie unter [Skype for Business Server-Verwaltungsshell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Rollenbasierte Zugriffssteuerung (RBAC)

Skype for Business Server bietet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), mit der Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards gewährleisten können. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen. Skype for Business Server bietet die Möglichkeit, eine neue Rolle zu erstellen und auch die Möglichkeit, eine vorhandene Rolle zu ändern. 
  
## <a name="network-address-translation-nat"></a>Netzwerkadressenübersetzung (Network Address Translation, NAT)

Skype for Business Server unterstützt nicht die Verwendung der Netzwerkadressübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edge-Servers, aber er unterstützt das Platzieren der externen Schnittstelle des Access Edge-Diensts, des Webkonferenz-Edgedienst und des A/V-Edgedienst. hinter einem Router oder Firewall, der Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeserver-Topologien ausführt. Mehrere Edgeserver hinter einem Hardware-Lastenausgleichsmodul können NAT nicht verwenden. Wenn mehrere Edgeserver für Ihre externen Schnittstellen NAT verwenden, ist ein DNS-Lastenausgleich (Domain Name System) erforderlich. Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserver-Pool reduzieren. Ausführliche Informationen finden Sie unter [Edge-Server Szenarien in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Wenn Sie mit einem Verbundunternehmen zusammenarbeiten, das über eine Bereitstellung von Microsoft Office Communications Server 2007 verfügt, und wenn Audio-/Videofunktionen zwischen Ihrem Unternehmen und dem Verbundunternehmen unterstützt werden sollen, entsprechen die Portanforderungen denen für die bereitgestellten älteren Edgeserver. Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Verbundpartner seine Edgeserver auf Skype for Business Server aktualisiert. Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Vereinfachte Zertifikate für Edgeserver

Der Bereitstellungs-Assistent kann Antragstellernamen (SNs) und alternative Antragstellernamen (SANs) automatisch ausfüllen. Dadurch reduziert sich das Risiko von unnötigen und potenziell unsicheren Einträgen.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Trustworthy Computing Security Development Lifecycle (SDL)

Skype for Business Server wurde in Übereinstimmung mit dem [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL) entwickelt und entwickelt.
  
- **Vertrauenswürdig nach Entwurf** Der erste Schritt beim Erstellen eines sichereren Unified Communications-Systems war das Entwerfen von Bedrohungsmodellen und das Testen der einzelnen Features, wie Sie entworfen wurden. Außerdem führt Microsoft Tests außerhalb des konzipierten Verhaltens durch, um Sicherheitsrisiken zu finden, die sich aus einem nicht erwarteten Produktverhalten ergeben. Viele sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt übernommen wird. Natürlich ist es nicht möglich, so zu entwerfen, dass alle unbekannten Sicherheitsbedrohungen beseitigt werden. Es gibt kein System, für das vollständige Sicherheit garantiert werden kann. Da die Produktentwicklung allerdings von Anfang an sichere Designprinzipien umfasste, umfasst Skype for Business Server branchenübliche Sicherheitstechnologien als grundlegende Komponente seiner Architektur.
    
- **Standardmäßig vertrauenswürdig** Standardmäßig werden Netzwerkkommunikationen in Skype for Business Server verschlüsselt. Da alle Serverzertifikate und Kerberos-Authentifizierung, TLS, SRTP (Secure Real-Time Transport Protocol) und andere Industriestandard-Verschlüsselungstechniken verwenden, einschließlich AES-Verschlüsselung (128-Bit Advanced Encryption Standard), praktisch alle Skype für Business Server-Daten sind im Netzwerk geschützt. Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern mit Skype for Business Server, damit jede Serverrolle nur die Dienste ausführt und nur über die Berechtigungen für diese Dienste verfügt, die für die Serverrolle geeignet sind.
    
- **Vertrauenswürdig durch Bereitstellung** Alle Skype for Business Server-Dokumentation umfasst bewährte Methoden und Empfehlungen, mit denen Sie die optimalen Sicherheitsstufen für Ihre Bereitstellung ermitteln und konfigurieren und die Sicherheitsrisiken bei der Aktivierung nicht standardmäßiger Optionen bewerten können.
    

