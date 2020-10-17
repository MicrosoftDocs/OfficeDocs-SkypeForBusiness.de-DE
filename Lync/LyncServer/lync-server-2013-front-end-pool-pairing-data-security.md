---
title: 'Lync Server 2013: Front-End-Pool koppeln von Datensicherheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500722"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Front-End-Pool koppeln von Datensicherheit in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-10-07_

Der Sicherungsdienst ist ein in lync Server 2013 eingeführter Datenreplikationsmechanismus, der Benutzerdaten und Konferenzinhalte zwischen zwei gekoppelten Front-End-Pools kontinuierlich über zwei Rechenzentren zur Notfallwiederherstellung überträgt. Die Benutzerdaten enthalten Benutzer-SIP-URIs sowie Kontaktlisten und-Einstellungen. Konferenzinhalte umfassen Microsoft PowerPoint 2010 Uploads sowie Whiteboards, die in Konferenzen verwendet werden. Aus dem Quell Pool werden Benutzerdaten und Konferenzinhalte aus dem lokalen Speicher exportiert, gezippt, an den Ziel Pool übertragen, wo er entpackt und in den lokalen Speicher importiert wird. Der Sicherungsdienst geht davon aus, dass sich die Kommunikationsverbindungzwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks befindet, das vor dem Internet geschützt ist. Die übertragenen Daten zwischen den beiden Rechenzentren werden nicht verschlüsselt, noch ist Sie nativ in ein sicheres Protokoll wie HTTPS gekapselt. Daher ist ein man-in-the-Middle-Angriff von internen Mitarbeitern innerhalb des Unternehmensnetzwerks möglich.

<div>

## <a name="evaluating-security-risks"></a>Bewerten von Sicherheitsrisiken

Jedes Unternehmen, das lync Server 2013 in mehreren Rechenzentren bereitstellt und die Notfallwiederherstellungsfunktion verwendet, muss sicherstellen, dass der datenbankübergreifende Datenverkehr durch das Unternehmens Intranet geschützt ist. Unternehmen, die ihren Datenverkehr vor internen Angriffen schützen möchten, müssen die Kommunikationsverbindungen zwischen den Rechenzentren schützen.

Es ist eine weit verbreitete Annahme, dass Rechenzentren eines Unternehmens hinter dem firmeneigenen Intranet geschützt sind. Viele andere Arten von vertraulichen Unternehmensdaten werden ebenfalls zwischen diesen Rechenzentren übertragen. Die IT-Infrastruktur des Unternehmens ist massiv gefährdet, wenn diese rechenzentrenübergreifenden Verbindungen nicht geschützt werden.

Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die Benutzerdaten, die vom Sicherungsdienst verfügbar gemacht werden (z. B. SIP-URIs), sind für alle Mitarbeiter im Unternehmen über andere Mittel wie etwa das globale Adressbuch von Exchange oder andere Verzeichnissoftware allgemein verfügbar. Daher sollte der Schwerpunkt auf dem Schutz des WANs zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen einem Poolpaar verwendet wird.

</div>

<div>

## <a name="mitigating-security-risks"></a>Minimieren von Sicherheitsrisiken

Es gibt viele Möglichkeiten, den Sicherheitsschutz für den Sicherungsdienst Datenverkehr zu verbessern, angefangen beim Einschränken des Zugriffs auf die Rechenzentren bis hin zum Sichern des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen verfügen Unternehmen, die lync Server 2013 bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur. Für Unternehmen, die nach Anleitungen suchen, stellt Microsoft die Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur bereit. Dies impliziert jedoch nicht, dass es sich um die einzige Lösung handelt, auch nicht, dass es die bevorzugte Lösung für lync Server ist. Es wird empfohlen, dass Unternehmenskunden basierend auf Ihrer IT-Sicherheitsinfrastruktur und-Anforderungen die Lösung auswählen, die ihren spezifischen Anforderungen entspricht. In der Microsoft-Beispiellösung werden IPSec-und Gruppenrichtlinien für die Server-und Domänenisolierung verwendet. Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) . Wenden Sie sich bei Fragen und Kommentaren an SecWish@Microsoft.com.

Eine weitere mögliche Lösung besteht in der Verwendung von IPSec, um die vom Sicherungsdienst selbst gesendeten Daten zu schützen. Wenn Sie diese Methode auswählen, sollten Sie die IPSec-Regeln für das SMB-Protokoll für die folgenden Server konfigurieren, wobei Pool a und Pool B zwei gekoppelte Front-End-Pools sind.

  - Der SMB-Dienst (TCP/445) von jeder Front-End-Server in Pool a auf die Dateispeicher, die von Pool B verwendet wird.

  - Der SMB-Dienst (TCP/445) von jeder Front-End-Server in Pool B zu der Dateispeicher, die von Pool A verwendet wird.

<div>


> [!WARNING]  
> IPSec ist nicht als Ersatz für die Sicherheit auf Anwendungsebene wie SSL/TLS gedacht. Ein Vorteil der Verwendung von IPSec besteht darin, dass Sie die Sicherheit von Netzwerkdatenverkehr für vorhandene Anwendungen bereitstellen kann, ohne Sie ändern zu müssen. Unternehmen, die lediglich den Transport zwischen den beiden Rechenzentren sichern möchten, sollten ihre jeweiligen Netzwerkhardware Anbieter über die Möglichkeiten zum Einrichten sicherer WAN-Verbindungen mithilfe der Geräte des Herstellers konsultieren.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

