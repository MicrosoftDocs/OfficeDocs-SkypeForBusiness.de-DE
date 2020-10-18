---
title: 'Lync Server 2013: Planen und Bereitstellen der zweistufigen Authentifizierung'
description: 'Lync Server 2013: Planen und Bereitstellen der zweistufigen Authentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1e04fa7a0c1184152328882a7c7b4bea8e42ec0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579501"
---
# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="c704a-103">Zweistufige Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c704a-103">Two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c704a-104">_**Letztes Änderungsstand des Themas:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="c704a-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="c704a-105">Die zweistufige Authentifizierung bietet eine höhere Sicherheit, da die Benutzer zwei Authentifizierungskriterien erfüllen müssen: eine Kombination aus Benutzername und Kennwort sowie ein Token oder Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="c704a-105">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="c704a-106">Dies wird auch als etwas bekanntes bezeichnet, das Sie kennen.</span><span class="sxs-lookup"><span data-stu-id="c704a-106">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="c704a-107">Ein typisches Beispiel für die zweistufige Authentifizierung mit einem Zertifikat ist die Verwendung von Smartcards.</span><span class="sxs-lookup"><span data-stu-id="c704a-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="c704a-108">Eine Smartcard enthält ein Zertifikat, das dem Benutzerkonto zugeordnet ist, und kann anhand der auf einem Server gespeicherten Benutzer-und Zertifikatinformationen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c704a-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="c704a-109">Wenn Sie die Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat vergleichen, überprüft der Server die Anmeldeinformationen und authentifiziert den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c704a-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c704a-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c704a-110">In This Section</span></span>

[<span data-ttu-id="c704a-111">Planen der zweistufigen Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c704a-111">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="c704a-112">Konfigurieren der zweistufigen Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c704a-112">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="c704a-113">Verwenden der zweistufigen Authentifizierung mit lync-Client und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c704a-113">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

