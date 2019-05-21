---
title: Infrastruktur öffentlicher Schlüssel für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server setzt auf Zertifikate für die Serverauthentifizierung und die Einrichtung einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 und die Windows Server 2008 Public Key-Infrastruktur (PKI) stellen die Infrastruktur für die Erstellung und Validierung dieser Vertrauenskette bereit.
ms.openlocfilehash: 381afce84c1a58d15187547c9cb8fd6f98e84790
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296854"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infrastruktur öffentlicher Schlüssel für Skype for Business Server
 
Skype for Business Server setzt auf Zertifikate für die Serverauthentifizierung und die Einrichtung einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 und die Windows Server 2008 Public Key-Infrastruktur (PKI) stellen die Infrastruktur für die Erstellung und Validierung dieser Vertrauenskette bereit.
  
Zertifikate sind digitale IDs. Sie identifizieren einen Server nach Namen und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen auf einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgegeben sein, die für Clients und andere Server, die sich mit dem Server verbinden, vertrauenswürdig ist. Wenn sich der Server nur mit anderen Clients und Servern in einem privaten Netzwerk verbindet, kann die Zertifizierungsstelle eine Unternehmenszertifizierungsstelle sein. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.
  
Selbst wenn die Informationen auf dem Zertifikat gültig sind, muss es eine Möglichkeit zum Überprüfen geben, ob der Server, der das Zertifikat präsentiert, tatsächlich der Server ist, der von dem Zertifikat repräsentiert wird. Hier kommt die Windows PKI ins Spiel.
  
Jedes Zertifikat ist mit einem öffentlichen Schlüssel verbunden. Der auf dem Zertifikat benannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur ihm bekannt ist. Ein sich verbindender Client oder Server verwendet den öffentlichen Schlüssel, um eine beliebige Information zu verschlüsseln und sendet diese an den Server. Wenn der Server die Information entschlüsselt und als Klartext zurückgibt, kann die sich verbindende Entität sicher sein, dass der Server über den privaten Schlüssel zum Zertifikat verfügt und es sich daher um den auf dem Zertifikat benannten Server handelt.
  
> [!NOTE]
> Nicht alle öffentlichen CAS erfüllen die Anforderungen von Skype for Business Server-Zertifikaten. Wir empfehlen Ihnen, für öffentliche Zertifikate auf die Auflistung von zertifizierten öffentlichen Zertifizierungsstellenanbietern zurückzugreifen. Ausführliche Informationen finden Sie unter [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte

Für Skype for Business Server müssen alle Serverzertifikate mindestens einen CRL-Verteilungspunkt (Certificate Revocation List) enthalten. Sperrlisten-Verteilungspunkte sind Standorte, von denen Zertifikatsperrlisten heruntergeladen werden können, um zu prüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, gesperrt wurde und es sich noch im Gültigkeitszeitraum befindet. Ein Sperrlisten-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL aufgeführt und ist normalerweise sicheres HTTP.
  
## <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung

Für Skype for Business Server müssen alle Serverzertifikate zur Unterstützung der erweiterten Schlüsselverwendung (EKU) für die Serverauthentifizierung verwendet werden. Die Konfiguration des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat für den Zweck der Serverauthentifizierung gültig ist. Diese EKU ist wesentlich für MTLS. Es ist möglich, mehr als einen Eintrag in der EKU zu haben und damit das Zertifikat für mehrere Zwecke zu aktivieren.
  

