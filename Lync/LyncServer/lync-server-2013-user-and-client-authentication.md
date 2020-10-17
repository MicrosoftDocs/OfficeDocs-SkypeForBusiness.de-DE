---
title: 'Lync Server 2013: Benutzer-und Clientauthentifizierung'
description: 'Lync Server 2013: Benutzer-und Clientauthentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef545dda38e9ab4236e93df769ead393648194cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569811"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Benutzer-und Clientauthentifizierung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-11_

Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Microsoft lync Server 2013 authentifiziert wurden. Dieser Server ist normalerweise ein Standard Edition-Server, Enterprise Edition Front-End-Server oder Director. Lync Server 2013 verwendet Active Directory-Domänendienste als einzelnes, vertrauenswürdiges Back-End-Repository mit Benutzeranmeldeinformationen.

Die Authentifizierung ist die Bereitstellung von Benutzerinformationen für einen vertrauenswürdigen Server. In lync Server 2013 werden je nach Status und Speicherort des Benutzers die folgenden Authentifizierungsprotokolle verwendet.

  - **Sicherheitsprotokoll MIT Kerberos Version 5** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert eine Clientverbindung zu den Active Directory-Domänendiensten. Aus diesem Grund kann es nicht zur Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden.

  - **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die eine Verbindung über ein Endgerät von außerhalb der Unternehmensfirewall herstellen. Der Zugriffs-Edgedienst gibt Anmeldeanforderungen zur Authentifizierung an einen Director (falls vorhanden) oder an einen Front-End-Server weiter. Der Zugriffs-Edgedienst selbst führt keine Authentifizierung durch.
    
    <div>
    

    > [!NOTE]  
    > NTLM-Protokoll bietet weniger Schutz vor Angriffen als Kerberos, daher reduzieren einige Organisationen die Verwendung von NTLM. Dadurch kann der Zugriff auf lync Server 2013 möglicherweise auf interne oder über eine VPN-oder DirectAccess-Verbindung verbundene Clients beschränkt werden.

    
    </div>

  - **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind Benutzer von außerhalb, die über keine anerkannten Active Directory-Anmeldeinformationen verfügen, jedoch zu einer Konferenz im Unternehmen eingeladen wurden und im Besitz eines gültigen Konferenzschlüssels sind. Die Digestauthentifizierung wird für keine weiteren Clientinteraktionen verwendet.

Die lync Server 2013-Authentifizierung besteht aus zwei Phasen:

1.  Zwischen Client und Server wird eine Sicherheitszuordnung erstellt.

2.  Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten zu signieren und um empfangene Nachrichten zu prüfen. Wenn die Authentifizierung auf dem Server aktiviert ist, werden nicht authentifizierte Nachrichten eines Clients nicht akzeptiert.

Jede Nachricht von einem Benutzer (nicht die Benutzeridentität selbst) wird mit Vertrauensinformationen ("Benutzervertrauensstellung") versehen. Der Server überprüft die einzelnen Nachrichten auf gültige Benutzeranmeldeinformationen. Wenn die Benutzerinformationen gültig sind, wird die Nachricht nicht nur vom ersten Server, der die Nachricht empfängt, akzeptiert, sondern auch von allen anderen Servern der vertrauenswürdigen Serverwolke wird keine Authentifizierung angefordert.

Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgestellt wurden, werden als vertrauenswürdig eingestuft. Möglicherweise gelten für sie jedoch zusätzliche Einschränkungen, sodass sie nicht über dieselben Berechtigungen wie die internen Benutzer verfügen.

Die ICE- und TURN-Protokolle verwenden ebenfalls Digestabfrage wie in IETF TURN RFC beschrieben.

Client Zertifikate bieten eine alternative Möglichkeit für Benutzer, von lync Server 2013 authentifiziert zu werden. Anstatt einen Benutzernamen und ein Kennwort anzugeben, verfügen Benutzer über ein Zertifikat und den privaten Schlüssel, die dem Zertifikat entsprechen, das zum Lösen einer kryptografischen Herausforderung erforderlich ist. (Dieses Zertifikat muss einen Antragstellernamen oder einen alternativen Antragstellernamen aufweisen, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die für Server mit lync Server 2013 vertrauenswürdig ist, innerhalb des Gültigkeitszeitraums des Zertifikats liegt und nicht widerrufen wurde.) Um authentifiziert zu werden, müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders nützlich für Telefone und andere Geräte, auf denen Microsoft lync 2013 Phone Edition läuft, in denen es schwierig ist, einen Benutzernamen und/oder ein Kennwort einzugeben.

</div>

<span> </span>

</div>

</div>

</div>

