---
title: Public Key-Infrastruktur für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server basiert auf Zertifikaten für die Serverauthentifizierung und zum Einrichten einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 und Windows Server 2008 Public Key Infrastructure (PKI) stellt die Infrastruktur zum Einrichten und Überprüfen dieser Vertrauenskette bereit.
ms.openlocfilehash: 61381840d6c82ce26f0b8e7e5210ebd37c3532c0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840957"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Public Key-Infrastruktur für Skype for Business Server
 
Skype for Business Server basiert auf Zertifikaten für die Serverauthentifizierung und zum Einrichten einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen. Die Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 und Windows Server 2008 Public Key Infrastructure (PKI) stellt die Infrastruktur zum Einrichten und Überprüfen dieser Vertrauenskette bereit.
  
Zertifikate sind digitale IDs. Sie identifizieren einen Server namentlich und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen in einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgestellt werden, die von Clients oder anderen Servern, die eine Verbindung mit dem Server herstellen, als vertrauenswürdig eingestuft wird. Wenn der Server nur mit Clients und Servern in einem privaten Netzwerk eine Verbindung herstellt, kann eine Unternehmenszertifizierungsstelle verwendet werden. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.
  
Selbst wenn das Zertifikat gültige Informationen enthält, muss überprüft werden können, ob es sich bei dem Server, der das Zertifikat vorlegt, auch tatsächlich um den Server handelt, für den das Zertifikat ausgestellt wurde. Hier kommt die Public Key-Infrastruktur von Windows ins Spiel.
  
Jedes Zertifikat ist mit einem öffentlichen Schlüssel verknüpft. Der im Zertifikat genannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur dem Server bekannt ist. Ein Client oder Server, der eine Verbindung herstellt, verwendet den öffentlichen Schlüssel zum Verschlüsseln zufällig gewählter Informationen und sendet diese an den Server. Wenn der Server die Informationen entschlüsselt und im Nur-Text-Format zurücksendet, kann die Einheit, die eine Verbindung herstellt, sicher sein, dass der Server über den privaten Schlüssel für das Zertifikat verfügt und es sich somit um den im Zertifikat genannten Server handelt.
  
> [!NOTE]
> Nicht alle öffentlichen Zertifizierungsstellen erfüllen die Anforderungen von Skype for Business Server Zertifikaten. Sehen Sie am besten in der Liste der zertifizierten Anbieter für öffentliche Zertifizierungsstellen nach. 
  
## <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte

Skype for Business Server erfordert, dass alle Serverzertifikate einen oder mehrere CRL-Verteilungspunkte (Certificate Revocation List) enthalten. CRL-Verteilungspunkte (CRL Distribution Points, CDPs) sind Speicherorte, von denen CRLs heruntergeladen werden können, um zu überprüfen, ob das Zertifikat seit der Ausstellung nicht widerrufen wurde und sich das Zertifikat noch innerhalb des Gültigkeitszeitraums befindet. Ein CRL-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL angegeben und ist in der Regel sicheres HTTP.
  
## <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung

Skype for Business Server erfordert, dass alle Serverzertifikate die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) zum Zweck der Serverauthentifizierung unterstützen. Das Konfigurieren des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat zum Authentifizieren von Servern gültig ist. Diese EKU ist für MTLS unerlässlich. Es ist möglich, mehrere Einträge in der EKU zu haben, wodurch das Zertifikat für mehrere Zwecke aktiviert wird.
  

