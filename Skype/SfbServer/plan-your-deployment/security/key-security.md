---
title: Wichtige Sicherheitsfeatures in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server umfasst mehrere Sicherheitsfeatures, z. B. die Server-zu-Server-Authentifizierung, die rollenbasierte Zugriffssteuerung und die zentrale Speicherung von Konfigurationsdaten.
ms.openlocfilehash: 1cf1e5f2866a3d03d77604afc83061b420658468
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104221"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Wichtige Sicherheitsfeatures in Skype for Business Server
 
Skype for Business Server umfasst mehrere Sicherheitsfeatures, z. B. die Server-zu-Server-Authentifizierung, die rollenbasierte Zugriffssteuerung und die zentrale Speicherung von Konfigurationsdaten. 
  
Dieser Artikel bietet eine Übersicht über die Sicherheit von Skype for Business Server auf hoher Ebene. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Wichtige Sicherheitsfeatures in Skype for Business Server

Sicherheit ist ein sehr breites Thema. Die Sicherheit erreicht alle Funktionen von Skype for Business Server sowie Datenbanken, Dienste und Hardware, die ein Skype for Business Server-Ökosystem bilden. In diesem Artikel werden einige der Features in Skype for Business Server beschrieben, die speziell für die Sicherheit entwickelt wurden.
  
### <a name="planning-and-design-tools"></a>Planungs- und Entwurfstools

Skype for Business Server bietet zwei Tools, um die Planung und den Entwurf zu erleichtern und die Wahrscheinlichkeit zu verringern, dass Skype for Business Server-Komponenten falsch konfiguriert werden. 
  
- **Das Topologieplanungstool** automatisiert einen großen Teil des Topologieentwurfsprozesses. Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren. Dabei handelt es sich um das Tool, das zum Installieren der einzelnen Server mit Skype for Business Server erforderlich ist.
    
- **Der Topologie-Generator** speichert alle Konfigurationsinformationen im zentralen Verwaltungsspeicher.
    
