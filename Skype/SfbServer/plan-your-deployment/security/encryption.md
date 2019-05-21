---
title: Verschlüsselung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server verwendet TLS und MTLS zum Verschlüsseln von Sofortnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet. Bei der Verbindung von Skype for Business Server mit IPPBX-Systemen oder SIP-Stämmen von Drittanbietern ist TLS optional, aber sehr empfehlenswert zwischen dem Vermittlungsserver und dem Mediengateway. Wenn TLS auf dieser Verbindung konfiguriert ist, ist MTLS erforderlich. Daher muss das Gateway mit einem Zertifikat von einer Zertifizierungsstelle konfiguriert werden, die vom Vermittlungs Server als vertrauenswürdig eingestuft wird.
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296917"
---
# <a name="encryption-for-skype-for-business-server"></a>Verschlüsselung für Skype for Business Server
 
Skype for Business Server verwendet TLS und MTLS zum Verschlüsseln von Sofortnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet. Bei der Verbindung von Skype for Business Server mit IPPBX-Systemen oder SIP-Stämmen von Drittanbietern ist TLS optional, aber sehr empfehlenswert zwischen dem Vermittlungsserver und dem Mediengateway. Wenn TLS auf dieser Verbindung konfiguriert ist, ist MTLS erforderlich. Daher muss das Gateway mit einem Zertifikat von einer Zertifizierungsstelle konfiguriert werden, die vom Vermittlungs Server als vertrauenswürdig eingestuft wird.
  
> [!NOTE]
> Im Jahr 2014 wurde eine Sicherheitsempfehlung zu SSL 3.0 veröffentlicht. Das Deaktivieren von SSL 3,0 in Skype for Business Server 2015 ist eine unterstützte Option. Weitere Informationen zur Sicherheitsempfehlung finden Sie unter [Deaktivieren von SSL 3,0 in lync Server 2013 und Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Sicherheitshinweis:** Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet Skype for Business Server 2015 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge für Clients an: **TLS 1,2, TLS 1,1, TLS 1,0**. TLS ist ein wichtiger Aspekt von Skype for Business Server 2015 und ist daher erforderlich, um eine unterstützte Umgebung zu erhalten.<br/>
**Sicherheitshinweis:** Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet Skype for Business Server 2019 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge für Clients an: **TLS 1,3, TLS 1,2**. TLS ist ein wichtiger Aspekt von Skype for Business Server 2019 und ist daher erforderlich, um eine unterstützte Umgebung zu erhalten. 
  
In der folgenden Tabelle sind die Protokollanforderungen für jeden Datenverkehrstyp zusammengefasst. 
  
**Datenverkehrsschutz**

|**Datenverkehrstyp**|**Geschützt durch**|
|:-----|:-----|
|Server-zu-Server  <br/> |MTLS  <br/> |
|Client-zu-Server  <br/> |TLS  <br/> |
|Chat und Anwesenheit  <br/> |TLS  <br/> |
|Audio und Video und Desktopfreigaben von Medien  <br/> |SRTP  <br/> |
|Desktopfreigabe (Signal)  <br/> |TLS  <br/> |
|Webkonferenzen  <br/> |TLS  <br/> |
|Herunterladen von Besprechungsinhalten, Herunterladen des Adressbuchs, Erweiterung der Verteilergruppe  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Medienverschlüsselung

Mediendatenverkehr wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport-Protokoll), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Vermittlungsserver und seinem internen nächsten Hop übertragen werden, ebenfalls über SRTP verschlüsselt. Medien, die in beide Richtungen zwischen dem Vermittlungsserver und einem Mediengateway übertragen werden, werden optional verschlüsselt (empfohlen). Der Vermittlungsserver kann die Verschlüsselung an das Mediengateway unterstützen, aber das Gateway muss MTLS und das Speichern eines Zertifikats unterstützen.
  
> [!NOTE]
> Weitere Informationen zum Einrichten von Hybriden finden Sie unter [Planen einer Hybrid Konnektivität](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype for Business Server und Microsoft Exchange Server 2016 arbeiten mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server-Betriebssysteme so konfiguriert sind, dass Sie die FIPS 140-2-Algorithmen für die Systemkryptografie verwenden . Zur Implementierung der FIPS-Unterstützung müssen Sie jeden Server, auf dem Skype for Business Server ausgeführt wird, zur Unterstützung konfigurieren.
  

