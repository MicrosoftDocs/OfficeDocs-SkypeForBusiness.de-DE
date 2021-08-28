---
title: Plan zur Integration von Skype for Business und Exchange
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
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Zusammenfassung: In diesem Thema finden Sie Informationen zur Integration von Skype for Business Server in Exchange Server 2016 oder Exchange Server 2013.'
ms.openlocfilehash: 6c830636b8db5b2a4fba02a1a5f34489e691459c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609222"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan zur Integration von Skype for Business und Exchange
 
**Zusammenfassung:** In diesem Thema finden Sie Informationen zum Integrieren von Skype for Business Server in Exchange Server 2016 oder Exchange Server 2013.
  
Bevor Sie Skype for Business Server und Exchange Server integrieren können, müssen Sie sicherstellen, dass sowohl Exchange Server als auch Skype for Business Server vollständig installiert und ausgeführt werden. 
  
Ausführliche Informationen zum Installieren von Exchange Server finden Sie in der Exchange Server Planungs- und Bereitstellungsdokumentation für Ihre Version von Exchange. 
   
Nachdem die Server eingerichtet und ausgeführt wurden, müssen Sie sowohl Skype for Business Server als auch Exchange Server Server-zu-Server-Authentifizierungszertifikate zuweisen. Mit diesen Zertifikaten können Skype for Business Server und Exchange Server Informationen austauschen und miteinander kommunizieren. Wenn Sie Exchange Server installieren, wird ein selbstsignes Zertifikat mit dem Namen Microsoft Exchange Server Authentifizierungszertifikats für Sie erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollte für die Server-zu-Server-Authentifizierung auf Exchange Server verwendet werden. Ausführliche Informationen zum Zuweisen von Zertifikaten in Exchange Server finden Sie unter [Konfigurieren von E-Mail-Flow und Clientzugriff.](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)
  
Für Skype for Business Server können Sie ein vorhandenes Skype for Business Server Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise kann Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. Skype for Business Server können Sie jedes Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, vorausgesetzt:
  
- Das Zertifikat enthält den Namen der SIP-Domäne im Betrefffeld.
    
- Dasselbe Zertifikat ist als "OAuthTokenIssuer"-Zertifikat auf allen Front-End-Servern konfiguriert.
    
- Das Zertifikat ist mindestens 2.048 Bit lang.
    
