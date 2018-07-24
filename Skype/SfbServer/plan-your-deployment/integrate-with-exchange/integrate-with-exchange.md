---
title: Plan zur Integration von Skype for Business mit Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Zusammenfassung: Lesen Sie diesen Abschnitt für Informationen zum Integrieren von Skype für Business Server mit Exchange Server 2016 oder Exchange Server 2013.'
ms.openlocfilehash: 0fc7975e35d84cf6fda75addacee9ffbb8f25b52
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013237"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan zur Integration von Skype for Business mit Exchange Server
 
**Zusammenfassung:** Lesen Sie dieses Thema bietet Informationen dazu, wie Sie Skype für Business Server mit Exchange Server 2016 oder Exchange Server 2013 zu integrieren.
  
Bevor Sie Skype für Business Server und Exchange Server integrieren können, müssen Sie sicherstellen, dass Exchange Server und Skype für Business Server vollständig installiert und eingerichtet und ausgeführt werden. 
  
Ausführliche Informationen zum Installieren von Exchange Server finden Sie in der Dokumentation für Exchange Server – Planung und Bereitstellung für Ihre Version von Exchange. 
   
Nachdem die Server ausgeführt werden, müssen Sie beide Skype-Server-zu-Server-Authentifizierungszertifikaten für Business Server und Exchange Server zuweisen; dieser Zertifikate zulassen Skype für Business Server und Exchange Server zum Austauschen von Informationen und miteinander zu kommunizieren. Bei der Installation von Exchange Server ist ein selbstsigniertes Zertifikat mit dem Namen Microsoft Exchange Server-Auth-Zertifikat für Sie erstellt. Dieses Zertifikat in lokalem Zertifikatspeicher aufbewahren gefunden werden kann, sollte für die Server-zu-Server-Authentifizierung auf Exchange-Server verwendet werden. Ausführliche Informationen zum Zuweisen von Zertifikaten in Exchange Server finden Sie unter [Konfigurieren Mail Flow and Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Für Skype für Business Server können Sie eine vorhandene Skype für Business Server-Zertifikat als das Zertifikat für die Server-zu-Server-Authentifizierung verwenden. Beispielsweise kann Ihre Standardzertifikat auch als "oauthtokenissuer"-Zertifikat verwendet werden. Skype für Business Server können Sie eine beliebige Webserverzertifikat verwenden, wie das Zertifikat für die Server-zu-Server-Authentifizierung, die bereitgestellt:
  
- Das Zertifikat enthält den Namen der SIP-Domäne im Feld „Betreff“.
    
- Dasselbe Zertifikat ist als „OAuthTokenIssuer“-Zertifikat auf allen Front-End-Servern konfiguriert.
    
- The certificate has a length of at least 2048 bits.
    
Ausführliche Informationen zur Server-zu-Server-Authentifizierungszertifikaten für Skype für Business Server finden Sie unter [Server-zu-Server-Zertifikat in Skype für Business Server zuweisen](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst klicken Sie dann auf Exchange-Server konfigurieren. In Exchange Server der AutoErmittlungsdienst Benutzerprofile konfiguriert und bietet Zugriff auf Exchange-Dienste, wenn Benutzer auf das System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:
  
- Verbindungsinformationen für interne und externe Konnektivität mit Exchange Server.
    
- Der Speicherort des Postfachservers des Benutzers.
    
- URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.
    
- Servereinstellungen für Outlook Anywhere.
    
Der AutoErmittlungsdienst muss konfiguriert sein, bevor Sie Skype für Business Server und Exchange Server integrieren können. Sie können überprüfen, ob der AutoErmittlungsdienst mithilfe des folgenden Befehls aus der Exchange Server-Verwaltungsshell und überprüfen Sie den Wert der Eigenschaft AutoDiscoverServiceInternalUri konfiguriert wurde oder nicht:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Wenn dieser Wert leer ist, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. In der Regel wird dieser URI wie folgt aussehen:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einen Befehl wie den folgenden ausführen:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Ausführliche Informationen zum AutoErmittlungsdienst finden Sie unter [AutoErmittlungsdienst](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Nach der AutoErmittlung-Dienst konfiguriert wurde, müssen Sie dann die Skype für Business Server OAuth-Konfigurationseinstellungen ändern; Dadurch wird sichergestellt, dass diese Skype für Business Server, wo Sie den AutoErmittlungsdienst finden weiß. Um die OAuth-Konfigurationseinstellungen in Skype für Business Server zu ändern, führen Sie den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell. Beim Ausführen dieses Befehls werden Sie sicher, dass Sie mit dem AutoErmittlungsdienst ausgeführt wird, auf dem Exchange Server-URI angeben, und für die Verwendung des **autodiscover.svc** So zeigen Sie auf den Speicherort des Diensts anstatt **autodiscover.XML erhalten** (die auf die XML-Datei verweist verwendet vom Dienst):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Der Parameter Identity im vorstehenden Befehl ist optional. Dies liegt daran Skype für Business Server nur eine einzige, globale Auflistung von OAuth-Konfigurationseinstellungen haben kann. Unter anderem bedeutet dies, dass Sie mit diesem Befehl geringfügig vereinfacht die URL für die AutoErmittlung konfigurieren können: 
  
> [!NOTE]
> Set-"csoauthconfiguration"-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
  
> [!NOTE]
> Wenn Sie mit der Technologie noch nicht so vertraut sind, ist „OAuth“ ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei „OAuth“ werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens. Diese Tokens erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz von Ressourcen. 
  
Zusätzlich zu den AutoErmittlungsdienst konfigurieren, müssen Sie auch einen DNS-Eintrag für den Dienst erstellen, die auf Ihrem Exchange-Server verweist. Beispielsweise ist der AutoErmittlungsdienst finden Sie unter autodiscover.litwareinc.com müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der den vollqualifizierten Domänennamen des Exchange-Servers (z. b auflöst "ATL-Exchange-001.litwareinc.com").
  
Wenn Sie Skype für Business Server mit Exchange Online integrieren, sind die nächsten Schritte in [Konfigurieren der Integration zwischen lokalen Skype für Business Server und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), finden Sie andernfalls unter [integrieren Skype für Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Unterstützung von Features
<a name="feature_support"> </a>

In der folgenden Tabelle werden die Features unter verschiedenen Kombinationen von online oder lokal für Exchange und Skype für Unternehmen unterstützt.
  
||**Exchange 2016/2013/2010 (lokal) + Skype für Business Server (lokal)**|**Exchange Online + Skype für Business Server (lokal)**|**Exchange 2010 (lokal) + Skype für Business Online**|**Exchange 2016/2013(on premises) + Skype für Business Online**|**Exchange Online + Skype für Unternehmen Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Anwesenheit in Outlook  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Antworten per Chat, Festnetzanruf, Skype-Anruf oder Videoanruf aus einer Outlook-E-Mail heraus  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Anwesenheit in Outlook Web App  <br/> |J  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Antworten per Chat, Festnetzanruf, Skype-Anruf oder Videoanruf aus einer OWA-E-Mail heraus  <br/> |J  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Planen von und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |J  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |J (erfordert Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Hochauflösende Foto des Kontakts (erfordert Lync 2013 oder Skype für Business Clients mindestens. Nicht unterstützt für LWA, mobile Anwendungen, Lync 2010, Lync für Mac und andere ältere Clients.)  <br/> |J (erfordert Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |J  <br/> |J  <br/> |
|Besprechungsdelegation  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Verpasste Unterhaltungsverlauf und Anrufprotokolle werden in Exchange-Postfach des Benutzers geschrieben.  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Inhalt wird in Exchange archiviert (Chat und Besprechung).  <br/> |J (erfordert Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Durchsuchen von archivierten Inhalten  <br/> |J (erfordert Exchange 2016/2013)  <br/> |J  <br/> |N  <br/> |N  <br/> |J  <br/> |
|Exchange UM-Voicemail  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |J  <br/> |
|Serverseitig aufgezeichnete Unterhaltungen  <br/> |J  <br/> |J  <br/> |N  <br/> |J  <br/> |J  <br/> |
   
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="feature_support"> </a>

[Konfigurieren der Integration zwischen lokalen Skype für Business Server und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[OAuth-Konfiguration zwischen Skype for Business Online und einer lokalen Bereitstellung von Exchange](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrieren von Skype für Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Vorgehensweise zur Integration von Exchange Server 2013 mit Lync Server 2013, Skype für Business Online oder eine hybridbereitstellung von Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Konfigurieren von partneranwendungen in Skype für Business Server und Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)