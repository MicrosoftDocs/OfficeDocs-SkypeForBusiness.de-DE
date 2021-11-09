---
title: Konfigurieren von Partneranwendungen in Skype for Business Server 2015 und Exchange Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: bb76b34bdf1a5a8a6c1b60fc200c46112985f31c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864242"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server
 
**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.
  
Für die Server-zu-Server-Authentifizierung sind in der Regel zwei Server erforderlich, die miteinander und mit einem Sicherheitstokenserver eines Drittanbieters kommunizieren müssen. Wenn Server A und Server B kommunizieren müssen, beginnen beide Server in der Regel damit, einen Tokenserver zu kontaktieren und ein sich gegenseitig vertrauenswürdiges Sicherheitstoken abzurufen. Server A stellt dieses Sicherheitstoken dann Server B (und umgekehrt) zur Gewährleistung seiner Authentizität und Vertrauenswürdigkeit vor.
  
Dies ist jedoch eine allgemeine Regel. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 müssen bei der Kommunikation miteinander keinen Drittanbietertokenserver verwenden; Dies liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die voneinander akzeptiert werden können, ohne dass ein separater Tokenserver erforderlich ist. (Diese Funktion ist nur in Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 verfügbar. Wenn Sie die Server-zu-Server-Authentifizierung mit anderen Servern einrichten müssen, einschließlich anderer Microsoft-Serverprodukte, müssen Sie dies mithilfe eines Drittanbietertokenservers tun.)
  
Zum Einrichten der Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server müssen Sie zwei Schritte ausführen: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und, 2) Sie müssen jeden Server so konfigurieren, dass er eine Partneranwendung des anderen Servers ist: Das bedeutet, dass Sie Skype for Business Server als Partneranwendung für Exchange Server konfigurieren und Exchange Server als Partneranwendung für Skype for Business Server konfigurieren müssen.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Konfigurieren von Skype for Business Server als Partneranwendung für Exchange Server

Die einfachste Möglichkeit, Skype for Business Server als Partneranwendung mit Exchange Server 2016 oder Exchange Server 2013 zu konfigurieren, besteht darin, das Configure-EnterprisePartnerApplication.ps1 Skript auszuführen, ein Windows PowerShell Skript, das mit Exchange Server ausgeliefert wird. Zum Ausführen dieses Skripts müssen Sie die URL für das Dokument mit den Skype for Business Server-Authentifizierungsmetadaten angeben. Dies ist in der Regel der vollqualifizierte Domänenname des Skype for Business Server Pools gefolgt vom Suffix /metadata/json/1. Beispiel:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Um Skype for Business Server als Partneranwendung zu konfigurieren, öffnen Sie die Exchange Verwaltungsshell, und führen Sie einen Befehl ähnlich dem folgenden aus (vorausgesetzt, dass Exchange auf Laufwerk C installiert wurde und den Standardordnerpfad verwendet):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Nach dem Konfigurieren der Partneranwendung wird empfohlen, Internetinformationsdienste (IIS) auf Ihren Exchange Postfach- und Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS mithilfe eines Befehls wie diesem neu starten, der den Dienst auf dem Computer atl-exchange-001 neu startet:
  
```powershell
iisreset atl-exchange-001
```

Dieser Befehl kann in der Exchange Verwaltungsshell oder in einem beliebigen anderen Befehlsfenster unter Administratorrechten ausgeführt werden.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Konfigurieren von Exchange Server als Partneranwendung für Skype for Business Server

Nachdem Sie Skype for Business Server als Partneranwendung für Exchange Server 2016 oder Exchange Server 2013 konfiguriert haben, müssen Sie Exchange Server als Partneranwendung für Skype for Business Server konfigurieren. Dazu können Sie die Skype for Business Server Verwaltungsshell verwenden und das Dokument mit den Authentifizierungsmetadaten für Exchange angeben. Dies ist in der Regel der URI des Exchange AutoErmittlungsdiensts gefolgt vom Suffix /metadata/json/1. Beispiel:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype for Business Server werden Partneranwendungen mithilfe des [Cmdlets "New-CsPartnerApplication"](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) konfiguriert. Zusätzlich zur Angabe des Metadaten-URI sollten Sie auch die Vertrauensebene der Anwendung auf "Vollständig" festlegen. dadurch können Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen. Beispiel:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode in der Dokumentation Skype for Business Server Server-zu-Server-Authentifizierung kopieren und ändern. Weitere Informationen finden Sie im Artikel "Verwalten der [Server-zu-Server-Authentifizierung (OAuth) und von Partneranwendungen" in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) Artikel.
  
Wenn Sie Partneranwendungen sowohl für Skype for Business Server als auch für Exchange Server erfolgreich konfiguriert haben, haben Sie auch die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert. Skype for Business Server enthält das Cmdlet ["Test-CsExStorageConnectivity"](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) Windows PowerShell, mit dem Sie überprüfen können, ob die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und ob der Skype for Business Server Storage Dienst eine Verbindung herstellen kann. Exchange Server. Das Cmdlet stellt hierzu eine Verbindung mit dem Postfach eines Exchange Server Benutzers her, schreibt ein Element in den Unterhaltungsverlaufsordner für diesen Benutzer und löscht dieses Element (optional).
  
Um die Integration von Skype for Business Server und Exchange Server zu testen, führen Sie in der Skype for Business Server Verwaltungsshell einen Befehl aus, der dem folgenden ähnelt:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Im vorherigen Befehl stellt der SipUri die SIP-Adresse eines Benutzers mit einem Konto auf Exchange Server dar. Der Befehl schlägt fehl, da es sich dabei nicht um ein gültiges Benutzerkonto handelt.
  
> [!NOTE]
> Wenn Sie eine 401-Antwort von diesem Cmdlet erhalten, liegt dies wahrscheinlich daran, dass die Standardkonfiguration für Exchange keine Unterstützung für das Akzeptieren von Oauth-Token enthält. Weitere Informationen zur Verwendung von Oauth in Exchange finden Sie unter Konfigurieren der [OAuth-Authentifizierung mit SharePoint 2013 und Skype for Business Server.](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help) 
  
Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen, wie der Integration der Archivierung und dem einheitlichen Kontaktspeicher fortfahren.