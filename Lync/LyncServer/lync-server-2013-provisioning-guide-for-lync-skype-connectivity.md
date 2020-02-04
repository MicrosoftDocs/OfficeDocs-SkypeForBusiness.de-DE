---
title: 'Lync Server 2013: Leitfaden für die Bereitstellung der Lync-Skype-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f94da566e4322f9b8d1d039441c561f5ed60f6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="f845d-102">Leitfaden für die Bereitstellung der Lync-Skype-Konnektivität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f845d-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f845d-103">_**Letztes Änderungsdatum des Themas:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="f845d-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="f845d-p101">Lync Server 2013 unterstützt die Konnektivität zu Skype. Dank dieser Konnektivität können Lync 2013-Benutzer Skype-Kontakte unter Verwendung des Microsoft-Kontos (MSA) der Skype-Benutzer hinzufügen und auch Skype-Kunden können ihren Kontaktlisten Lync-Benutzer hinzufügen. Basierend auf Richtlinien, die vom Administrator in Lync Server festgelegt werden, können Lync- und Skype-Benutzer Chatnachrichten austauschen, den Anwesenheitsstatus der jeweiligen Kontakte anzeigen sowie Audio- und Videoanrufe tätigen. Die Lync-Skype-Konnektivität ist auch ein Feature von Lync Online und kann für Lync Online-Kunden im Lync Admin Center im Office 365-Portal aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f845d-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="f845d-p102">Wenn Lync Server bereits für die Herstellung der Verbindung zu Windows Messenger über PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Instant Messaging-Diensten) konfiguriert ist, ist Ihre Umgebung bereits für die Lync-Skype-Konnektivität konfiguriert. Die einzige Änderung, die Sie ggf. vornehmen möchten, ist, den vorhandenen Messenger PIC-Eintrag in "Skype" umzubenennen. Einzelheiten hierzu finden Sie unter "Konfigurieren der Einstellung des Skype PIC-Anbieters für Lync" an späterer Stelle in diesem Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="f845d-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f845d-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f845d-112">In This Section</span></span>

  - [<span data-ttu-id="f845d-113">Hinweis zu lync-Skype-Konnektivität in lync Server 2013 für lync Online-Kunden</span><span class="sxs-lookup"><span data-stu-id="f845d-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="f845d-114">Zugreifen auf die Lync Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f845d-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="f845d-115">Aktivieren der Lync-Skype-Konnektivität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f845d-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="f845d-116">Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f845d-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="f845d-117">Häufig gestellte Fragen: Bereitstellen der Skype-Konnektivität für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f845d-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

