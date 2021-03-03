---
title: TLS und MTLS für Skype for Business Server
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
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Die Protokolle TLS (Transport Layer Security) und MTLS (Mutual Transport Layer Security) bieten verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype for Business Server verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und um sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen den Servern erfolgt über MTLS. Die SIP-Kommunikation von Client zu Server erfolgt über TLS.
ms.openlocfilehash: 7acc75ef35a9fe9c3f155ca31f06ac38df371e37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832015"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS und MTLS für Skype for Business Server
 
Die Protokolle TLS (Transport Layer Security) und MTLS (Mutual Transport Layer Security) bieten verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype for Business Server verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und um sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen den Servern erfolgt über MTLS. Die SIP-Kommunikation von Client zu Server erfolgt über TLS.
  
Mit TLS können Benutzer über ihre Clientsoftware die Skype for Business Server-Server authentifizieren, mit denen sie eine Verbindung herstellen. Bei einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Ein gültiges Zertifikat muss von einer auch für den Client vertrauenswürdigen Zertifizierungsstelle ausgegeben worden sein, und der DNS-Name des Servers muss mit dem DNS-Namen des Zertifikats übereinstimmen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel zu verschlüsseln, die zur Kommunikation verwendet werden sollen, damit nur der ursprüngliche Besitzer des Zertifikats den privaten Schlüssel zum Entschlüsseln der Kommunikationsinhalte verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig, und im weiteren Verlauf wird keine Authentifizierung von anderen vertrauenswürdigen Servern oder Clients angefordert. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten auf TLS-Basis zugeordnet werden.
  
Server-zu-Server-Verbindungen verwenden MTLS für die gegenseitige Authentifizierung. Bei einer MTLS-Verbindung tauschen der Server, von dem eine Nachricht stammt, und der Server, der sie empfängt, Zertifikate von einer gegenseitig vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate belegen die Identität der einzelnen Server für den jeweils anderen Server. In Skype for Business Server-Bereitstellungen werden von der Unternehmens-CA ausgestellte Zertifikate, die während ihrer Gültigkeitsdauer ausgestellt und nicht von der ausstellenden Zertifizierungsstelle widerrufen wurden, automatisch von allen internen Clients und Servern als gültig betrachtet, da alle Mitglieder einer Active Directory-Domäne der Unternehmens-CA in dieser Domäne vertrauen. In Verbundszenarien muss die ausstellende Zertifizierungsstelle von beiden Verbundpartnern als vertrauenswürdig eingestuft werden. Jeder Partner kann bei Bedarf eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch vom anderen Partner als vertrauenswürdig eingestuft wird. Diese Vertrauensstellung wird am besten durch die Edgeserver erreicht, die das Zertifikat der Stammzertifizierungsstelle des Partners in ihren vertrauenswürdigen Stammzertifizierungsstellen haben, oder durch die Verwendung einer Drittanbieterzertifizierungsstelle, die von beiden Parteien als vertrauenswürdig eingestuft wird.
  
TLS und MTLS verhindern sowohl Lauschangriffe als auch Man-in-the-Middle-Angriffe. Bei einem Man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten ohne wissen der beiden Parteien über den Computer des Angreifers um. Die TLS- und Skype for Business Server-Spezifikation vertrauenswürdiger Server (nur die im Topologie-Generator angegebenen) verringern das Risiko eines Man-in-the-Middle-Angriffs teilweise auf der Anwendungsebene, indem eine End-to-End-Verschlüsselung verwendet wird, die mithilfe der Kryptografie des öffentlichen Schlüssels zwischen den beiden Endpunkten koordiniert wird, und ein Angreifer müsste über ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel verfügen und an den Namen des Diensts ausgegeben werden, mit dem der Client kommuniziert, um die Kommunikation zu entschlüsseln. Letztendlich müssen Sie jedoch bewährte Sicherheitsmethoden für Ihre Netzwerkinfrastruktur (in diesem Fall Unternehmens-DNS) befolgen. Skype for Business Server geht davon aus, dass der DNS-Server auf die gleiche Weise vertrauenswürdig ist, wie Domänencontroller und globale Kataloge vertrauenswürdig sind. DNS bietet jedoch eine Schutzebene vor DNS-Hijack-Angriffen, indem verhindert wird, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den Gefälschten Namen reagiert.
  

