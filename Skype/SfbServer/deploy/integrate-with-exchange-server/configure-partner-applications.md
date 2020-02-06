---
title: Konfigurieren von Partneranwendungen in Skype for Business Server 2015 und Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: 9512d271b23f26afcb1ef6385a1a6dd5d513c948
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797076"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server
 
**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.
  
An einer Server-zu-Server-Authentifizierung sind üblicherweise zwei Server, die miteinander kommunizieren müssen, und ein Sicherheitstokenserver eines Drittanbieters beteiligt. Wenn Server a und Server B kommunizieren müssen, beginnen diese beiden Server in der Regel mit einem tokenserver, und Sie erhalten ein vertrauenswürdiges Sicherheitstoken. Server A präsentiert das Sicherheitstoken dann Server B (und umgekehrt), womit beide ihre Authentizität und Vertrauenswürdigkeit nachweisen.
  
Das ist jedoch eine allgemeine Regel. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 brauchen keinen tokenserver eines Drittanbieters, wenn Sie miteinander kommunizieren. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die voneinander akzeptiert werden können, ohne dass ein separater tokenserver erforderlich ist. (Diese Funktion steht nur in Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 zur Verfügung. Wenn Sie die Server-zu-Server-Authentifizierung für andere Server, einschließlich anderer Microsoft-Serverprodukte, einrichten müssen, müssen Sie dies unter Verwendung eines tokenserver eines Drittanbieters tun.)
  
Damit Sie die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server einrichten können, müssen Sie zwei Schritte ausführen: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: Dies bedeutet, dass Sie Skype for Business Server als Partneranwendung für Exchange Server konfigurieren müssen, und Sie müssen Exchange Server als eine Partneranwendung für Skype konfigurieren. für Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Konfigurieren von Skype for Business Server als Partner Anwendung für Exchange Server

Die einfachste Möglichkeit zum Konfigurieren von Skype for Business Server für eine Partneranwendung mit Exchange Server 2016 oder Exchange Server 2013 besteht darin, das configure-EnterprisePartnerApplication. ps1-Skript auszuführen, ein Windows PowerShell-Skript, das mit Exchange Server ausgeliefert wird. Um dieses Skript ausführen zu können, müssen Sie die URL für das Dokument für die Authentifizierung von Skype for Business Server-Metadaten angeben. Dies ist in der Regel der vollqualifizierte Domänenname des Skype for Business Server-Pools, gefolgt vom Suffix/Metadata/JSON/1. Beispiel:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Wenn Sie Skype for Business Server als Partneranwendung konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Nachdem Sie die Partneranwendung konfiguriert haben, empfiehlt es sich, Internet Informationsdienste (IIS) auf Ihrem Exchange-Postfach und den Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS neu starten, indem Sie einen ähnlichen Befehl verwenden, mit dem der Dienst auf dem Computer "ATL-Exchange-001" neu gestartet wird:
  
```powershell
iisreset atl-exchange-001
```

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden, das unter Administratorprivilegien ausgeführt wird.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Konfigurieren von Exchange Server als Partner Anwendung für Skype for Business Server

Nachdem Sie Skype for Business Server als Partneranwendung für Exchange Server 2016 oder Exchange Server 2013 konfiguriert haben, müssen Sie Exchange Server so konfigurieren, dass es sich um eine Partneranwendung für Skype for Business Server handelt. Dies kann über die Skype for Business Server-Verwaltungsshell und die Angabe des authentifizierungsmetadaten-Dokuments für Exchange erfolgen. Dies ist in der Regel der URI des Exchange-AutoErmittlungsdiensts, gefolgt vom Suffix/Metadata/JSON/1. Beispiel:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype for Business Server werden Partneranwendungen mithilfe des Cmdlets [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) konfiguriert. Zusätzlich zur Angabe des Metadaten-URIs sollten Sie auch die Vertrauensebene der Anwendung auf Full festlegen. Dadurch kann Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen. Beispiel:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode kopieren und ändern, der in der Dokumentation zur Authentifizierung von Skype for Business Server Server-zu-Server-Authentifizierung zu finden ist. Weitere Informationen finden Sie im Artikel [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) .
  
Wenn Sie erfolgreich Partneranwendungen für Skype for Business Server und Exchange Server konfiguriert haben, haben Sie auch die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert. Skype for Business Server enthält ein Windows PowerShell-Cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , mit dem Sie überprüfen können, ob die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und dass der Skype for Business Server-Speicherdienst eine Verbindung mit Exchange Server herstellen kann. Das Cmdlet führt hierzu eine Verbindung mit dem Postfach eines Exchange Server-Benutzers aus, wobei ein Element in den Ordner "Konversations Verlauf" für diesen Benutzer geschrieben und dann (optional) das Element gelöscht wird.
  
Um die Integration von Skype for Business Server und Exchange Server zu testen, führen Sie in der Skype for Business Server-Verwaltungsshell einen Befehl wie den folgenden aus:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Im vorangehenden Befehl stellt der SipUri die SIP-Adresse eines Benutzers mit einem Konto auf Exchange Server dar. Ihr Befehl schlägt fehl, da es sich nicht um ein gültiges Benutzerkonto handelt.
  
> [!NOTE]
> Wenn Sie eine 401-Antwort von diesem Cmdlet erhalten, liegt dies wahrscheinlich daran, dass die Standardkonfiguration für Exchange keine Unterstützung für das annehmen von OAuth-Token umfasst. Weitere Informationen zur Verwendung von OAuth in Exchange finden Sie unter [Konfigurieren der OAuth-Authentifizierung mit SharePoint 2013 und Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen (z. B. der Integration der Archivierung und des einheitlichen Kontaktspeichers) fortfahren.
