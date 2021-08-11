---
title: Verschlüsselung für Skype for Business Server
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
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Der gesamte Datenverkehr zwischen den Servern erfordert MTLS, und zwar unabhängig davon, ob die Daten innerhalb des internen Netzwerks verbleiben oder den internen Netzwerkumkreis verlassen. Beim Verbinden von Skype for Business Server mit IPPBX-Systemen oder SIP-Trunks von Drittanbietern ist TLS optional, wird jedoch dringend zwischen dem Vermittlungsserver und dem Mediengateway empfohlen. Wenn TLS für diesen Link konfiguriert ist, ist MTLS erforderlich. Aus diesem Grund muss das Gateway mit einem Zertifikat von einer für den Vermittlungsserver vertrauenswürdigen Zertifizierungsstelle konfiguriert werden.
ms.openlocfilehash: a315b26f14db16759eb2c6c6fc9d6d6562060221efdd1b642f259aeecffadc7b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289533"
---
# <a name="encryption-for-skype-for-business-server"></a>Verschlüsselung für Skype for Business Server
 
Skype for Business Server verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Der gesamte Datenverkehr zwischen den Servern erfordert MTLS, und zwar unabhängig davon, ob die Daten innerhalb des internen Netzwerks verbleiben oder den internen Netzwerkumkreis verlassen. Wenn Sie Skype for Business Server mit IPPBX-Systemen oder SIP-Trunks von Drittanbietern verbinden, ist TLS optional, wird jedoch dringend zwischen dem Vermittlungsserver und dem Mediengateway empfohlen. Wenn TLS für diesen Link konfiguriert ist, ist MTLS erforderlich. Aus diesem Grund muss das Gateway mit einem Zertifikat von einer für den Vermittlungsserver vertrauenswürdigen Zertifizierungsstelle konfiguriert werden.
  
> [!NOTE]
> 2014 wurde eine Sicherheitsempfehlung zu SSL 3.0 veröffentlicht. Das Deaktivieren von SSL 3.0 in Skype for Business Server 2015 wird unterstützt. Weitere Informationen zur Sicherheitsempfehlung finden Sie unter [Deaktivieren von SSL 3.0 in Lync Server 2013 und Skype for Business Server 2015.](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)<br/>
**Sicherheitshinweis:** Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet Skype for Business Server 2015 den Clients TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge an: **TLS 1.2 , TLS 1.1, TLS 1.0**. TLS ist ein wichtiger Aspekt von Skype for Business Server 2015 und daher erforderlich, um eine unterstützte Umgebung aufrechtzuerhalten.<br/>
**Sicherheitshinweis:** Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet Skype for Business Server 2019 Clients TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge an: **TLS 1.3, TLS 1.2.** TLS ist ein wichtiger Aspekt von Skype for Business Server 2019 und daher erforderlich, um eine unterstützte Umgebung aufrechtzuerhalten. 
  
In der folgenden Tabelle werden die Protokollanforderungen für die einzelnen Datenverkehrstypen dargestellt. 
  
**Schutz des Datenverkehrs**

|**Datenverkehrstyp**|**Geschützt durch**|
|:-----|:-----|
|Server-zu-Server  <br/> |Mtls  <br/> |
|Client-zu-Server  <br/> |TLS  <br/> |
|Sofortnachrichten und Anwesenheit  <br/> |TLS  <br/> |
|Audio-, Video- und Desktopfreigabe von Medien  <br/> |Srtp  <br/> |
|Desktopfreigabe (Signaldaten)  <br/> |TLS  <br/> |
|Webkonferenzen  <br/> |TLS  <br/> |
|Herunterladen von Besprechungsinhalten und Adressbüchern, Erweiterung der Verteilergruppe  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Medienverschlüsselung

Der Mediendatenverkehr wird mit Secure RTP (SRTP) verschlüsselt, einem Profil von Real-Time Transport Protocol (RTP), das Vertraulichkeit, Authentifizierung und Replay-Angriffsschutz für RTP-Datenverkehr bereitstellt. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Mediationsserver und seinem internen Next Hop fließen, ebenfalls mit SRTP verschlüsselt. Medien, die in beide Richtungen zwischen dem Vermittlungsserver und einem Mediengateway fließen, werden optional verschlüsselt und empfohlen. Der Vermittlungsserver kann die Verschlüsselung für das Mediengateway unterstützen, aber das Gateway muss MTLS und den Speicher eines Zertifikats unterstützen.
  
> [!NOTE]
> Weitere Informationen zum Einrichten einer Hybridbereitstellung finden Sie unter Planen der [Hybridkonnektivität.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)
  
## <a name="fips"></a>Fips

Skype for Business Server und Microsoft Exchange Server 2016 unterstützen FIPS-Algorithmen (Federal Information Processing Standard) 140-2, wenn die Windows Server-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert sind. Um die FIPS-Unterstützung zu implementieren, müssen Sie jeden Server konfigurieren, auf dem Skype for Business Server ausgeführt wird, um ihn zu unterstützen.
