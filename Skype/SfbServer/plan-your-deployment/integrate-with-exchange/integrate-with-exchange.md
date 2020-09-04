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
description: 'Zusammenfassung: in diesem Thema finden Sie Informationen zur Integration von Skype for Business Server mit Exchange Server 2016 oder Exchange Server 2013.'
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359261"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan zur Integration von Skype for Business mit Exchange Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zur Integration von Skype for Business Server mit Exchange Server 2016 oder Exchange Server 2013 zu erhalten.
  
Bevor Sie Skype for Business Server und Exchange Server integrieren können, müssen Sie sicherstellen, dass sowohl Exchange Server als auch Skype for Business Server vollständig installiert sind und betriebsbereit sind. 
  
Ausführliche Informationen zum Installieren von Exchange Server finden Sie in der Exchange Server-Planungs-und-Bereitstellungsdokumentation für Ihre Version von Exchange. 
   
Nachdem die Serverbetriebs bereit sind, müssen Sie sowohl Skype for Business Server als auch Exchange Server Server-zu-Server-Authentifizierungszertifikate zuweisen. Diese Zertifikate ermöglichen Skype for Business Server und Exchange Server zum Austauschen von Informationen und zur Kommunikation miteinander. Wenn Sie Exchange Server installieren, wird ein selbstsigniertes Zertifikat mit dem Namen Exchange Server Authentifizierungszertifikat für Sie erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollte für die Server-zu-Server-Authentifizierung in Exchange Server verwendet werden. Ausführliche Informationen zum Zuweisen von Zertifikaten in Exchange Server finden Sie unter [Configure Mail Flow and Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Für Skype for Business Server können Sie ein vorhandenes Skype for Business Server Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise kann Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. Skype for Business Server können Sie ein beliebiges Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, vorausgesetzt:
  
- Das Zertifikat enthält den Namen der SIP-Domäne im Betrefffeld.
    
- Dasselbe Zertifikat ist als "OAuthTokenIssuer"-Zertifikat auf allen Front-End-Servern konfiguriert.
    
- Das Zertifikat ist mindestens 2.048 Bit lang.
    
Ausführliche Informationen zu Server-zu-Server-Authentifizierungszertifikaten für Skype for Business Server finden Sie unter [Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst in Exchange Server konfigurieren. In Exchange Server konfiguriert der AutoErmittlungsdienst Benutzerprofile und bietet Zugriff auf Exchange-Dienste, wenn sich Benutzer am System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:
  
- Verbindungsinformationen für die interne und externe Konnektivität mit Exchange Server.
    
- Der Speicherort des Postfachservers des Benutzers.
    
- URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.
    
- Servereinstellungen für Outlook Anywhere.
    
Der AutoErmittlungsdienst muss konfiguriert werden, bevor Sie Skype for Business Server und Exchange Server integrieren können. Sie können überprüfen, ob der AutoErmittlungsdienst konfiguriert wurde, indem Sie den folgenden Befehl in der Exchange Server-Verwaltungsshell ausführen und den Wert der parameterautodiscoverserviceinternaluri-Eigenschaft überprüfen:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Ist dieser Wert leer, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. Normalerweise sieht dieser URI wie folgt aus: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einem Befehl ähnlich folgendem ausführen:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Ausführliche Informationen zum AutoErmittlungsdienst finden Sie unter [AutoErmittlungsdienst](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Nachdem der AutoErmittlungsdienst konfiguriert wurde, müssen Sie die Skype for Business Server Konfigurationseinstellungen für OAuth ändern. Dadurch wird sichergestellt, dass Skype for Business Server weiß, wo der AutoErmittlungsdienst zu finden ist. Um die OAuth-Konfigurationseinstellungen in Skype for Business Server zu ändern, führen Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus. Wenn Sie diesen Befehl ausführen, stellen Sie sicher, dass Sie den URI für den AutoErmittlungsdienst angeben, der auf Ihrem Exchange Server läuft, und dass Sie **autodiscover. svc** verwenden, um auf den Dienst Speicherort zu zeigen, statt auf **autodiscover.xml** (der auf die vom Dienst verwendete XML-Datei zeigt):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Der Parameter Identity im vorangehenden Befehl ist optional; Das liegt daran, dass Skype for Business Server nur eine einzelne globale Auflistung von OAuth-Konfigurationseinstellungen haben kann. Dies bedeutet unter anderem, dass Sie die Auto Ermittlungs-URL mit dem folgenden leicht vereinfachten Befehl konfigurieren können: 
> 
> [!NOTE]
> Festlegen-csoauthconfiguration "-ExchangeAutodiscoverUrl" <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Wenn Sie mit der Technologie noch nicht so vertraut sind, ist "OAuth" ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei "OAuth" werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz Ressourcen. 
  
Sie müssen nicht nur den AutoErmittlungsdienst konfigurieren, sondern auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihre Exchange Server verweist. Wenn sich der AutoErmittlungsdienst beispielsweise unter autodiscover.litwareinc.com befindet, müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der in den vollqualifizierten Domänennamen Ihrer Exchange Server aufgelöst wird (beispielsweise ATL-Exchange-001.litwareinc.com).
  
Wenn Sie Skype for Business Server mit Exchange Online integrieren, sind die nächsten Schritte im [Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), andernfalls Siehe integrieren von [Skype for Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Unterstützung von Features
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nachdem die unten aufgeführten Exchange-Integrationen, die den Dienst enthalten, nicht mehr unterstützt werden.

In der folgenden Tabelle sind die Features aufgeführt, die in verschiedenen Kombinationen von Online oder lokal für Exchange und Skype for Business unterstützt werden.
  
||**Exchange 2016/2013/2010 (lokal) + Skype for Business Server (lokal)**|**Exchange Online + Skype for Business Server (lokal)**|**Exchange 2010 (lokal) + Skype for Business Online**|**Exchange 2016/2013 (lokal) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Anwesenheit in Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Antworten per Chat, PSTN-Anruf, Skype-Anruf oder Video Anruf aus einer Outlook-e-Mail  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Planen und teilnehmen an Onlinebesprechungen über Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Anwesenheit in Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Antworten per Chat, PSTN-Anruf, Skype-Anruf oder Video Anruf von einer OWA-e-Mail  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Planen und teilnehmen an Onlinebesprechungen über Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Chat/Anwesenheit in mobilen Clients  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Teilnahme an Onlinebesprechungen in mobilen Clients  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen des Outlook-Kalenders  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Kontaktliste (über den einheitlichen Kontaktspeicher)  <br/> |Y (benötigt Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Hochauflösendes Kontakt Foto (erfordert lync 2013 oder Skype for Business Clients mindestens. Nicht unterstützt für LWA, Mobile Apps, lync 2010, lync für Mac und andere ältere Clients.)  <br/> |Y (benötigt Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |
|Besprechungs Delegation  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Archivieren von Inhalt (Chat und Besprechung) in Exchange  <br/> |Y (benötigt Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Durchsuchen archivierter Inhalte  <br/> |Y (benötigt Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Exchange um Voice Mail  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Server seitiger Unterhaltungsverlauf  <br/> |v  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |

> [!NOTE]
> Es gibt einen Cloud Voicemail-Dienst, der für Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 und lync Server 2013 unterstützt wird.
> 

## <a name="see-also"></a>Weitere Artikel
<a name="feature_support"> </a>

[Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Konfigurieren von OAuth zwischen Skype for Business Online und Exchange lokal](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrieren von Skype for Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Integrieren von Exchange Server 2013 mit lync Server 2013, Skype for Business Online oder einer lync Server 2013-hybridbereitstellung](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
