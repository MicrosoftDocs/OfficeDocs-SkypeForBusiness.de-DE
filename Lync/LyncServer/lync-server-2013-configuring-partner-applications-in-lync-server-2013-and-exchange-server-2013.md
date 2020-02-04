---
title: Konfigurieren von Partneranwendungen in lync Server 2013 und Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c60e018a86ec0838791d5fc46845460b5f039f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-12_

Die Server-zu-Server-Authentifizierung umfasst in der Regel drei Entitäten: die beiden Server, die miteinander kommunizieren müssen, und einen Sicherheitstoken-Server eines Drittanbieters. Wenn zwei Server (beispielsweise Server A und Server B) kommunizieren müssen, beginnen diese beiden Server in der Regel mit einem tokenserver, und Sie erhalten ein gegenseitig vertrauenswürdiges Sicherheitstoken. Server a stellen Sie dann dieses Sicherheitstoken auf Server B (und umgekehrt) als eine Möglichkeit dar, um seine Authentizität und Zuverlässigkeit zu gewährleisten.

Das ist jedoch eine allgemeine Regel. Lync Server 2013, Microsoft Exchange Server 2013 und Microsoft SharePoint Server 2013 müssen keinen tokenserver eines Drittanbieters verwenden, wenn Sie miteinander kommunizieren. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die voneinander akzeptiert werden können, ohne dass ein separater tokenserver erforderlich ist. (Diese Funktion steht nur in lync Server 2013, Exchange 2013 und SharePoint Server 2013 zur Verfügung. Wenn Sie die Server-zu-Server-Authentifizierung für andere Server, einschließlich anderer Microsoft-Serverprodukte, einrichten müssen, müssen Sie dies unter Verwendung eines tokenserver eines Drittanbieters tun.)

Damit Sie die Server-zu-Server-Authentifizierung zwischen lync Server und Exchange einrichten können, müssen Sie zwei Schritte ausführen: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: Dies bedeutet, dass Sie lync Server 2013 so konfigurieren müssen, dass es sich um eine Partneranwendung für Exchange 2013 handelt, und Sie müssen Exchange 2013 so konfigurieren, dass es sich um eine Partneranwendung für lync Server 2013 handelt.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Konfigurieren von lync Server 2013 als Partner Anwendung für Exchange 2013

Die einfachste Möglichkeit, lync Server 2013 auf eine Partneranwendung mit Exchange 2013 zu konfigurieren, besteht darin, das configure-EnterprisePartnerApplication. ps1-Skript auszuführen, ein Windows PowerShell-Skript, das mit Exchange 2013 ausgeliefert wird. Um dieses Skript ausführen zu können, müssen Sie die URL für das Dokument für die lync Server-authentifizierungsmetadaten angeben. Dies ist in der Regel der vollqualifizierte Domänenname des lync Server 2013-Pools, gefolgt vom Suffix/Metadata/JSON/1. Beispiel:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Wenn Sie lync Server als Partneranwendung konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Nachdem Sie die Partneranwendung konfiguriert haben, empfiehlt es sich, Internet Informationsdienste (IIS) auf Ihrem Exchange-Postfach und den Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS neu starten, indem Sie einen ähnlichen Befehl verwenden, mit dem der Dienst auf dem Computer "ATL-Exchange-001" neu gestartet wird:

    iisreset atl-exchange-001

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden, das unter Administratorprivilegien ausgeführt wird.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Konfigurieren von Exchange 2013 als Partner Anwendung für lync Server 2013

Nachdem Sie lync Server 2013 als Partneranwendung für Exchange 2013 konfiguriert haben, müssen Sie Exchange so konfigurieren, dass es sich um eine Partneranwendung für lync Server handelt. Dies kann mithilfe der lync Server-Verwaltungsshell und dem Angeben des Dokuments für die authentifizierungsmetadaten für Exchange erfolgen. Dies ist in der Regel der URI des Exchange-AutoErmittlungsdiensts, gefolgt vom Suffix/Metadata/JSON/1. Beispiel:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

In lync Server werden Partneranwendungen mithilfe des Cmdlets [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) konfiguriert. Zusätzlich zur Angabe des Metadaten-URIs sollten Sie auch die Vertrauensebene der Anwendung auf Full festlegen. Dadurch kann Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen. Beispiel:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Sie können eine Partneranwendung auch erstellen, indem Sie den Skriptcode, der in der Dokumentation zur Server-zu-Server-Authentifizierung von lync Server 2013 gefunden wurde, kopieren und ändern. Weitere Informationen finden Sie im Artikel [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Wenn Sie erfolgreich Partneranwendungen für lync Server und Exchange konfiguriert haben, bedeutet dies, dass Sie auch die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert haben. Lync Server 2013 enthält ein Windows PowerShell-Cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), mit dem Sie überprüfen können, ob die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und der lync Server-Speicherdienst eine Verbindung mit Exchange 2013 herstellen kann. Das Cmdlet führt dazu eine Verbindung mit dem Postfach eines Exchange 2013-Benutzers, wobei ein Element in den Ordner "Konversations Verlauf" für diesen Benutzer geschrieben wird, und dann optional das Element gelöscht.

Um die Integration von lync Server 2013 und Exchange 2013 zu testen, führen Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl wie den folgenden aus:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Im vorangehenden Befehl stellt der SipUri die SIP-Adresse eines Benutzers mit einem Konto in Exchange 2013 dar; Ihr Befehl schlägt fehl, da es sich nicht um ein gültiges Benutzerkonto handelt.

Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen (z. B. der Integration der Archivierung und des einheitlichen Kontaktspeichers) fortfahren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

