---
title: 'Lync Server 2013: Benutzer-und Clientauthentifizierung'
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
ms.openlocfilehash: 4dbddb0dab36a8ad805691196a00a3dc8bf6f9d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="5d012-102">Benutzer-und Clientauthentifizierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d012-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d012-103">_**Letztes Änderungsstand des Themas:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="5d012-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="5d012-104">Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Microsoft lync Server 2013 authentifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="5d012-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5d012-105">Dieser Server ist normalerweise ein Standard Edition-Server, Enterprise Edition Front-End-Server oder Director.</span><span class="sxs-lookup"><span data-stu-id="5d012-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="5d012-106">Lync Server 2013 verwendet Active Directory-Domänendienste als einzelnes, vertrauenswürdiges Back-End-Repository mit Benutzeranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="5d012-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="5d012-107">Die Authentifizierung ist die Bereitstellung von Benutzerinformationen für einen vertrauenswürdigen Server.</span><span class="sxs-lookup"><span data-stu-id="5d012-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="5d012-108">In lync Server 2013 werden je nach Status und Speicherort des Benutzers die folgenden Authentifizierungsprotokolle verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d012-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="5d012-p103">**Sicherheitsprotokoll MIT Kerberos Version 5** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert eine Clientverbindung zu den Active Directory-Domänendiensten. Aus diesem Grund kann es nicht zur Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d012-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="5d012-p104">**NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die eine Verbindung über ein Endgerät von außerhalb der Unternehmensfirewall herstellen. Der Zugriffs-Edgedienst gibt Anmeldeanforderungen zur Authentifizierung an einen Director (falls vorhanden) oder an einen Front-End-Server weiter. Der Zugriffs-Edgedienst selbst führt keine Authentifizierung durch.</span><span class="sxs-lookup"><span data-stu-id="5d012-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d012-114">NTLM-Protokoll bietet weniger Schutz vor Angriffen als Kerberos, daher reduzieren einige Organisationen die Verwendung von NTLM.</span><span class="sxs-lookup"><span data-stu-id="5d012-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="5d012-115">Dadurch kann der Zugriff auf lync Server 2013 möglicherweise auf interne oder über eine VPN-oder DirectAccess-Verbindung verbundene Clients beschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="5d012-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="5d012-p106">**Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind Benutzer von außerhalb, die über keine anerkannten Active Directory-Anmeldeinformationen verfügen, jedoch zu einer Konferenz im Unternehmen eingeladen wurden und im Besitz eines gültigen Konferenzschlüssels sind. Die Digestauthentifizierung wird für keine weiteren Clientinteraktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d012-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="5d012-119">Die lync Server 2013-Authentifizierung besteht aus zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="5d012-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="5d012-120">Zwischen Client und Server wird eine Sicherheitszuordnung erstellt.</span><span class="sxs-lookup"><span data-stu-id="5d012-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="5d012-p107">Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten zu signieren und um empfangene Nachrichten zu prüfen. Wenn die Authentifizierung auf dem Server aktiviert ist, werden nicht authentifizierte Nachrichten eines Clients nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="5d012-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="5d012-p108">Jede Nachricht von einem Benutzer (nicht die Benutzeridentität selbst) wird mit Vertrauensinformationen ("Benutzervertrauensstellung") versehen. Der Server überprüft die einzelnen Nachrichten auf gültige Benutzeranmeldeinformationen. Wenn die Benutzerinformationen gültig sind, wird die Nachricht nicht nur vom ersten Server, der die Nachricht empfängt, akzeptiert, sondern auch von allen anderen Servern der vertrauenswürdigen Serverwolke wird keine Authentifizierung angefordert.</span><span class="sxs-lookup"><span data-stu-id="5d012-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="5d012-126">Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgestellt wurden, werden als vertrauenswürdig eingestuft. Möglicherweise gelten für sie jedoch zusätzliche Einschränkungen, sodass sie nicht über dieselben Berechtigungen wie die internen Benutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d012-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="5d012-127">Die ICE- und TURN-Protokolle verwenden ebenfalls Digestabfrage wie in IETF TURN RFC beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d012-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="5d012-128">Client Zertifikate bieten eine alternative Möglichkeit für Benutzer, von lync Server 2013 authentifiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="5d012-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="5d012-129">Anstatt einen Benutzernamen und ein Kennwort anzugeben, verfügen Benutzer über ein Zertifikat und den privaten Schlüssel, die dem Zertifikat entsprechen, das zum Lösen einer kryptografischen Herausforderung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5d012-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="5d012-130">(Dieses Zertifikat muss einen Antragstellernamen oder einen alternativen Antragstellernamen aufweisen, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die für Server mit lync Server 2013 vertrauenswürdig ist, innerhalb des Gültigkeitszeitraums des Zertifikats liegt und nicht widerrufen wurde.) Um authentifiziert zu werden, müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben.</span><span class="sxs-lookup"><span data-stu-id="5d012-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="5d012-131">Zertifikate sind besonders nützlich für Telefone und andere Geräte, auf denen Microsoft lync 2013 Phone Edition läuft, in denen es schwierig ist, einen Benutzernamen und/oder ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="5d012-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

