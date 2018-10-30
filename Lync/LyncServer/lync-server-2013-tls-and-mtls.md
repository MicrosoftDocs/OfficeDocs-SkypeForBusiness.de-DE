---
title: TLS und MTLS für Lync Server 2013
TOCTitle: TLS und MTLS für Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59679135
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# TLS und MTLS für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Die Protokolle Transport Layer Security (TLS) und Mutual Transport Layer Security (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet. Microsoft Lync Server 2013 verwendet diese zwei Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen Servern findet über die MTLS. SIP-Kommunikation vom Client zum Server über TLS statt.

Mit TLS können Benutzer über ihre Clientsoftware die Lync Server 2013-Server authentifizieren, mit denen sie sich verbinden. In einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Damit das Zertifikat gültig ist, muss es von einer Zertifizierungsstelle ausgestellt sein, die auch für den Client vertrauenswürdig ist, und der DNS-Name des Servers muss dem DNS-Namen auf dem Zertifikat entsprechen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an nicht von anderen vertrauenswürdigen Servern oder Clients angezweifelt. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten als TLS-basiert zugeordnet werden.

Server-zu-Server-Verbindungen nutzen MTLS für die gegenseitige Authentifizierung. Bei einer MTLS-Verbindung tauchen der Server, von dem eine Nachricht stammt, und der Server, der diese empfängt, Zertifikate von einer beiderseits vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate beweisen jedem Server die Identität des anderen. In Lync Server 2013-Bereitstellungen werden Zertifikate, die von der Unternehmenszertifizierungsstelle ausgestellt, in ihrem Gültigkeitszeitraum und nicht von der ausstellenden Zertifizierungsstelle gesperrt sind, automatisch von allen internen Clients und Servern als gültig betrachtet, da alle Mitglieder einer Active Directory-Domäne der Unternehmenszertifizierungsstelle in dieser Domäne vertrauen. In Verbundszenarien muss die ausstellende Zertifizierungsstelle für beide Verbundpartner vertrauenswürdig sein. Jeder Partner kann auf Wunsch eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch für den anderen Partner vertrauenswürdig ist. Diese Vertrauenswürdigkeit wird am einfachsten erreicht, wenn die Edgeserver das Zertifikat der Stammzertifizierungsstelle des Partners in den vertrauenswürdigen Stammzertifizierungsstellen hat oder eine Zertifizierungsstelle von Drittanbietern verwendet wird, die für beide Beteiligte vertrauenswürdig ist.

TLS und MTLS tragen dazu bei, Abhöraktionen und Man-in-the-Middle-Angriffe zu verhindern. Bei einem Man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten ohne Wissen der Beteiligten über den Computer des Angreifers um. TLS und die Lync Server 2013-Spezifikation vertrauenswürdiger Server (nur die in Topologie-Generator angegebenen) mindern das Risiko von Man-in-the-Middle-Angriffen teilweise auf der Anwendungsebene, indem sie eine End-to-End-Verschlüsselung verwenden, die über die Public Key-Kryptografie zwischen den zwei Endpunkten koordiniert wird, und ein Angreifer bräuchte ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel, das zudem auf den Namen des Diensts ausgestellt ist, mit dem der Client kommuniziert, um die Kommunikation zu entschlüsseln. Letztendlich aber müssen Sie die bewährten Methoden für Ihre Infrastruktur anwenden (in diesem Fall Firmen-DNS). Lync Server 2013 geht davon aus, dass der DNS-Server auf dieselbe Weise wie Domänencontroller und globale Kataloge vertrauenswürdig ist, aber DNS bietet gewissen Schutzmaßnahmen vor DNS-Hijack-Angriffen, da verhindert wird, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den gespooften Namen reagiert.

In der folgenden Abbildung finden Sie eine allgemeine Übersicht, wie Lync Server 2013 MTLS für die Erstellung eines Netzwerks vertrauenswürdiger Server verwendet.

**Vertrauenswürdige Verbindungen in einem Lync Server-Netzwerk**

![Verwendung von MTLS](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "Verwendung von MTLS")

