---
title: TLS und MTLS für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/5/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Die Protokolle „Transport Layer Security“ (TLS) und „Mutual Transport Layer Security“ (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype für Business Server 2015 verwendet diese beiden Protokolle zum Erstellen des Netzwerks vertrauenswürdiger Server und stellen Sie sicher, dass die gesamte Kommunikation über das Netzwerk verschlüsselt werden. Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt. SIP-Kommunikation vom Client zum Server findet über TLS statt.
ms.openlocfilehash: 1cc7554ab14e29fd85d2964d1323fccdfd4af604
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tls-and-mtls-for-skype-for-business-server-2015"></a>TLS und MTLS für Skype for Business Server 2015
 
Die Protokolle „Transport Layer Security“ (TLS) und „Mutual Transport Layer Security“ (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype für Business Server 2015 verwendet diese beiden Protokolle zum Erstellen des Netzwerks vertrauenswürdiger Server und stellen Sie sicher, dass die gesamte Kommunikation über das Netzwerk verschlüsselt werden. Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt. SIP-Kommunikation vom Client zum Server findet über TLS statt.
  
TLS können die Benutzer über ihre Clientsoftware, die Skype für Business Server 2015 Server authentifiziert, dem sie eine Verbindung herstellen. In einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Damit das Zertifikat gültig ist, muss es von einer Zertifizierungsstelle ausgestellt sein, die auch für den Client vertrauenswürdig ist, und der DNS-Name des Servers muss dem DNS-Namen auf dem Zertifikat entsprechen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an nicht von anderen vertrauenswürdigen Servern oder Clients angezweifelt. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten als TLS-basiert zugeordnet werden.
  
Server-zu-Server-Verbindungen nutzen MTLS für die gegenseitige Authentifizierung. Bei einer MTLS-Verbindung tauschen der Server, von dem eine Nachricht stammt, und der Server, der diese empfängt, Zertifikate von einer beiderseits vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate beweisen jedem Server die Identität des anderen. In Skype für Business Server 2015 Bereitstellungen, von der Unternehmenszertifizierungsstelle ausgegebenen Zertifikate, die während der ihre Gültigkeit Zeitraum und nicht durch die ausstellende Zertifizierungsstelle gesperrt werden automatisch als gültig betrachtet werden alle internen Clients und Servern, da alle Mitglieder einer aktiven Directory-Domäne der Unternehmenszertifizierungsstelle in dieser Domäne als vertrauenswürdig betrachtet. In Verbundszenarien muss die ausstellende Zertifizierungsstelle für beide Verbundpartner vertrauenswürdig sein. Jeder Partner kann auf Wunsch eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch für den anderen Partner vertrauenswürdig ist. Diese Vertrauensstellung wird durch das Zertifikat der Stammzertifizierungsstelle in ihre vertrauenswürdigen Stammzertifizierungsstellen des Partners mit Edge-Server oder durch Verwendung einer Drittanbieter-Zertifizierungsstelle, die beide Parteien vertrauenswürdig ist am einfachsten erreicht.
  
TLS und MTLS tragen zur Vermeidung von Abhör- und Man-in-the-middle-Angriffe zu verhindern. Bei einem Man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten über seinen Computer ohne Wissen der Kommunikationspartner. TLS und Skype für Business Server 2015 Angabe der vertrauenswürdigen Server (nur die angegebenen im Topologie-Generator) Risiko das einen Man-in-the middle-Angriff teilweise auf Anwendungsebene mithilfe von End-to-End-Verschlüsselung koordinierte mithilfe des öffentlichen Schlüssels Kryptografie zwischen zwei Endpunkte und ein Angreifer müsste über ein Zertifikat gültig und vertrauenswürdig mit dem entsprechenden privaten Schlüssel verfügen und auf den Namen des Diensts, dem der Client kommuniziert, um die Kommunikation zu entschlüsseln, ausgegeben. Schließlich müssen jedoch Sie bewährte Methoden für die Sicherheit mit Netzwerkinfrastruktur (in diesem Fall Unternehmens-DNS) befolgen. Skype für Business Server 2015 wird davon ausgegangen, dass der DNS-Server als vertrauenswürdig auf die gleiche Weise wie eingestuft wird Domänencontroller und globale Kataloge vertrauenswürdig sind, dass DNS ein Maß an Schutz vor Hijack-Angriffe über DNS bereitstellen, indem Sie verhindern, dass ein Angreifer Server reagiert erfolgreich auf eine Anforderung an den Namen mit Spoofing stammen.
  

