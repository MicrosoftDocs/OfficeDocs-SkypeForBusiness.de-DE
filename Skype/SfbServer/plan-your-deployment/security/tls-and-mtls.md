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
description: Transport Layer Security (TLS) und Mutual Transport Layer Security (MTLS)-Protokolle bieten verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype for Business Server verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen den Servern erfolgt über MTLS. Die SIP-Kommunikation von Client zu Server erfolgt über TLS.
ms.openlocfilehash: bdb0ca586614e81d6d7e5e93b253349c9d388e6b9312931d08a75e2a0359f6e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349897"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS und MTLS für Skype for Business Server
 
Transport Layer Security (TLS) und Mutual Transport Layer Security (MTLS)-Protokolle bieten verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype for Business Server verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen den Servern erfolgt über MTLS. Die SIP-Kommunikation von Client zu Server erfolgt über TLS.
  
MIT TLS können Benutzer über ihre Clientsoftware die Skype for Business Server Server authentifizieren, mit denen sie eine Verbindung herstellen. Bei einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Ein gültiges Zertifikat muss von einer auch für den Client vertrauenswürdigen Zertifizierungsstelle ausgegeben worden sein, und der DNS-Name des Servers muss mit dem DNS-Namen des Zertifikats übereinstimmen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel zu verschlüsseln, die zur Kommunikation verwendet werden sollen, damit nur der ursprüngliche Besitzer des Zertifikats den privaten Schlüssel zum Entschlüsseln der Kommunikationsinhalte verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig, und im weiteren Verlauf wird keine Authentifizierung von anderen vertrauenswürdigen Servern oder Clients angefordert. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten auf TLS-Basis zugeordnet werden.
  
Server-zu-Server-Verbindungen basieren für die gegenseitige Authentifizierung auf MTLS. Bei einer MTLS-Verbindung tauscht der Server, der eine Nachricht stammt, und der Empfangende Server Zertifikate von einer gegenseitig vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate bestätigen die Identität der einzelnen Server für den anderen Server. In Skype for Business Server Bereitstellungen werden von der Unternehmenszertifizierungsstelle ausgestellte Zertifikate, die während ihres Gültigkeitszeitraums ausgestellt wurden und nicht von der ausstellenden Zertifizierungsstelle widerrufen werden, automatisch von allen internen Clients und Servern als gültig betrachtet, da alle Mitglieder einer Active Directory-Domäne der Enterprise Zertifizierungsstelle in dieser Domäne vertrauen. In Verbundszenarien muss die ausstellende Zertifizierungsstelle von beiden Verbundpartnern als vertrauenswürdig eingestuft werden. Jeder Partner kann bei Bedarf eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch vom anderen Partner als vertrauenswürdig eingestuft wird. Diese Vertrauensstellung wird am einfachsten durch die Edgeserver erreicht, die über das Zertifikat der Stammzertifizierungsstelle des Partners in ihren vertrauenswürdigen Stammzertifizierungsstellen verfügen, oder durch die Verwendung einer Drittanbieterzertifizierungsstelle, die von beiden Parteien als vertrauenswürdig eingestuft wird.
  
TLS und MTLS tragen dazu bei, Lauschangriffe und Man-in-the-Middle-Angriffe zu verhindern. Bei einem Man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten ohne Wissen einer der beiden Parteien über den Computer des Angreifers um. TLS und Skype for Business Server Spezifikation vertrauenswürdiger Server (nur die im Topologie-Generator angegebenen) verringern das Risiko eines Man-in-the-Middle-Angriffs teilweise auf der Anwendungsebene durch die Verwendung der End-to-End-Verschlüsselung, die mithilfe der Public Key-Kryptografie zwischen den beiden Endpunkten koordiniert wird, und ein Angreifer müsste über ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel verfügen und an den Namen des Diensts ausgegeben werden, mit dem der Client die Kommunikation entschlüsseln möchte. Letztendlich müssen Sie jedoch bewährte Sicherheitsmethoden mit Ihrer Netzwerkinfrastruktur (in diesem Fall Unternehmens-DNS) befolgen. Skype for Business Server geht davon aus, dass der DNS-Server auf die gleiche Weise vertrauenswürdig ist, wie Domänencontroller und globale Kataloge vertrauenswürdig sind. DNS bietet jedoch ein Maß an Schutz vor DNS-Angriffen, indem verhindert wird, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den gefälschten Namen reagiert.
  

