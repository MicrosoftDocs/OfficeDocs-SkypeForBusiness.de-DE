---
title: TLS und MTLS für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Die Protokolle „Transport Layer Security“ (TLS) und „Mutual Transport Layer Security“ (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype for Business Server verwendet diese beiden Protokolle, um das Netzwerk von vertrauenswürdigen Servern zu erstellen und sicherzustellen, dass alle Kommunikationen über dieses Netzwerk verschlüsselt sind. Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt. SIP-Kommunikation vom Client zum Server findet über TLS statt.
ms.openlocfilehash: fe8619dd499388472612c67ddf1801a027ed1e5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296847"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS und MTLS für Skype for Business Server
 
Die Protokolle „Transport Layer Security“ (TLS) und „Mutual Transport Layer Security“ (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Skype for Business Server verwendet diese beiden Protokolle, um das Netzwerk von vertrauenswürdigen Servern zu erstellen und sicherzustellen, dass alle Kommunikationen über dieses Netzwerk verschlüsselt sind. Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt. SIP-Kommunikation vom Client zum Server findet über TLS statt.
  
TLS ermöglicht Benutzern über Ihre Client Software, die Skype for Business Server-Server zu authentifizieren, mit denen Sie eine Verbindung herstellen. In einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Damit das Zertifikat gültig ist, muss es von einer Zertifizierungsstelle ausgestellt sein, die auch für den Client vertrauenswürdig ist, und der DNS-Name des Servers muss dem DNS-Namen auf dem Zertifikat entsprechen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an nicht von anderen vertrauenswürdigen Servern oder Clients angezweifelt. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten als TLS-basiert zugeordnet werden.
  
Server-zu-Server-Verbindungen nutzen MTLS für die gegenseitige Authentifizierung. Bei einer MTLS-Verbindung tauschen der Server, von dem eine Nachricht stammt, und der Server, der diese empfängt, Zertifikate von einer beiderseits vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate beweisen jedem Server die Identität des anderen. In Skype for Business Server-Bereitstellungen werden von der Unternehmenszertifizierungsstelle ausgestellte Zertifikate, die sich während Ihres Gültigkeitszeitraums befinden und von der ausstellenden Zertifizierungsstelle nicht widerrufen werden, automatisch für alle internen Clients und Server als gültig erachtet, weil alle Mitglieder eines aktiven Verzeichnisdomäne Vertrauen der Unternehmenszertifizierungsstelle in dieser Domäne. In Verbundszenarien muss die ausstellende Zertifizierungsstelle für beide Verbundpartner vertrauenswürdig sein. Jeder Partner kann auf Wunsch eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch für den anderen Partner vertrauenswürdig ist. Diese Vertrauensstellung erfolgt am einfachsten durch die Edgeserver, die das Stammzertifikat der Partner-Zertifizierungsstelle in ihren vertrauenswürdigen Stammzertifizierungsstellen besitzen, oder durch Verwendung einer Drittanbieter-Zertifizierungsstelle, die von beiden Parteien als vertrauenswürdig eingestuft wird.
  
TLS und MTLS verhindern Lauschangriffe und Man-in-the-Middle-Angriffe. Bei einem man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten über den Computer des Angreifers ohne das Wissen einer Partei neu. TLS-und Skype for Business Server-Spezifikation von vertrauenswürdigen Servern (nur die im Topologie-Generator angegebenen) minimieren das Risiko eines man-in-the-Middle-Angriffs teilweise auf der Anwendungsebene mithilfe von End-to-End-Verschlüsselung, die mit dem öffentlichen Schlüssel koordiniert wird Kryptografie zwischen den beiden Endpunkten, und ein Angreifer müsste über ein gültiges und vertrauenswürdiges Zertifikat mit dem zugehörigen privaten Schlüssel verfügen und für den Namen des Diensts ausgestellt werden, mit dem der Client kommuniziert, um die Kommunikation zu entschlüsseln. Letztendlich müssen Sie jedoch die besten Sicherheitsmethoden für Ihre Netzwerkinfrastruktur (in diesem Fall Corporate DNS) befolgen. Für Skype for Business Server wird davon ausgegangen, dass der DNS-Server auf die gleiche Weise als vertrauenswürdig eingestuft wird wie Domänencontroller und globale Kataloge, doch DNS bietet eine Schutzebene gegen DNS-Hijack-Angriffe, indem verhindert wird, dass der Server eines Angreifers reagiert. erfolgreich auf eine Anforderung an den gefälschten Namen.
  

