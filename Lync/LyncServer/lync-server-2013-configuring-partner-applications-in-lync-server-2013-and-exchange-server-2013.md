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
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-12_

An einer Authentifizierung zwischen Servern sind üblicherweise drei Entitäten beteiligt: Die beiden Server, die miteinander kommunizieren müssen, und ein Sicherheitstokenserver eines Drittanbieters. Wenn zwei Server (z. B. Server A und Server B) miteinander kommunizieren müssen, beginnen beide Server in der Regel damit, dass sie einen Tokenserver kontaktieren und ein gegenseitig als vertrauenswürdig eingestuftes Sicherheitstoken erhalten. Server A präsentiert das Sicherheitstoken dann Server B (und umgekehrt), womit beide ihre Authentizität und Vertrauenswürdigkeit nachweisen.

Dies ist jedoch eine allgemeine Regel. Lync Server 2013, Microsoft Exchange Server 2013 und Microsoft SharePoint Server 2013 müssen bei der Kommunikation miteinander keinen tokenserver eines Drittanbieters verwenden. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die miteinander akzeptiert werden können, ohne dass ein separater tokenserver erforderlich ist. (Diese Funktion steht nur in lync Server 2013, Exchange 2013 und SharePoint Server 2013 zur Verfügung. Wenn Sie die Server-zu-Server-Authentifizierung für andere Server, einschließlich anderer Microsoft-Serverprodukte, einrichten müssen, müssen Sie dies mit einem Drittanbieter-tokenserver tun.)

Um die Server-zu-Server-Authentifizierung zwischen lync Server und Exchange einzurichten, müssen Sie zwei Dinge tun: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und, 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: das heißt, Sie müssen lync Server 2013 als Partneranwendung für Exchange 2013 konfigurieren, und Sie müssen Exchange 2013 als Partneranwendung für lync Server 2013 konfigurieren.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Konfigurieren von lync Server 2013 als Partner Anwendung für Exchange 2013

Am einfachsten können Sie lync Server 2013 als Partneranwendung mit Exchange 2013 konfigurieren, indem Sie das configure-EnterprisePartnerApplication. ps1-Skript ausführen, ein Windows PowerShelles Skript, das mit Exchange 2013 ausgeliefert wird. Um dieses Skript auszuführen, müssen Sie die URL für das Dokument lync Server authentifizierungsmetadaten angeben. Dabei handelt es sich normalerweise um den vollqualifizierten Domänennamen des lync Server 2013 Pools gefolgt vom Suffix/Metadata/JSON/1. Zum Beispiel:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Wenn Sie lync Server als Partneranwendung konfigurieren möchten, öffnen Sie das Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus (vorausgesetzt, dass Exchange auf Laufwerk C: installiert wurde und der Standardordnerpfad verwendet wird):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Nach dem Konfigurieren der Partneranwendung wird empfohlen, Internet Information Services (IIS) auf Ihrem Exchange-Postfach und den Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS mithilfe eines Befehls, der dem folgenden ähnelt, neu starten, um den Dienst auf dem Computer mit ATL-Exchange-001 neu zu starten:

    iisreset atl-exchange-001

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden, das unter Administratorrechten ausgeführt wird.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Konfigurieren von Exchange 2013 als Partner Anwendung für lync Server 2013

Nachdem Sie lync Server 2013 als Partneranwendung für Exchange 2013 konfiguriert haben, müssen Sie Exchange als Partneranwendung für lync Server konfigurieren. Hierzu können Sie die lync Server-Verwaltungsshell verwenden und das Dokument "authentifizierungsmetadaten" für Exchange angeben. Dies ist normalerweise der URI des Exchange-AutoErmittlungsdiensts, gefolgt vom Suffix/Metadata/JSON/1. Zum Beispiel:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

In lync Server werden Partneranwendungen mithilfe des [New-cspartnerapplication "-](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) Cmdlets konfiguriert. Zusätzlich zur Angabe des Metadaten-URI sollten Sie auch die Vertrauensebene der Anwendung auf Full festlegen. Dadurch kann Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen. Zum Beispiel:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode kopieren und ändern, der in der Dokumentation lync Server 2013 Server-zu-Server-Authentifizierung enthalten ist. Weitere Informationen finden Sie im Artikel [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Wenn Sie Partneranwendungen sowohl für lync Server als auch für Exchange erfolgreich konfiguriert haben, bedeutet dies, dass Sie die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert haben. Lync Server 2013 enthält ein Windows PowerShell-Cmdlet, [Test-csexstorageconnectivity "](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), mit dem Sie sicherstellen können, dass die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und dass der lync Server-Speicherdienst eine Verbindung mit Exchange 2013 herstellen kann. Das Cmdlet tut dies, indem eine Verbindung mit dem Postfach eines Exchange 2013 Benutzers hergestellt wird, ein Element in den Ordner Unterhaltungsverlauf für diesen Benutzer geschrieben wird und dann optional das Element gelöscht wird.

Um die Integration von lync Server 2013 und Exchange 2013 zu testen, führen Sie einen Befehl wie den folgenden aus der lync Server-Verwaltungsshell aus:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Im vorherigen Befehl stellt die SipUri die SIP-Adresse eines Benutzers mit einem Konto auf Exchange 2013 dar; der Befehl schlägt fehl, da es sich nicht um ein gültiges Benutzerkonto handelt.

Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen, wie der Integration der Archivierung und dem einheitlichen Kontaktspeicher fortfahren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

