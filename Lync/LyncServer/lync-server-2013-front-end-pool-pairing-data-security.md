---
title: 'Lync Server 2013: Datensicherheit beim Bilden von Front-End-Poolpaaren'
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
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Datensicherheit beim Bilden von Front-End-Poolpaaren in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-10-07_

Bei dem Sicherungsdienst handelt es sich um einen in lync Server 2013 eingeführten Datenreplikationsmechanismus, der Benutzerdaten und Konferenzinhalte zwischen zwei gekoppelten Front-End-Pools kontinuierlich über zwei Rechenzentren für Disaster Recovery überträgt. Die Benutzerdaten enthalten Benutzer-SIP-URIs sowie Kontaktlisten und-Einstellungen. Konferenzinhalte umfassen Microsoft PowerPoint 2010-Uploads sowie Whiteboards, die in Konferenzen verwendet werden. Aus dem Quell Pool werden Benutzerdaten und Konferenzinhalte aus dem lokalen Speicher exportiert, gezippt, in den Ziel Pool übertragen, wo Sie entpackt und in den lokalen Speicher importiert werden. Der Sicherungsdienst geht davon aus, dass die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks besteht, das vor dem Internet geschützt ist. Sie verschlüsseln weder die übertragenen Daten zwischen den beiden Rechenzentren, noch ist Sie nativ in einem sicheren Protokoll wie HTTPS gekapselt. Deshalb ist ein man-in-the-Middle-Angriff durch internes Personal innerhalb des Unternehmensnetzwerks möglich.

<div>

## <a name="evaluating-security-risks"></a>Auswerten von Sicherheitsrisiken

Alle Unternehmen, die lync Server 2013 in mehreren Rechenzentren bereitstellen und das Disaster Recovery-Feature verwenden, müssen sicherstellen, dass der Verkehr zwischen Datencentern durch das Unternehmens Intranet geschützt ist. Unternehmen, die sich um internen Angriffsschutz kümmern, müssen die Kommunikationsverbindungen zwischen den Rechenzentren sichern.

Die Annahme, dass Rechenzentren eines Unternehmens hinter dem Unternehmens Intranet geschützt sind, ist Standard. Es gibt viele andere Arten vertraulicher Unternehmensdaten, die zwischen diesen Rechenzentren übertragen werden. Die IT-Infrastruktur des Unternehmens ist mit einem unsicheren Risiko behaftet, wenn diese quer Datencenter-Links nicht geschützt sind.

Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere sind die vom Sicherungsdienst (wie SIP-URIs) verfügbar gemachten Benutzerdaten im Allgemeinen für alle Mitarbeiter im Unternehmen über andere Mittel wie das globale Adressbuch von Exchange oder einer anderen Verzeichnis Software verfügbar. Daher sollte der Fokus auf dem Sichern des WAN zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen den beiden gekoppelten Pools verwendet wird.

</div>

<div>

## <a name="mitigating-security-risks"></a>Verringern von Sicherheitsrisiken

Es gibt viele Möglichkeiten, den Sicherheitsschutz für den Backup-Dienst Datenverkehr zu verbessern, vom Einschränken des Zugriffs auf die Rechenzentren bis hin zum Sichern des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen verfügen Unternehmen, die lync Server 2013 bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur. Für Unternehmen, die nach Anleitungen suchen, bietet Microsoft eine Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur. Dies impliziert jedoch nicht, dass es sich um die einzige Lösung handelt, und es impliziert auch nicht, dass es sich um die bevorzugte Lösung für lync Server handelt. Es wird empfohlen, dass Unternehmenskunden die Lösung auswählen, die ihren spezifischen Anforderungen entspricht, basierend auf Ihrer IT-Sicherheitsinfrastruktur und-Anforderungen. Die Microsoft-Beispiellösung verwendet IPSec und Gruppenrichtlinien für die Server-und Domänenisolierung. Ausführliche Informationen finden Sie [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)unter. Wenden Sie sich bei Fragen und Kommentaren an SecWish@Microsoft.com.

Eine weitere mögliche Lösung besteht in der Verwendung von IPSec ausschließlich zur Sicherung der vom Sicherungsdienst selbst gesendeten Daten. Wenn Sie sich für diese Methode entscheiden, konfigurieren Sie die IPSec-Regeln für das SMB-Protokoll auf den folgenden Servern, wenn Pool A und Pool B zwei verbundene Front-End-Pools sind.

  - Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A an den von Pool B verwendeten Dateispeicher.

  - Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B an den von Pool A verwendeten Dateispeicher.

<div>


> [!WARNING]  
> IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene wie etwa SSL/TLS gedacht. Ein Vorteil der Verwendung von IPsec liegt darin, dass es Sicherheit für Netzwerkdatenverkehr für vorhandene Apps bereitstellen kann, ohne dass diese geändert werden müssen. Unternehmen, die einfach nur den Transport zwischen den beiden Rechenzentren schützen möchten, sollten sich bei den Herstellern der jeweiligen Netzwerkhardware erkundigen, wie sie mit den betreffenden Geräten sichere WAN-Verbindungen einrichten können.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

