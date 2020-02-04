---
title: 'Lync Server 2013: Infrastruktur öffentlicher Schlüssel'
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
ms.openlocfilehash: 9b205699e9efd896a157654f5c1fb200e34087fc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infrastruktur öffentlicher Schlüssel für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-13_

Microsoft lync Server 2013 stützt sich auf Zertifikate für die Serverauthentifizierung und die Einrichtung einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen. Der Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 und Windows Server 2003 Public-Key-Infrastruktur (PKI) bietet die Infrastruktur für die Erstellung und Validierung dieser Vertrauenskette.

Zertifikate sind digitale IDs. Sie identifizieren einen Server nach Namen und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen auf einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgegeben sein, die für Clients und andere Server, die sich mit dem Server verbinden, vertrauenswürdig ist. Wenn sich der Server nur mit anderen Clients und Servern in einem privaten Netzwerk verbindet, kann die Zertifizierungsstelle eine Unternehmenszertifizierungsstelle sein. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.

Selbst wenn die Informationen auf dem Zertifikat gültig sind, muss es eine Möglichkeit zum Überprüfen geben, ob der Server, der das Zertifikat präsentiert, tatsächlich der Server ist, der von dem Zertifikat repräsentiert wird. Hier kommt die Windows PKI ins Spiel.

Jedes Zertifikat ist mit einem öffentlichen Schlüssel verbunden. Der auf dem Zertifikat benannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur ihm bekannt ist. Ein sich verbindender Client oder Server verwendet den öffentlichen Schlüssel, um eine beliebige Information zu verschlüsseln und sendet diese an den Server. Wenn der Server die Information entschlüsselt und als Klartext zurückgibt, kann die sich verbindende Entität sicher sein, dass der Server über den privaten Schlüssel zum Zertifikat verfügt und es sich daher um den auf dem Zertifikat benannten Server handelt.

<div>


> [!NOTE]  
> Nicht alle öffentlichen CAS erfüllen die Anforderungen von lync Server 2013-Zertifikaten. Wir empfehlen Ihnen, für öffentliche Zertifikate auf die Auflistung von zertifizierten öffentlichen Zertifizierungsstellenanbietern zurückzugreifen. Ausführliche Informationen finden Sie unter Unified Communications Certificate Partners <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>unter.



</div>

<div>

## <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte

Lync Server 2013 erfordert, dass alle Server Zertifikate mindestens einen CRL-Verteilungspunkt (Certificate Revocation List) enthalten. Sperrlisten-Verteilungspunkte sind Standorte, von denen Zertifikatsperrlisten heruntergeladen werden können, um zu prüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, gesperrt wurde und es sich noch im Gültigkeitszeitraum befindet. Ein Sperrlisten-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL aufgeführt und ist normalerweise sicheres HTTP.

</div>

<div>

## <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung

Lync Server 2013 erfordert, dass alle Serverzertifikate zur Unterstützung der erweiterten Schlüsselverwendung (EKU) für die Serverauthentifizierung verwendet werden. Die Konfiguration des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat für den Zweck der Serverauthentifizierung gültig ist. Diese EKU ist wesentlich für MTLS. Es ist möglich, mehr als einen Eintrag in der EKU zu haben und damit das Zertifikat für mehrere Zwecke zu aktivieren.

<div>


> [!NOTE]  
> Die EKU für die Client Authentifizierung ist für ausgehende MTLS-Verbindungen von Live Communications Server 2003 und Live Communications Server 2005 erforderlich, aber nicht mehr erforderlich. Diese EKU muss jedoch auf Edgeserver vorhanden sein, die mithilfe öffentlicher Chat Verbindungen mit AOL verbunden sind.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

