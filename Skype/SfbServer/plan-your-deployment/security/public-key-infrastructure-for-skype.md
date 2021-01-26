---
title: Public Key Infrastructure for Skype for Business Server
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
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server basiert auf Zertifikaten für die Serverauthentifizierung und zum Einrichten einer Vertrauenskette zwischen Clients und Servern und zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2-, Windows Server 2012-, Windows Server 2008 R2- und Windows Server 2008 Public Key Infrastructure (PKI) stellt die Infrastruktur zum Einrichten und Überprüfen dieser Vertrauenskette zur Verfügung.
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832145"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Public Key Infrastructure for Skype for Business Server
 
Skype for Business Server basiert auf Zertifikaten für die Serverauthentifizierung und zum Einrichten einer Vertrauenskette zwischen Clients und Servern und zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2-, Windows Server 2012-, Windows Server 2008 R2- und Windows Server 2008 Public Key Infrastructure (PKI) stellt die Infrastruktur zum Einrichten und Überprüfen dieser Vertrauenskette zur Verfügung.
  
Zertifikate sind digitale IDs. Sie identifizieren einen Server namentlich und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen auf einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgestellt werden, die von Clients oder anderen Servern, die eine Verbindung mit dem Server herstellen, als vertrauenswürdig eingestuft wird. Wenn der Server nur mit Clients und Servern in einem privaten Netzwerk eine Verbindung herstellt, kann eine Unternehmenszertifizierungsstelle verwendet werden. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.
  
Selbst wenn das Zertifikat gültige Informationen enthält, muss überprüft werden können, ob es sich bei dem Server, der das Zertifikat vorlegt, auch tatsächlich um den Server handelt, für den das Zertifikat ausgestellt wurde. Hier kommt die Public Key-Infrastruktur von Windows ins Spiel.
  
Jedes Zertifikat ist mit einem öffentlichen Schlüssel verknüpft. Der im Zertifikat genannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur dem Server bekannt ist. Ein Client oder Server, der eine Verbindung herstellt, verwendet den öffentlichen Schlüssel zum Verschlüsseln zufällig gewählter Informationen und sendet diese an den Server. Wenn der Server die Informationen entschlüsselt und im Nur-Text-Format zurücksendet, kann die Einheit, die eine Verbindung herstellt, sicher sein, dass der Server über den privaten Schlüssel für das Zertifikat verfügt und es sich somit um den im Zertifikat genannten Server handelt.
  
> [!NOTE]
> Nicht alle öffentlichen Zertifizierungsas erfüllen die Anforderungen von Skype for Business Server-Zertifikaten. Sehen Sie am besten in der Liste der zertifizierten Anbieter für öffentliche Zertifizierungsstellen nach. Weitere Informationen finden Sie unter [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte

Skype for Business Server erfordert, dass alle Serverzertifikate einen oder mehrere Zertifikatsperrlistenverteilungspunkte (Certificate Revocation List, CRL) enthalten. CrL Distribution Points (CDPs) sind Speicherorte, von denen CRLs heruntergeladen werden können, um zu überprüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, nicht widerrufen wurde und sich das Zertifikat noch innerhalb des Gültigkeitszeitraums befindet. Ein CrL-Verteilungspunkt ist in den Eigenschaften des Zertifikats als URL angegeben und ist in der Regel sicheres HTTP.
  
## <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung

Skype for Business Server erfordert, dass alle Serverzertifikate die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für die Serverauthentifizierung unterstützen. Das Konfigurieren des Felds "EKU" für die Serverauthentifizierung bedeutet, dass das Zertifikat für die Authentifizierung von Servern gültig ist. Diese EKU ist für MTLS unerlässlich. Es ist möglich, mehr als einen Eintrag in der EKU zu verwenden, wodurch das Zertifikat für mehrere Zwecke aktiviert wird.
  