Weitere Informationen zu diesen Tools finden Sie unter [Skype for Business Server Management Tools](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Zentraler Verwaltungsspeicher

In Skype for Business Server sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierte Speicherung der Daten, die zum Definieren, Einrichten, Warten, Verwalten, Beschreiben und Betreiben einer Skype for Business Server-Bereitstellung erforderlich sind. Darüber hinaus werden die Daten überprüft, um eine konsistente Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten werden im zentralen Verwaltungsspeicher vorgenommen, wodurch "Out-of-Sync"-Probleme beseitigt werden. 
  
Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig im Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden. 
  
### <a name="server-to-server-authentication"></a>Server-zu-Server-Authentifizierung

In Skype for Business Server kann die Authentifizierung zwischen Servern mithilfe des Open Authorization (OAuth)-Protokolls konfiguriert werden. Beispielsweise können Sie Skype for Business Server für die Authentifizierung bei einem Server konfigurieren, auf dem Microsoft Exchange Server 2016 ausgeführt wird. Mithilfe des OAuth-Protokolls können sich Skype for Business Server und Microsoft Exchange Server gegenseitig vertrauen. Dadurch können die Produkte nahtlos integriert werden. Weitere Informationen finden Sie [unter Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell-basierte Verwaltung und webbasierte Verwaltungsschnittstelle

Skype for Business Server bietet eine leistungsstarke Verwaltungsschnittstelle, die auf der Windows PowerShell Befehlszeilenschnittstelle baut. Sie enthält Cmdlets für die Verwaltung der Sicherheit, und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Benutzern nicht versehentlich oder unwissentlich ausgeführt werden können. Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden. Weitere Informationen zur Windows PowerShell in Skype for Business Server finden Sie unter [Skype for Business Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Role-Based Access Control (RBAC)

Skype for Business Server bietet eine rollenbasierte Zugriffssteuerung (RBAC), mit der Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards einhalten können. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Benutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen. Skype for Business Server bietet die Möglichkeit, eine neue Rolle zu erstellen und auch eine vorhandene Rolle zu ändern. 
  
## <a name="network-address-translation-nat"></a>Network Address Translation (NAT)

Skype for Business Server unterstützt die Verwendung der Netzwerkadressenübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edgeservers nicht, unterstützt jedoch das Platzieren der externen Schnittstelle des Zugriffs-Edgediensts, des Webkonferenz-Edgediensts und des A/V-Edgediensts hinter einem Router oder einer Firewall, der die Netzwerkadressenübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeservertopologien durchführt. Mehrere Edgeserver hinter einem Hardwaregerät zum Lastenausgleich können NAT nicht verwenden. Wenn mehrere Edgeserver NAT auf ihren externen Schnittstellen verwenden, ist ein LASTENAUSGLEICH (Domain Name System, DNS) erforderlich. Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserverpool reduzieren. Weitere Informationen finden Sie [unter Edgeserverszenarien in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Wenn Sie mit Unternehmen zusammenarbeiten, die über eine Microsoft Office Communications Server 2007-Bereitstellung verfügen und Audio/Video zwischen Ihrem Unternehmen und dem Verbundunternehmen verwenden müssen, gelten die Portanforderungen für die ältere Version der bereitgestellten Edgeserver. Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Verbundpartner seine Edgeserver auf Skype for Business Server aktualisiert. Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Vereinfachte Zertifikate für Edgeserver

Der Bereitstellungs-Assistent kann automatisch Betreffnamen (Subject Names, SNs) und alternative Subject-Namen (Subject Alternative Names, SANs) auffüllen, wodurch die Möglichkeit reduziert wird, unnötige und potenziell unsichere Einträge zu verwenden.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Trustworthy Computing Security Development Lifecycle (SDL)

Skype for Business Server wurde in Übereinstimmung mit dem [Microsoft Trustworthy Computing Security Development Lifecycle (SDL)](/previous-versions/ms995349(v=msdn.10)) entworfen und entwickelt.
  
- **Vertrauenswürdig nach Entwurf** Der erste Schritt beim Erstellen eines sichereren Unified Communications-Systems war das Entwerfen von Bedrohungsmodellen und das Testen der einzelnen Features, wie sie entworfen wurden. Darüber hinaus führt Microsoft Tests außerhalb des entworfenen Verhaltens durch, um Sicherheitsrisiken zu finden, die sich aus unerwartetem Produktverhalten ergeben. Mehrere sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt aufgenommen wird. Natürlich ist es nicht möglich, alle unbekannten Sicherheitsbedrohungen vorherzusehen. Es gibt kein System ohne Sicherheitslücken. Da bei der Produktentwicklung jedoch von Anfang an Prinzipien für sicheres Design berücksichtigt wurden, enthält Skype for Business Server standardmäßige Sicherheitstechnologien als grundlegenden Bestandteil der Architektur.
    
- **Vertrauenswürdig standardmäßig** Standardmäßig ist die Netzwerkkommunikation in Skype for Business Server verschlüsselt. Da alle Server Zertifikate und Kerberos-Authentifizierung, TLS, Secure Real-Time Transport Protocol (SRTP) und andere branchenübliche Verschlüsselungstechniken verwenden, einschließlich 128-Bit Advanced Encryption Standard (AES)-Verschlüsselung, sind praktisch alle Skype for Business Server-Daten im Netzwerk geschützt. Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern, auf denen Skype for Business Server ausgeführt wird, sodass jede Serverrolle nur die Dienste ausgeführt und nur über die berechtigungen verfügt, die sich auf diese Dienste bezogen, die für die Serverrolle geeignet sind.
    
- **Vertrauenswürdig nach Bereitstellung** Die gesamte Skype for Business Server-Dokumentation enthält bewährte Methoden und Empfehlungen, mit deren Hilfe Sie die optimalen Sicherheitsstufen für Ihre Bereitstellung ermitteln und konfigurieren und die Sicherheitsrisiken der Aktivierung nicht standardmäßiger Optionen bewerten können.
