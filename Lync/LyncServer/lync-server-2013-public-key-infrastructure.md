---
title: Public Key-Infrastruktur für Lync Server 2013
TOCTitle: Public Key-Infrastruktur für Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59679133
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Public Key-Infrastruktur für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2013 nutzt Zertifikate für die Serverauthentifizierung und die Einrichtung einer Vertrauenskette zwischen Clients und Servern und zwischen den verschiedenen Serverrollen. Die Public Key-Infrastruktur (PKI) von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 und Windows Server 2003 stellt die Infrastruktur für die Einrichtung und Validierung dieser Vertrauenskette bereit.

Zertifikate sind digitale IDs. Sie identifizieren einen Server nach Namen und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen auf einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgegeben sein, die für Clients und andere Server, die sich mit dem Server verbinden, vertrauenswürdig ist. Wenn sich der Server nur mit anderen Clients und Servern in einem privaten Netzwerk verbindet, kann die Zertifizierungsstelle eine Unternehmenszertifizierungsstelle sein. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.

Selbst wenn die Informationen auf dem Zertifikat gültig sind, muss es eine Möglichkeit zum Überprüfen geben, ob der Server, der das Zertifikat präsentiert, tatsächlich der Server ist, der von dem Zertifikat repräsentiert wird. Hier kommt die Windows PKI ins Spiel.

Jedes Zertifikat ist mit einem öffentlichen Schlüssel verbunden. Der auf dem Zertifikat benannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur ihm bekannt ist. Ein sich verbindender Client oder Server verwendet den öffentlichen Schlüssel, um eine beliebige Information zu verschlüsseln und sendet diese an den Server. Wenn der Server die Information entschlüsselt und als Klartext zurückgibt, kann die sich verbindende Entität sicher sein, dass der Server über den privaten Schlüssel zum Zertifikat verfügt und es sich daher um den auf dem Zertifikat benannten Server handelt.


> [!NOTE]
> Nicht alle öffentlichen Zertifizierungsstellen sind kompatibel mit den Anforderungen von Lync Server&nbsp;2013-Zertifikaten. Wir empfehlen Ihnen, für öffentliche Zertifikate auf die Auflistung von zertifizierten öffentlichen Zertifizierungsstellenanbietern zurückzugreifen. Ausführliche Informationen finden Sie unter „Partner für Unified Communications-Zertifikate“ unter <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.



## Sperrlisten-Verteilungspunkte

Lync Server 2013 erfordert, dass alle Serverzertifikate mindestens einen Sperrlisten-Verteilungspunkt enthalten. Sperrlisten-Verteilungspunkte sind Standorte, von denen Zertifikatsperrlisten heruntergeladen werden können, um zu prüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, gesperrt wurde und es sich noch im Gültigkeitszeitraum befindet. Ein Sperrlisten-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL aufgeführt und ist normalerweise sicheres HTTP.

## Erweiterte Schlüsselverwendung

Lync Server 2013 erfordert, dass alle Serverzertifikate die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für den Zweck der Serverauthentifizierung unterstützen. Die Konfiguration des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat für den Zweck der Serverauthentifizierung gültig ist. Diese EKU ist wesentlich für MTLS. Es ist möglich, mehr als einen Eintrag in der EKU zu haben und damit das Zertifikat für mehrere Zwecke zu aktivieren.


> [!NOTE]
> Die EKU für die Clientauthentifizierung wird für ausgehende MTLS-Verbindungen von Live Communications Server 2003 und Live Communications Server 2005 benötigt, ist aber nicht mehr erforderlich. Dennoch muss diese EKU auf Edgeservern vorhanden sein, die sich über öffentliche Chatverbindungen mit AOL verbinden.


