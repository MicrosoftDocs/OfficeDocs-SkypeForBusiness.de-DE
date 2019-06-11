---
title: 'Lync Server 2013: Benutzer-und Clientauthentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Benutzer-und Clientauthentifizierung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-11_

Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Microsoft lync Server 2013 authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server oder Director. Lync Server 2013 basiert auf Active Directory-Domänendiensten als einzelnes, vertrauenswürdiges Back-End-Repository für Benutzeranmeldeinformationen.

Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen für einen vertrauenswürdigen Server. Lync Server 2013 verwendet die folgenden Authentifizierungsprotokolle, abhängig vom Status und Standort des Benutzers.

  - Mit **Kerberos Version 5-Sicherheitsprotokoll** für interne Benutzer mit Active Directory-Anmeldeinformationen Für Kerberos ist eine Clientverbindung mit Active Directory-Domänendiensten erforderlich, weshalb Sie nicht für die Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden kann.

  - **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die von einem Endpunkt außerhalb der Unternehmensfirewall eine Verbindung herstellen. Der Access-Edgedienst übergibt Anmeldeanforderungen an einen Director, falls vorhanden, oder einen Front-End-Server zur Authentifizierung. Der Access-Edgedienst selbst führt keine Authentifizierung durch.
    
    <div>
    

    > [!NOTE]  
    > Da der Angriffsschutz des NTLM-Protokolls schwächer ist als der von Kerberos, minimieren einige Organisationen die Nutzung von NTLM. Daher kann der Zugriff auf lync Server 2013 auf interne oder über eine VPN-oder DirectAccess-Verbindung verbundene Clients beschränkt sein.

    
    </div>

  - Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.

Die lync Server 2013-Authentifizierung besteht aus zwei Phasen:

1.  Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.

2.  Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.

Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht mit der Benutzeridentität selbst. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, wird die Nachricht weder vom ersten Server, der sie empfängt, noch von allen anderen Servern in der vertrauenswürdigen Servercloud herausgefordert.

Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.

Die Protokolle ICE und TURN verwenden ebenfalls die Digestherausforderung, wie im IETF TURN RFC beschrieben.

Client Zertifikate stellen eine alternative Möglichkeit für Benutzer dar, von lync Server 2013 authentifiziert zu werden. Anstelle der Angabe eines Benutzernamens und eines Kennworts haben die Benutzer ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Auflösen einer kryptografischen Aufforderung benötigt wird. (Dieses Zertifikat muss über einen Antragstellernamen oder einen alternativen Antragstellernamen verfügen, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die von Servern mit lync Server 2013 als vertrauenswürdig eingestuft wird und nicht widerrufen wurde.) Damit die Benutzer authentifiziert werden können, müssen Sie nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders nützlich für Telefone und andere Geräte mit Microsoft lync 2013 Phone Edition, bei denen es schwierig ist, einen Benutzernamen und/oder ein Kennwort einzugeben.

</div>

<span> </span>

</div>

</div>

</div>

