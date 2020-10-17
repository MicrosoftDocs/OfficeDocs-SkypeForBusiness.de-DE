---
title: 'Lync Server 2013: Public Key-Infrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cee633f877a34dcf2ec0fd0b98891c62faf0bad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512412"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a>Öffentliche Schlüsselinfrastruktur für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-13_

Microsoft lync Server 2013 basiert auf Zertifikaten für die Serverauthentifizierung und zum Einrichten einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2-, Windows Server 2012-, Windows Server 2008 R2-, Windows Server 2008-und Windows Server 2003 Public Key-Infrastruktur (PKI) stellt die Infrastruktur zum Einrichten und validieren dieser Vertrauenskette bereit.

Zertifikate sind digitale IDs. Sie identifizieren einen Server namentlich und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen in einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgestellt werden, die von Clients oder anderen Servern als vertrauenswürdig eingestuft wird, die eine Verbindung mit dem Server herstellen. Wenn der Server nur mit Clients und Servern in einem privaten Netzwerk eine Verbindung herstellt, kann eine Unternehmenszertifizierungsstelle verwendet werden. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.

Selbst wenn das Zertifikat gültige Informationen enthält, muss überprüft werden können, ob es sich bei dem Server, der das Zertifikat vorlegt, auch tatsächlich um den Server handelt, für den das Zertifikat ausgestellt wurde. Hier kommt die Public Key-Infrastruktur von Windows ins Spiel.

Jedes Zertifikat ist mit einem öffentlichen Schlüssel verknüpft. Der im Zertifikat genannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur dem Server bekannt ist. Ein Client oder Server, der eine Verbindung herstellt, verwendet den öffentlichen Schlüssel zum Verschlüsseln zufällig gewählter Informationen und sendet diese an den Server. Wenn der Server die Informationen entschlüsselt und im Nur-Text-Format zurücksendet, kann die Einheit, die eine Verbindung herstellt, sicher sein, dass der Server über den privaten Schlüssel für das Zertifikat verfügt und es sich somit um den im Zertifikat genannten Server handelt.

<div>


> [!NOTE]  
> Nicht alle öffentlichen CAS entsprechen den Anforderungen lync Server 2013 Zertifikate. Sehen Sie am besten in der Liste der zertifizierten Anbieter für öffentliche Zertifizierungsstellen nach. Ausführliche Informationen finden Sie unter Unified Communications Certificate Partners unter <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> .



</div>

<div>

## <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte

Lync Server 2013 erfordert, dass alle Server Zertifikate mindestens einen Zertifikatsperrlisten-Verteilungspunkt (Certificate Revocation List, CRL) enthalten. CRL-Verteilungspunkte (CDPs) sind Standorte, aus denen Zertifikatsperrlisten heruntergeladen werden können, um zu überprüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, nicht widerrufen wurde und sich das Zertifikat noch innerhalb des Gültigkeitszeitraums befindet. Ein CRL-Verteilungs Pfad wird in den Eigenschaften des Zertifikats als URL vermerkt und ist in der Regel sicheres HTTP.

</div>

<div>

## <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung

Lync Server 2013 erfordert, dass alle Serverzertifikate zur Unterstützung der EKU (Enhanced Key Usage, EKU) für die Serverauthentifizierung verwendet werden. Das Konfigurieren des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat zum Zweck der Authentifizierung von Servern gültig ist. Diese EKU ist für MTLS unerlässlich. Es ist möglich, mehr als einen Eintrag in der EKU zu haben, sodass das Zertifikat für mehrere Zwecke aktiviert werden kann.

<div>


> [!NOTE]  
> Die Clientauthentifizierungs-EKU ist für ausgehende MTLS-Verbindungen von Live Communications Server 2003 und Live Communications Server 2005 erforderlich, wird jetzt aber nicht mehr benötigt. Diese EKU muss jedoch auf Edgeservern vorhanden sein, die über öffentliche Instant Messaging-Dienste eine Verbindung zu AOL herstellen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

