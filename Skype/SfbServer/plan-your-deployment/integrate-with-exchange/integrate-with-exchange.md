---
title: Plan zur Integration von Skype for Business mit Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Zusammenfassung: In diesem Thema finden Sie Informationen zur Integration von Skype for Business Server in Exchange Server 2016 oder Exchange Server 2013.'
ms.openlocfilehash: 995511f55d131bfd3d446f5691563436c19da2c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815883"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan zur Integration von Skype for Business mit Exchange Server
 
**Zusammenfassung:** In diesem Thema finden Sie Informationen zur Integration von Skype for Business Server in Exchange Server 2016 oder Exchange Server 2013.
  
Vor der Integration von Skype for Business Server und Exchange Server müssen Sie sicherstellen, dass sowohl Exchange Server als auch Skype for Business Server vollständig installiert ist und ausgeführt wird. 
  
Details zum Installieren von Exchange Server finden Sie in der Exchange Server-Planungs- und -Bereitstellungsdokumentation für Ihre Version von Exchange. 
   
Wenn die Server ausgeführt werden, müssen Sie Skype for Business Server und Exchange Server Zertifikate für die Server-zu-Server-Authentifizierung zuweisen. Diese Zertifikate sind notwendig, damit Skype for Business Server und Exchange Server Informationen austauschen und miteinander kommunizieren können. Bei der Installation von Exchange Server wird ein selbstsigniertes Zertifikat mit dem Namen „Microsoft Exchange Server Auth Certificate“ für Sie erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollte für die Server-zu-Server-Authentifizierung in Exchange Server verwendet werden. Details zum Zuweisen von Zertifikaten in Exchange Server finden Sie unter [Konfigurieren von Nachrichtenfluss und Clientzugriff](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Für Skype for Business Server können Sie ein vorhandenes Skype for Business Server-Zertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden. Sie können beispielsweise Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwenden. Sie können für Skype for Business Server jedes Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, sofern es die folgenden Voraussetzungen erfüllt:
  
- Das Zertifikat enthält den Namen der SIP-Domäne im Feld „Betreff“.
    
- Dasselbe Zertifikat ist als „OAuthTokenIssuer“-Zertifikat auf allen Front-End-Servern konfiguriert.
    
- Das Zertifikat hat eine Länge von mindestens 2048 Bits.
    
Details zu Zertifikaten für die Server-zu-Server-Authentifizierung für Skype for Business Server finden Sie unter [Zuweisen eines Zertifikats für die Server-zu-Server-Authentifizierung zu Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst in Exchange Server konfigurieren. In Exchange Server konfiguriert der AutoErmittlungsdienst Benutzerprofile und gewährt Zugriff auf Exchange-Dienste, wenn Benutzer sich beim System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:
  
- Verbindungsinformationen für die interne und externe Konnektivität mit Exchange Server
    
- Den Standort des Postfachservers des Benutzers
    
- URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.
    
- Servereinstellungen für Outlook Anywhere.
    
Der AutoErmittlungsdienst muss konfiguriert sein, damit Sie Skype for Business Server und Exchange Server integrieren können. Sie können feststellen, ob der AutoErmittlungsdienst konfiguriert ist, indem Sie in der Exchange Server-Verwaltungsshell den folgenden Befehl ausführen und den Wert der „AutoDiscoverServiceInternalUri“-Eigenschaft überprüfen:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Wenn dieser Wert leer ist, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. Dieser URI sieht in der Regel etwa so aus: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einen Befehl wie den folgenden ausführen:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Details zum AutoErmittlungsdienst finden Sie unter [AutoErmittlungsdienst](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Nachdem der AutoErmittlungsdienst konfiguriert wurde, müssen Sie die Konfigurationseinstellungen für Skype for Business Server OAuth ändern. Dadurch wird sichergestellt, dass Skype for Business Server weiß, wo der AutoErmittlungsdienst zu finden ist. Um die OAuth-Konfigurationseinstellungen in Skype for Business Server zu ändern, führen Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl aus. Geben Sie beim Ausführen dieses Befehls unbedingt den URI zu dem AutoErmittlungsdienst an, der auf Ihrem Exchange-Server ausgeführt wird, und verwenden Sie zum Verweisen auf den Dienstspeicherort **autodiscover.svc** und nicht **autodiscover.xml** (letzteres verweist auf die vom Dienst verwendete XML-Datei):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Der Parameter „Identity“ im oben genannten Befehl ist optional, da Skype for Business Server nur eine einzige globale Auflistung von OAuth-Konfigurationseinstellungen zulässt. Das bedeutet unter anderem, dass Sie die URL für den AutoErmittlungsdienst mit diesem etwas einfacheren Befehl konfigurieren können: 
> 
> [!NOTE]
> Satz-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Wenn Sie mit der Technologie noch nicht so vertraut sind, ist „OAuth“ ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei „OAuth“ werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens. Diese Tokens erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz von Ressourcen. 
  
Sie müssen nicht nur den AutoErmittlungsdienst konfigurieren, sondern auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihren Exchange-Server verweist. Wenn sich der AutoErmittlungsdienst beispielsweise unter „autodiscover.litwareinc.com“ befindet, müssen Sie einen DNS-Eintrag für „autodiscover.litwareinc.com“ erstellen, der in den vollqualifizierten Domänennamen Ihres Exchange-Servers aufgelöst wird (z. B. „atl-exchange-001.litwareinc.com“).
  
Wenn Sie Skype for Business Server in Exchange Online integrieren, finden Sie die nächsten Schritte unter [Konfigurieren der Integration zwischen einer lokalen Skype for Business Server-Bereitstellung und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md). Lesen Sie andernfalls [Integrieren von Skype for Business Server in Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Unterstützung von Features
<a name="feature_support"> </a>

Die folgende Tabelle zeigt Einzelheiten zu den unterstützten Funktionen in verschiedenen Kombinationen von Onlinebereitstellungen oder lokalen Bereitstellungen von Exchange und Skype for Business.
  
||**Exchange 2016/2013/2010 (lokal) + Skype for Business Server (lokal)**|**Exchange Online + Skype for Business Server (lokal)**|**Exchange 2010 (lokal) + Skype for Business Online**|**Exchange 2016/2013 (lokal) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Anwesenheit in Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Antworten per Chat, Festnetzanruf, Skype-Anruf oder Videoanruf aus einer Outlook-E-Mail heraus  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Anwesenheit in Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Antworten per Chat, Festnetzanruf, Skype-Anruf oder Videoanruf aus einer OWA-E-Mail heraus  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> |J  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |J  <br/> |
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |J (erfordert Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Hochauflösende Kontaktfotos (Erfordert mindestens Lync 2013- oder Skype for Business-Clients. Nicht unterstützt für LWA, mobile Apps, Lync 2010, Lync für Mac und andere ältere Clients.)  <br/> |J (erfordert Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Besprechungsdelegation  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Die Protokolle der verpassten Unterhaltungen und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> |J (erfordert Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Durchsuchen von archivierten Inhalten  <br/> |J (erfordert Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Exchange UM-Voicemail  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Serverseitig aufgezeichnete Unterhaltungen  <br/> |J  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Es gibt einen Cloud Voicemail-Dienst, der für Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 und lync Server 2013 unterstützt wird.
> 

## <a name="see-also"></a>Siehe auch
<a name="feature_support"> </a>

[Konfigurieren der Integration zwischen einer lokalen Skype for Business Server-Bereitstellung und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Konfigurieren von OAuth zwischen Skype for Business Online und einer lokalen Exchange-Bereitstellung](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrieren von Skype for Business Server in Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Integrieren von Exchange Server 2013 in Lync Server 2013, Skype for Business Online oder eine Lync Server 2013-Hybridbereitstellung](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Konfigurieren von Partneranwendungen in Skype for Business Server und Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
