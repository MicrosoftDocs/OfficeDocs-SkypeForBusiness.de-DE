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
description: 'Zusammenfassung: Konfigurieren der Serverauthentifizierung für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: 47f192ce11a48ab4c256ac6a1f499aa24563a725
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110111"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server
 
**Zusammenfassung:** Konfigurieren Sie server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.
  
Die Server-zu-Server-Authentifizierung erfordert in der Regel zwei Server, die miteinander kommunizieren müssen, und einen Sicherheitstokenserver eines Drittanbieters. Wenn Server A und Server B kommunizieren müssen, beginnen beide Server in der Regel, indem sie einen Tokenserver kontaktieren und ein sicherheitstoken mit gegenseitigem Vertrauen abrufen. Server A stellt dann dieses Sicherheitstoken für Server B (und umgekehrt) als Möglichkeit bereit, seine Authentizität und Vertrauenswürdigkeit zu gewährleisten.
  
Dies ist jedoch eine allgemeine Regel. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 müssen keinen Tokenserver eines Drittanbieters verwenden, wenn sie miteinander kommunizieren. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die voneinander akzeptiert werden können, ohne dass ein separater Tokenserver erforderlich ist. (Diese Funktion ist nur in Skype for Business Server, Exchange Server 2016, Exchange Server 2013 und SharePoint Server 2013 verfügbar. Wenn Sie die Server-zu-Server-Authentifizierung mit anderen Servern einrichten müssen, einschließlich anderer Microsoft Serverprodukte, müssen Sie dazu einen Tokenserver eines Drittanbieters verwenden.)
  
Zum Einrichten der Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server müssen Sie zwei Dinge tun: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: Das bedeutet, Sie müssen Skype for Business Server als Partneranwendung für Exchange Server konfigurieren, und Sie müssen Exchange Server als Partneranwendung für Skype for Business Server konfigurieren.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Konfigurieren von Skype for Business Server als Partneranwendung für Exchange Server

Die einfachste Möglichkeit, Skype for Business Server als Partneranwendung mit Exchange Server 2016 oder Exchange Server 2013 zu konfigurieren, besteht im Ausführen des Configure-EnterprisePartnerApplication.ps1-Skripts, einem Windows PowerShell-Skript, das mit Exchange Server. Zum Ausführen dieses Skripts müssen Sie die URL für das Skype for Business #A0 angeben. Dies ist in der Regel der vollqualifizierte Domänenname des Skype for Business Server-Pools, gefolgt vom Suffix /metadata/json/1. Zum Beispiel:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Um Skype for Business Server als Partneranwendung zu konfigurieren, öffnen Sie die #A0 und führen einen Befehl wie den folgenden aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Nach dem Konfigurieren der Partneranwendung wird empfohlen, internetinformationsdienste (Internet Information Services, IIS) auf Ihrem Exchange-Postfach und auf Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS mit einem Befehl wie dem folgenden neu starten, der den Dienst auf dem Computer atl-exchange-001 neu startet:
  
```powershell
iisreset atl-exchange-001
```

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem beliebigen anderen Befehlsfenster ausgeführt werden, das mit Administratorrechten ausgeführt wird.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Konfigurieren Exchange Server als Partneranwendung für Skype for Business Server

Nachdem Sie Skype for Business Server als Partneranwendung für Exchange Server 2016 oder Exchange Server 2013 konfiguriert haben, müssen Sie Exchange Server als Partneranwendung für Skype for Business Server konfigurieren. Dies kann mithilfe der Skype for Business #A0 und dem Angeben des Authentifizierungsmetadatendokuments für Exchange geschehen. Dies ist in der Regel der URI des Exchange-AutoErmittlungsdiensts gefolgt vom Suffix /metadata/json/1. Zum Beispiel:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype for Business Server werden Partneranwendungen mithilfe des [Cmdlets New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) konfiguriert. Sie sollten nicht nur den Metadaten-URI angeben, sondern auch die Anwendungsvertrauensebene auf Vollständig festlegen. Dadurch kann Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen. Zum Beispiel:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode in der Skype for Business Server-zu-Server-Authentifizierungsdokumentation kopieren und ändern. Weitere Informationen finden Sie im Artikel Verwalten von [Server-zu-Server-Authentifizierung (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) und Partneranwendungen in Skype for Business Server.
  
Wenn Sie Partneranwendungen für Skype for Business Server und Exchange Server erfolgreich konfiguriert haben, haben Sie auch die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert. Skype for Business Server enthält ein Windows PowerShell-Cmdlet, [Test-CsExStorageConnectivity,](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) mit dem Sie überprüfen können, ob die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und ob der Skype for Business Server Storage Service eine Verbindung mit Exchange Server. Das Cmdlet führt dazu eine Verbindung mit dem Postfach eines Exchange Server-Benutzers aus, schreibt ein Element in den Ordner Unterhaltungsverlauf für diesen Benutzer und löscht dieses Element anschließend (optional).
  
Um die Integration von Skype for Business Server und Exchange Server zu testen, führen Sie einen Befehl wie den folgenden aus der Skype for Business Server-Verwaltungsshell aus:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Im vorherigen Befehl stellt der SipUri die #A0 eines Benutzers mit einem Konto auf Exchange Server; Ihr Befehl wird fehlschlagen, da es sich nicht um ein gültiges Benutzerkonto handelt.
  
> [!NOTE]
> Wenn Sie eine 401-Antwort von diesem Cmdlet erhalten, liegt dies wahrscheinlich daran, dass die Standardkonfiguration für Exchange keine Unterstützung für die Annahme von Oauth-Token enthält. Weitere Informationen zur Verwendung von Oauth in Exchange finden Sie unter [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help). 
  
Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen, wie der Integration der Archivierung und dem einheitlichen Kontaktspeicher fortfahren.