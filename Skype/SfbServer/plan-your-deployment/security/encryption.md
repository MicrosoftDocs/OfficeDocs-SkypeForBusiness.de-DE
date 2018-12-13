---
title: Verschlüsselung für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype für Business Server verwendet TLS und MTLS zum Verschlüsseln von Sofortnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet. Wenn ist das Verbinden von Skype für Business Server mit 3. Partei IPPBX Systemen oder SIP-Trunks TLS optional, wird jedoch dringend empfohlen, zwischen dem Vermittlungsserver und dem Mediengateway. Wenn TLS auf dieser Verbindung konfiguriert ist, ist MTLS erforderlich. Aus diesem Grund muss das Gateway mit einem Zertifikat von einer Zertifizierungsstelle konfiguriert werden, die der Vermittlungsserver vertrauenswürdig ist.
ms.openlocfilehash: ff2aa0a3d0727aa5ed579413fe03593568f9f773
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240895"
---
# <a name="encryption-for-skype-for-business-server"></a>Verschlüsselung für Skype für Business Server
 
Skype für Business Server verwendet TLS und MTLS zum Verschlüsseln von Sofortnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet. Wenn ist das Verbinden von Skype für Business Server mit Drittanbietersystemen IPPBX oder SIP-Trunks TLS optional, wird jedoch dringend empfohlen, zwischen dem Vermittlungsserver und dem Mediengateway. Wenn TLS auf dieser Verbindung konfiguriert ist, ist MTLS erforderlich. Aus diesem Grund muss das Gateway mit einem Zertifikat von einer Zertifizierungsstelle konfiguriert werden, die der Vermittlungsserver vertrauenswürdig ist.
  
> [!NOTE]
> Im Jahr 2014 wurde eine Sicherheitsempfehlung zu SSL 3.0 veröffentlicht. Deaktivieren SSL 3.0 in Skype für Business Server 2015 ist eine unterstützte Option. Weitere Informationen über die Sicherheit advisory finden Sie unter [Deaktivieren von SSL 3.0 in Lync Server 2013 und Skype für Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Sicherheitshinweis:** Damit sichergestellt ist das sicherste kryptografische Protokoll wird verwendet, Skype für Business Server 2015 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge an die Clients bieten: **1.2 TLS, TLS 1.1, TLS 1.0**. TLS ist ein wichtiger Aspekt des Skype für Business Server 2015, und es ist daher erforderlich, um einen unterstützten Umgebung aufrechterhalten können.<br/>
**Sicherheitshinweis:** Damit sichergestellt ist das sicherste kryptografische Protokoll wird verwendet, Skype für Business Server 2019 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge an die Clients bieten: **1.3 TLS, TLS 1.2**. TLS ist ein wichtiger Aspekt des Skype für Business Server 2019, und es ist daher erforderlich, um einen unterstützten Umgebung aufrechterhalten können. 
  
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
> Wenn Sie eine hybridumgebung implementieren, müssen Sie auch die Skype für Verschlüsselungsstufe Business Server ändern. Standardmäßig ist die Verschlüsselungsstufe auf „Erforderlich“ eingestellt. Sie müssen diese Einstellung Supported ändern, mit der Skype für Business Server-Verwaltungsshell. Weitere Informationen zum Einrichten von Hybriden finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) oder [Skype für hybridlösungen Business Server 2019](../../../SfBServer2019/hybrid/hybrid-solutions.md) in der Bereitstellungsdokumentation.
  
## <a name="fips"></a>FIPS

Skype für Business Server und Microsoft Exchange Server 2016 für die Ausführung mit Unterstützung für Federal Information Processing Standard (FIPS) 140-2-Algorithmen Betriebssysteme der Windows Server konfiguriert sind, um den FIPS 140-2-Algorithmen zur Systemkryptografie verwenden . Um FIPS-Unterstützung zu implementieren, müssen Sie auf jedem Server mit Skype für Business Server für die Unterstützung konfigurieren.
  

