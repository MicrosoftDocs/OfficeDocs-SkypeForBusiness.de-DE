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

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="cec8a-102">Benutzer-und Clientauthentifizierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cec8a-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cec8a-103">_**Letztes Änderungsdatum des Themas:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="cec8a-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="cec8a-104">Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Microsoft lync Server 2013 authentifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="cec8a-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cec8a-105">Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server oder Director.</span><span class="sxs-lookup"><span data-stu-id="cec8a-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="cec8a-106">Lync Server 2013 basiert auf Active Directory-Domänendiensten als einzelnes, vertrauenswürdiges Back-End-Repository für Benutzeranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="cec8a-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="cec8a-107">Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen für einen vertrauenswürdigen Server.</span><span class="sxs-lookup"><span data-stu-id="cec8a-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="cec8a-108">Lync Server 2013 verwendet die folgenden Authentifizierungsprotokolle, abhängig vom Status und Standort des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cec8a-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="cec8a-109">Mit **Kerberos Version 5-Sicherheitsprotokoll** für interne Benutzer mit Active Directory-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="cec8a-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="cec8a-110">Für Kerberos ist eine Clientverbindung mit Active Directory-Domänendiensten erforderlich, weshalb Sie nicht für die Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cec8a-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="cec8a-111">**NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die von einem Endpunkt außerhalb der Unternehmensfirewall eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="cec8a-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="cec8a-112">Der Access-Edgedienst übergibt Anmeldeanforderungen an einen Director, falls vorhanden, oder einen Front-End-Server zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cec8a-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="cec8a-113">Der Access-Edgedienst selbst führt keine Authentifizierung durch.</span><span class="sxs-lookup"><span data-stu-id="cec8a-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cec8a-114">Da der Angriffsschutz des NTLM-Protokolls schwächer ist als der von Kerberos, minimieren einige Organisationen die Nutzung von NTLM.</span><span class="sxs-lookup"><span data-stu-id="cec8a-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="cec8a-115">Daher kann der Zugriff auf lync Server 2013 auf interne oder über eine VPN-oder DirectAccess-Verbindung verbundene Clients beschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="cec8a-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="cec8a-p106">Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cec8a-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="cec8a-119">Die lync Server 2013-Authentifizierung besteht aus zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="cec8a-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="cec8a-120">Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="cec8a-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="cec8a-p107">Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cec8a-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="cec8a-p108">Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht mit der Benutzeridentität selbst. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, wird die Nachricht weder vom ersten Server, der sie empfängt, noch von allen anderen Servern in der vertrauenswürdigen Servercloud herausgefordert.</span><span class="sxs-lookup"><span data-stu-id="cec8a-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="cec8a-126">Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="cec8a-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="cec8a-127">Die Protokolle ICE und TURN verwenden ebenfalls die Digestherausforderung, wie im IETF TURN RFC beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cec8a-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="cec8a-128">Client Zertifikate stellen eine alternative Möglichkeit für Benutzer dar, von lync Server 2013 authentifiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="cec8a-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="cec8a-129">Anstelle der Angabe eines Benutzernamens und eines Kennworts haben die Benutzer ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Auflösen einer kryptografischen Aufforderung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="cec8a-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="cec8a-130">(Dieses Zertifikat muss über einen Antragstellernamen oder einen alternativen Antragstellernamen verfügen, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die von Servern mit lync Server 2013 als vertrauenswürdig eingestuft wird und nicht widerrufen wurde.) Damit die Benutzer authentifiziert werden können, müssen Sie nur eine persönliche Identifikationsnummer (PIN) eingeben.</span><span class="sxs-lookup"><span data-stu-id="cec8a-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="cec8a-131">Zertifikate sind besonders nützlich für Telefone und andere Geräte mit Microsoft lync 2013 Phone Edition, bei denen es schwierig ist, einen Benutzernamen und/oder ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="cec8a-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

