---
title: Konfigurieren von partneranwendungen in Skype für Business Server 2015 und Exchange Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.'
ms.openlocfilehash: d9d2b32b637946555b906f24e7abbd5dda007d7f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878473"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Konfigurieren von partneranwendungen in Skype für Business Server und Exchange Server
 
**Zusammenfassung:** Konfigurieren Sie Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.
  
An einer Server-zu-Server-Authentifizierung sind üblicherweise zwei Server, die miteinander kommunizieren müssen, und ein Sicherheitstokenserver eines Drittanbieters beteiligt. Wenn Server A und Server B kommunizieren müssen, starten, klicken Sie dann beide dieser Server in der Regel indem wenden Sie sich an einen token-Server und Abrufen von einer gegenseitig vertrauenswürdigen Sicherheitstoken. Server A präsentiert das Sicherheitstoken dann Server B (und umgekehrt), womit beide ihre Authentizität und Vertrauenswürdigkeit nachweisen.
  
Dies ist jedoch in der Regel. Skype für Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 müssen nicht Drittanbieter-token Server verwenden, wenn Sie miteinander kommunizieren. Dies liegt daran diese-Serverprodukte Sicherheitstoken erstellen können, die von einem anderen ohne die Notwendigkeit einer separaten token Server akzeptiert werden können. (Diese Funktion ist nur verfügbar in Skype für Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013. Wenn Sie Server-zu-Server-Authentifizierung mit anderen Servern einrichten müssen, müssen einschließlich anderen Microsoft-Serverprodukten, dann können Sie dazu unter Verwendung eines Drittanbieter-token.)
  
Zum Einrichten der Server-zu-Server-Authentifizierung zwischen Skype für Business Server und Exchange Server müssen Sie zwei Schritte ausführen: 1) müssen Sie die geeigneten Zertifikate auf jedem Server; zuweisen und 2) müssen Sie jeden Server, um eine partneranwendung des anderen Servers konfigurieren: Das bedeutet, dass Sie Skype für Business Server werden als partneranwendung für Exchange Server konfigurieren müssen, müssen Sie Exchange-Server, um eine partneranwendung für Skype konfigurieren für Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Konfigurieren von Skype für Business Server werden als Partneranwendung für Exchange Server

Die einfachste Möglichkeit zum Konfigurieren von Skype für Business Server eine partneranwendung mit Exchange Server 2016 oder Exchange Server 2013 ist das Skript konfigurieren EnterprisePartnerApplication.ps1, ein Windows PowerShell-Skript auszuführen, die mit Exchange Server verwendet werden soll. Um dieses Skript ausführen, müssen Sie die URL für die Skype für Business Server-Authentifizierung Metadatendokument angeben. Dies wird in der Regel die vollqualifizierten Domänennamen der Skype für Business Serverpool gefolgt von dem Suffix /metadata/json/1 sein. Beispiel:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Öffnen Sie die Exchange-Verwaltungsshell und führen Sie einen Befehl wie den folgenden (unter der Annahme, dass Exchange auf Laufwerk C: installiert wurde, und das alles den Standardordnerpfad verwendet), um Skype für Business Server als partneranwendung zu konfigurieren:
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Nach der Konfiguration der partneranwendung wird empfohlen, dass Sie beenden und neu (Internet Information Services, IIS) auf den Exchange-Postfach und Client Access-Servern starten. Mit einem Befehl wie den folgenden, der den Dienst auf dem Computer Atl-Exchange-001 neu gestartet wird, können Sie IIS neu starten:
  
```
iisreset atl-exchange-001
```

Dieser Befehl kann aus in der Exchange-Verwaltungsshell oder aus einem beliebigen anderen Befehlsfenster Befehlfenster ausgeführt werden.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Konfigurieren von Exchange Server als Partneranwendung für Skype für Business Server sein.

Nachdem Sie Skype für Business Server werden als partneranwendung für Exchange Server 2016 oder Exchange Server 2013 konfiguriert haben, müssen Sie dann Exchange-Server als partneranwendung für Skype für Business Server konfigurieren. Dies kann erfolgen, indem Sie die Skype für Business Server-Verwaltungsshell und das Metadatendokument Authentifizierung für Exchange; Normalerweise wird dies der URI des Exchange-AutoErmittlungsdiensts, gefolgt von dem Suffix /metadata/json/1 sein. Beispiel:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype für Business Server werden partneranwendungen mithilfe des Cmdlets ["New-cspartnerapplication"](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) konfiguriert. Zusätzlich zur Angabe der Metadaten URI sollten Sie auch die Vertrauenswürdigkeit der Anwendung auf vollständig festlegen; Dadurch können Exchange selbst und alle autorisierten Benutzer im Bereich darstellen. Beispiel:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Alternativ können Sie eine partneranwendung zu erstellen, durch Kopieren und Ändern des Skriptcodes gefunden in der Skype Business Server eine Server-zu-Server-Dokumentation. Finden Sie weitere Informationen im Artikel [Verwalten Server-zu-Server-Authentifizierung (OAuth) und partneranwendungen in Skype für Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) aus.
  
Wenn Sie partneranwendungen für beide Skype für Business Server und Exchange Server erfolgreich konfiguriert haben, haben Sie die Server-zu-Server-Authentifizierung zwischen den beiden Produkten auch erfolgreich konfiguriert. Skype für Business Server umfasst eines Windows PowerShell-Cmdlets, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , wodurch Sie sicherstellen, dass die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und dass die Skype für Business Server Speicherdienst können Verbinden Sie mit Exchange Server. Das Cmdlet wird eine Verbindung mit dem Postfach eines Benutzers von Exchange Server, für diesen Benutzer ein Element in den Ordner "Unterhaltungsverlauf" schreiben und klicken Sie dann (optional), dass das Element löschen.
  
Um die Integration von Skype für Business Server und Exchange Server zu testen, führen Sie einen Befehl ähnlich dem folgenden aus der Skype für Business Server-Verwaltungsshell aus:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Im vorstehenden Befehl stellt die SipUri die SIP-Adresse eines Benutzers mit einem Konto an, auf dem Exchange-Server; der Befehl schlägt fehl, dies ist nicht um ein gültiges Konto.
  
> [!NOTE]
> Wenn Sie eine 401-Antwort von dieses Cmdlet empfangen, ist es wahrscheinlich, da die Standardkonfiguration für Exchange keine Unterstützung für das Akzeptieren von Oauth-Token einschließt. Weitere Informationen zur Verwendung von Oauth in Exchange finden Sie unter [Konfigurieren der OAuth-Authentifizierung mit SharePoint 2013 und Skype für Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen (z. B. der Integration der Archivierung und des einheitlichen Kontaktspeichers) fortfahren.