Ausführliche Informationen zu Zertifikaten für die Server-zu-Server-Authentifizierung für Skype for Business Server finden Sie unter [Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst auf Exchange Server konfigurieren. In Exchange Server konfiguriert der AutoErmittlungsdienst Benutzerprofile und bietet Zugriff auf Exchange Dienste, wenn sich Benutzer beim System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:
  
- Verbindungsinformationen für interne und externe Verbindungen mit Exchange Server.
    
- Der Speicherort des Postfachservers des Benutzers.
    
- URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.
    
- Servereinstellungen für Outlook Anywhere.
    
Der AutoErmittlungsdienst muss konfiguriert sein, bevor Sie Skype for Business Server und Exchange Server integrieren können. Sie können überprüfen, ob der AutoErmittlungsdienst konfiguriert wurde, indem Sie den folgenden Befehl in der Exchange Server-Verwaltungsshell ausführen und den Wert der AutoDiscoverServiceInternalUri-Eigenschaft überprüfen:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Ist dieser Wert leer, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. In der Regel sieht dieser URI wie folgt aus: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einem Befehl ähnlich folgendem ausführen:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Ausführliche Informationen zum AutoErmittlungsdienst finden Sie unter [AutoErmittlungsdienst.](/Exchange/architecture/client-access/autodiscover)
  
Nachdem der AutoErmittlungsdienst konfiguriert wurde, müssen Sie die Skype for Business Server OAuth-Konfigurationseinstellungen ändern. dadurch wird sichergestellt, dass Skype for Business Server weiß, wo der AutoErmittlungsdienst zu finden ist. Um die OAuth-Konfigurationseinstellungen in Skype for Business Server zu ändern, führen Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell aus. Achten Sie beim Ausführen dieses Befehls darauf, dass Sie den URI für den autoErmittlungsdienst angeben, der auf Ihrem Exchange Server ausgeführt wird, und dass Sie **autodiscover.svc** verwenden, um auf den Dienstspeicherort zu verweisen, anstatt **aufautodiscover.xml** (die auf die vom Dienst verwendete XML-Datei verweist):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Der Parameter "Identity" im vorherigen Befehl ist optional. Dies liegt daran, dass Skype for Business Server nur eine einzelne, globale Sammlung von OAuth-Konfigurationseinstellungen ermöglicht. Dies bedeutet unter anderem, dass Sie die AutoErmittlungs-URL mithilfe dieses etwas einfacheren Befehls konfigurieren können: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Wenn Sie mit der Technologie noch nicht so vertraut sind, ist "OAuth" ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei "OAuth" werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz Ressourcen. 
  
Zusätzlich zur Konfiguration des AutoErmittlungsdiensts müssen Sie auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihre Exchange Server verweist. Wenn sich der AutoErmittlungsdienst beispielsweise bei autodiscover.litwareinc.com befindet, müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der in den vollqualifizierten Domänennamen Ihrer Exchange Server aufgelöst wird (z. B. atl-exchange-001.litwareinc.com).
  
Wenn Sie Skype for Business Server in Exchange Online integrieren, finden Sie die nächsten Schritte in der Konfiguration der [Integration zwischen lokalen Skype for Business Server und Outlook Web App.](../../deploy/integrate-with-exchange-server/outlook-web-app.md)Andernfalls finden Sie informationen unter Integrieren Skype for Business Server in [Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
## <a name="feature-support"></a>Featureunterstützung
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem die unten aufgeführten Exchange Integrationen, die den Dienst enthalten, nicht mehr unterstützt werden.

In der folgenden Tabelle sind die Features aufgeführt, die unter verschiedenen Kombinationen von online oder lokal für Exchange und Skype for Business unterstützt werden.
  
||**Exchange 2013.02.2010 (lokal) + Skype for Business Server (lokal)**|**Exchange Online + Skype for Business Server (lokal)**|**Exchange 2010 (lokal) + Skype for Business Online**|**Exchange 2016/2013 (lokal) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Anwesenheit in Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Antworten per Chat, PSTN-Anruf, Skype Anruf oder Videoanruf über eine Outlook E-Mail  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Planen und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Anwesenheit in Outlook Web App  <br/> |v  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Antworten über Chat, PSTN-Anruf, Skype Anruf oder Videoanruf aus einer OWA-E-Mail  <br/> |v  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Planen und Teilnehmen an Onlinebesprechungen über Outlook Web App  <br/> |v  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Veröffentlichungsstatus basierend auf Outlook Frei/Gebucht-Kalenderinformationen  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Kontaktliste (über unified Contact Store)  <br/> |J (erforderlich Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Kontaktfoto mit hoher Auflösung (erfordert mindestens Lync 2013- oder Skype for Business-Clients. Nicht unterstützt für LWA, mobile Apps, Lync 2010, Lync für Mac und andere ältere Clients.)  <br/> |J (erforderlich Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |v  <br/> |v  <br/> |
|Besprechungsdelegierung  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Der Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Archivierung von Inhalten (Chat und Besprechung) in Exchange  <br/> |J (erforderlich Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |J (erforderlich Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Exchange UM-Voicemail  <br/> |v  <br/> |J  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Serverseitiger Unterhaltungsverlauf  <br/> |v  <br/> |J  <br/> |N  <br/> |v  <br/> |v  <br/> |

> [!NOTE]
> Es gibt einen Cloud-Voicemail Dienst, der für Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 und Lync Server 2013 unterstützt wird.
> 

## <a name="see-also"></a>Siehe auch
<a name="feature_support"> </a>

[Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Konfigurieren von OAuth zwischen Skype for Business Online und Exchange lokal](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrieren von Skype for Business Server in Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Integrieren von Exchange Server 2013 in Lync Server 2013, Skype for Business Online oder einer Lync Server 2013-Hybridbereitstellung](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Konfigurieren von Partneranwendungen in Skype for Business Server und Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)