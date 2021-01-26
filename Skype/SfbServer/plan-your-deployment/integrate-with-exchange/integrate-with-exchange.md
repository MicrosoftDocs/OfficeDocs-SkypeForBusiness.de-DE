---
title: Plan zur Integration von Skype for Business und Exchange
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
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Zusammenfassung: In diesem Thema finden Sie Informationen zur Integration von Skype for Business Server in Exchange Server 2016 oder Exchange Server 2013.'
ms.openlocfilehash: f2a9dfc718b7891a0cbe9b7b1455df24531a6ed0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810100"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan zur Integration von Skype for Business und Exchange
 
**Zusammenfassung:** In diesem Thema finden Sie Informationen zur Integration von Skype for Business Server in Exchange Server 2016 oder Exchange Server 2013.
  
Bevor Sie Skype for Business Server und Exchange Server integrieren können, müssen Sie sicherstellen, dass sowohl Exchange Server als auch Skype for Business Server vollständig installiert und ausgeführt werden. 
  
Ausführliche Informationen zum Installieren Exchange Server finden Sie in Exchange Server Planungs- und Bereitstellungsdokumentation für Ihre Exchange-Version. 
   
Nachdem die Server ausgeführt wurden, müssen Sie Server-zu-Server-Authentifizierungszertifikate sowohl Skype for Business Server als auch Skype for Business Server Exchange Server; Diese Zertifikate ermöglichen Skype for Business Server und Exchange Server, Informationen zu austauschen und miteinander zu kommunizieren. Wenn Sie Exchange Server installieren, wird ein selbst signiertes Zertifikat mit dem Namen Microsoft Exchange Server A0 für Sie erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befinden kann, sollte für die Server-zu-Server-Authentifizierung auf Exchange Server. Weitere Informationen zum Zuweisen von Zertifikaten in Exchange Server finden Sie unter [Configure Mail Flow and Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Für Skype for Business Server können Sie ein vorhandenes Skype for Business #A0 als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise kann Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. Mit Skype for Business Server können Sie ein beliebiges Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, sofern:
  
- Das Zertifikat enthält den Namen der SIP-Domäne im Betrefffeld.
    
- Dasselbe Zertifikat ist als "OAuthTokenIssuer"-Zertifikat auf allen Front-End-Servern konfiguriert.
    
- Das Zertifikat ist mindestens 2.048 Bit lang.
    
Details zu Server-zu-Server-Authentifizierungszertifikaten für Skype for Business Server finden Sie unter Zuweisen eines [Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst auf der Exchange Server. In Exchange Server Der AutoErmittlungsdienst konfiguriert Benutzerprofile und bietet Zugriff auf Exchange-Dienste, wenn sich Benutzer am System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:
  
- Verbindungsinformationen für interne und externe Verbindungen Exchange Server.
    
- Der Speicherort des Postfachservers des Benutzers.
    
- URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.
    
- Servereinstellungen für Outlook Anywhere.
    
Der AutoErmittlungsdienst muss konfiguriert werden, bevor Sie Skype for Business Server und ihre Exchange Server. Sie können überprüfen, ob der AutoErmittlungsdienst konfiguriert wurde, indem Sie den folgenden Befehl in der Exchange Server-Verwaltungsshell ausführen und den Wert der Eigenschaft "AutoDiscoverServiceInternalUri" überprüfen:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Ist dieser Wert leer, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. In der Regel sieht dieser URI wie der gleiche aus: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einem Befehl ähnlich folgendem ausführen:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Weitere Informationen zum AutoErmittlungsdienst finden Sie unter [AutoErmittlungsdienst](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Nachdem der AutoErmittlungsdienst konfiguriert wurde, müssen Sie die Skype for Business Server #A0 ändern. dadurch wird sichergestellt, dass Skype for Business Server weiß, wo der AutoErmittlungsdienst zu finden ist. Führen Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus, um die OAuth-Konfigurationseinstellungen in Skype for Business Server zu ändern. Stellen Sie beim Ausführen dieses Befehls sicher, dass Sie den URI für den AutoErmittlungsdienst angeben, der auf Ihrem Exchange Server ausgeführt wird, und dass Sie **"autodiscover.svc"** verwenden, um auf den Dienstspeicherort anstelle von **autodiscover.xml** zu verweisen (der auf die vom Dienst verwendete XML-Datei verweist):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Der Parameter "Identity" im vorherigen Befehl ist optional. Das liegt daran, dass Skype for Business Server nur eine einzelne, globale Auflistung von OAuth-Konfigurationseinstellungen zulässt. Das bedeutet unter anderem, dass Sie die AutoErmittlungs-URL mithilfe des etwas einfacheren Befehls konfigurieren können: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Wenn Sie mit der Technologie noch nicht so vertraut sind, ist "OAuth" ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei "OAuth" werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz Ressourcen. 
  
Zusätzlich zur Konfiguration des AutoErmittlungsdiensts müssen Sie auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihre Exchange Server. Wenn sich Ihr AutoErmittlungsdienst beispielsweise unter autodiscover.litwareinc.com müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der in den vollqualifizierten Domänennamen Ihrer Exchange Server aufgelöst wird (z. B. atl-exchange-001.litwareinc.com).
  
Wenn Sie Skype for Business Server in Exchange Online integrieren, finden Sie die nächsten Schritte unter "Konfigurieren der Integration zwischen lokalem Skype for Business Server und [Outlook Web App",](../../deploy/integrate-with-exchange-server/outlook-web-app.md)andernfalls siehe "Integrieren von Skype for Business Server in [Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
## <a name="feature-support"></a>Featureunterstützung
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem die unten aufgeführten Exchange-Integrationen, die den Dienst enthalten, nicht mehr unterstützt werden.

In der folgenden Tabelle sind die Features aufgeführt, die unter verschiedenen Kombinationen von Online- oder lokalen Funktionen für Exchange und Skype for Business unterstützt werden.
  
||**Exchange 2016/2013/2010 (lokal) + Skype for Business Server (lokal)**|**Exchange Online + Skype for Business Server (lokal)**|**Exchange 2010 (lokal) + Skype for Business Online**|**Exchange 2016/2013 (lokal) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Anwesenheit in Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Antworten über Chat, PSTN-Anruf, Skype-Anruf oder Videoanruf über eine Outlook-E-Mail  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Planen und Teilnehmen an Onlinebesprechungen über Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Anwesenheit in Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Antworten über Chat, PSTN-Anruf, Skype-Anruf oder Videoanruf über eine OWA-E-Mail  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Planen und Teilnehmen an Onlinebesprechungen über Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Im/Anwesenheit in mobilen Clients  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Teilnehmen an Onlinebesprechungen in mobilen Clients  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Informationen im Outlook-Kalender  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Y (Exchange 2016/2013 benötigen)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Hochauflösendes Kontaktfoto (erfordert mindestens Lync 2013- oder Skype for Business-Clients. Nicht unterstützt für LWA, mobile Apps, Lync 2010, Lync für Mac und andere ältere Clients.)  <br/> |Y (Exchange 2016/2013 benötigen)  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |
|Besprechungsdelegierung  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Der Verlauf verpasster Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Archivieren von Inhalten (Im- und Besprechung) in Exchange  <br/> |Y (Exchange 2016/2013 benötigen)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Y (Exchange 2016/2013 benötigen)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Exchange UM Voice Mail  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Serverseitiger Unterhaltungsverlauf  <br/> |v  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |

> [!NOTE]
> Es gibt einen Cloud-Voicemaildienst, der für Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 und Lync Server 2013 unterstützt wird.
> 

## <a name="see-also"></a>Siehe auch
<a name="feature_support"> </a>

[Konfigurieren der Integration zwischen lokalem Skype for Business Server und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Konfigurieren von OAuth zwischen Skype for Business Online und Exchange lokal](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrieren von Skype for Business Server in Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Integrieren von Exchange Server 2013 in Lync Server 2013, Skype for Business Online oder eine Lync Server 2013-Hybridbereitstellung](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Konfigurieren von Partneranwendungen in Skype for Business Server und Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
