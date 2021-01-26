---
title: Konfigurieren von Partneranwendungen in Skype for Business Server 2015 und Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834045"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server
 
**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.
  
Die Server-zu-Server-Authentifizierung erfordert in der Regel zwei Server, die miteinander kommunizieren müssen, und einen Sicherheitstokenserver eines Drittanbieters. Wenn Server A und Server B kommunizieren müssen, beginnen beide Server in der Regel mit dem Kontaktieren eines Tokenservers und dem Abrufen eines gegenseitig vertrauenswürdigen Sicherheitstokens. Server A stellt dieses Sicherheitstoken dann Server B (und umgekehrt) als Möglichkeit vor, seine Authentizität und Vertrauenswürdigkeit zu gewährleisten.
  
Dies ist jedoch eine allgemeine Regel. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 müssen bei der Kommunikation miteinander keinen Tokenserver eines Drittanbieters verwenden. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die voneinander akzeptiert werden können, ohne dass ein separater Tokenserver erforderlich ist. (Diese Funktion ist nur in Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 verfügbar. Wenn Sie die Server-zu-Server-Authentifizierung mit anderen Servern einrichten müssen, einschließlich anderer Microsoft-Serverprodukte, müssen Sie dazu einen Tokenserver eines Drittanbieters verwenden.)
  
Zum Einrichten der Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server müssen Sie zwei Dinge tun: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: Das bedeutet, dass Sie Skype for Business Server als Partneranwendung für Exchange Server konfigurieren müssen, und Sie müssen Exchange Server als Partneranwendung für Skype for Business Server konfigurieren.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Konfigurieren von Skype for Business Server als Partneranwendung für Exchange Server

Die einfachste Möglichkeit, Skype for Business Server als Partneranwendung mit Exchange Server 2016 oder Exchange Server 2013 zu konfigurieren, besteht in der Ausführung des Configure-EnterprisePartnerApplication.ps1-Skripts, einem Windows PowerShell-Skript, das im Exchange Server.. Zum Ausführen dieses Skripts müssen Sie die URL für das Dokument mit den Skype for Business #A0 angeben. Dies ist in der Regel der vollqualifizierte Domänenname des Skype for Business Server-Pools, gefolgt vom Suffix /metadata/json/1. Beispiel:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Um Skype for Business Server als Partneranwendung zu konfigurieren, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Nach dem Konfigurieren der Partneranwendung wird empfohlen, internetinformationsdienste (Internet Information Services, IIS) auf Dem Postfach- und Clientzugriffsservern von Exchange zu beenden und neu zu starten. Sie können IIS mit einem Befehl wie dem folgenden neu starten, der den Dienst auf dem Computer "atl-exchange-001" neu startet:
  
```powershell
iisreset atl-exchange-001
```

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem beliebigen anderen Befehlsfenster ausgeführt werden, das mit Administratorrechten ausgeführt wird.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Konfigurieren Exchange Server als Partneranwendung für Skype for Business Server

Nachdem Sie Skype for Business Server als Partneranwendung für Exchange Server 2016 oder Exchange Server 2013 konfiguriert haben, müssen Sie Exchange Server als Partneranwendung für Skype for Business Server konfigurieren. Dazu können Sie die Skype for Business #A0 verwenden und das Dokument mit den Authentifizierungsmetadaten für Exchange angeben. Dies ist in der Regel der URI des Exchange-AutoErmittlungsdiensts, gefolgt vom Suffix /metadata/json/1. Beispiel:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype for Business Server werden Partneranwendungen mithilfe des [Cmdlets "New-CsPartnerApplication"](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) konfiguriert. Sie sollten nicht nur den Metadaten-URI angeben, sondern auch die Vertrauensebene der Anwendung auf "Vollständig" festlegen. Dadurch kann Exchange sich selbst und alle autorisierten Benutzer im Bereich darstellen. Beispiel:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode in der Dokumentation zur Server-zu-Server-Authentifizierung von Skype for Business Server kopieren und ändern. Weitere Informationen finden Sie im Artikel zum Verwalten der [Server-zu-Server-Authentifizierung (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) und von Partneranwendungen in Skype for Business Server.
  
Wenn Sie Partneranwendungen für Skype for Business Server und Exchange Server erfolgreich konfiguriert haben, haben Sie auch die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert. Skype for Business Server enthält das Windows PowerShell-Cmdlet ["Test-CsExStorageConnectivity",](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) mit dem Sie überprüfen können, ob die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und ob der Skype for Business Server Storage Service eine Verbindung mit Exchange Server. Das Cmdlet stellt dazu eine Verbindung mit dem Postfach eines Exchange Server-Benutzers sicher, schreibt ein Element in den Ordner "Unterhaltungsverlauf" für diesen Benutzer und löscht dieses Element (optional).
  
Führen Sie einen Befehl wie den folgenden aus der Skype for Business Server-Verwaltungsshell aus, um die Integration von Skype for Business Server und Exchange Server zu testen:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Im vorstehenden Befehl stellt der SipUri die #A0 eines Benutzers dar, für den ein Konto Exchange Server; Der Befehl kann nicht ausgeführt werden, wenn es sich nicht um ein gültiges Benutzerkonto handelt.
  
> [!NOTE]
> Wenn Sie eine 401-Antwort von diesem Cmdlet erhalten, liegt dies wahrscheinlich daran, dass die Standardkonfiguration für Exchange keine Unterstützung für das Akzeptieren von Oauth-Token enthält. Weitere Informationen zur Verwendung von Oauth in Exchange finden Sie unter "Konfigurieren der [OAuth-Authentifizierung mit SharePoint 2013 und Skype for Business Server".](https://go.microsoft.com/fwlink/p/?LinkId=513103) 
  
Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen, wie der Integration der Archivierung und dem einheitlichen Kontaktspeicher fortfahren.
