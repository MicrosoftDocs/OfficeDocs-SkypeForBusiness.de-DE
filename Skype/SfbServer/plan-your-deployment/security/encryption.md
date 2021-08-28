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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Der gesamte Datenverkehr zwischen den Servern erfordert MTLS, und zwar unabhängig davon, ob die Daten innerhalb des internen Netzwerks verbleiben oder den internen Netzwerkumkreis verlassen. Beim Verbinden von Skype for Business Server mit IPPBX-Systemen oder SIP-Trunks von Drittanbietern ist TLS optional, wird jedoch dringend zwischen dem Vermittlungsserver und dem Mediengateway empfohlen. Wenn TLS für diesen Link konfiguriert ist, ist MTLS erforderlich. Aus diesem Grund muss das Gateway mit einem Zertifikat von einer für den Vermittlungsserver vertrauenswürdigen Zertifizierungsstelle konfiguriert werden.
ms.openlocfilehash: ec87f7d2a32e02e8dcd4a4c489b77d2add3ac43a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586857"
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
|Server-zu-Server  <br/> |MTLS  <br/> |
|Client-zu-Server  <br/> |TLS  <br/> |
|Sofortnachrichten und Anwesenheit  <br/> |TLS  <br/> |
|Audio-, Video- und Desktopfreigabe von Medien  <br/> |SRTP  <br/> |
|Desktopfreigabe (Signaldaten)  <br/> |TLS  <br/> |
|Webkonferenzen  <br/> |TLS  <br/> |
|Herunterladen von Besprechungsinhalten und Adressbüchern, Erweiterung der Verteilergruppe  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Medienverschlüsselung

Der Mediendatenverkehr wird mit Secure RTP (SRTP) verschlüsselt, einem Profil von Real-Time Transport Protocol (RTP), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Mediationsserver und seinem internen Next Hop fließen, ebenfalls mit SRTP verschlüsselt. Medien, die in beide Richtungen zwischen dem Vermittlungsserver und einem Mediengateway fließen, werden optional verschlüsselt und empfohlen. Der Vermittlungsserver kann die Verschlüsselung für das Mediengateway unterstützen, aber das Gateway muss MTLS und den Speicher eines Zertifikats unterstützen.
  
> [!NOTE]
> Weitere Informationen zum Einrichten einer Hybridbereitstellung finden Sie unter Planen der [Hybridkonnektivität.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)
  
## <a name="fips"></a>FIPS

Skype for Business Server und Microsoft Exchange Server 2016 arbeiten mit Unterstützung für FIPS-Algorithmen (Federal Information Processing Standard) 140-2, wenn die Windows Server-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert sind. Um FIPS-Unterstützung zu implementieren, müssen Sie jeden Server konfigurieren, auf dem Skype for Business Server ausgeführt wird, um ihn zu unterstützen.
