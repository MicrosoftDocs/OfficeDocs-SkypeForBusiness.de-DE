---
title: 'Lync Server 2013: Unterstützung für Exchange-und SharePoint-Integration'
description: 'Lync Server 2013: Unterstützung für Exchange und SharePoint-Integration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7416ffa23de9a0820c3087d18254810d58444ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564861"
---
# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="e15f2-103">Unterstützung von Exchange und SharePoint-Integration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e15f2-103">Exchange and SharePoint integration support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e15f2-104">_**Letztes Änderungsstand des Themas:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="e15f2-104">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="e15f2-105">Lync Server 2013 und lync 2013 können sicher und nahtlos mit anderen Anwendungen und Server Produkten kommunizieren, einschließlich Office 2013, Exchange Server 2013, Exchange Server 2016 und SharePoint, wenn Sie diese Produkte integrieren.</span><span class="sxs-lookup"><span data-stu-id="e15f2-105">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="e15f2-106">Durch die Integration von lync Server 2013 und Office erhalten Benutzer einen kontextbezogenen Zugriff auf die Funktionen Instant Messaging (Sofortnachrichten), erweiterte Anwesenheitsinformationen, Telefonie und Konferenzen von lync.</span><span class="sxs-lookup"><span data-stu-id="e15f2-106">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="e15f2-107">Office-Benutzer können aus dem Outlook 2013 Messaging and Collaboration-Client und anderen Office-Programmen oder von einer SharePoint-Seite aus auf lync-Funktionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e15f2-107">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="e15f2-108">Benutzer können auch einen Datensatz von lync-Unterhaltungen im Outlook-Ordner "Unterhaltungsverlauf" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e15f2-108">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="e15f2-109">Wenn Sie in Exchange 2013, Exchange 2016 oder Exchange Online integriert sind, unterstützt lync Server 2013 außerdem Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e15f2-109">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="e15f2-110">Einheitlicher Kontaktspeicher, mit dem Benutzer alle Kontaktinformationen in Exchange oder Exchange Online speichern können, damit die Informationen Global in lync 2013, Exchange, Outlook und Outlook Web App zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e15f2-110">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="e15f2-111">Unter Haltungs Verlauf und Webkonferenz Verlauf, der in Exchange-Benutzerordnern gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e15f2-111">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="e15f2-112">Archivierte Inhalte aus lync, wie Chatnachrichten und Besprechungsinhalte, können im Exchange-Speicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e15f2-112">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e15f2-113">Lync Server 2013 unterstützt die Integration in frühere Versionen von Exchange Server und SharePoint Server, aber nicht alle Funktionen werden mit diesen früheren Versionen unterstützt, wie etwa die Integration von Archivierungsspeicher mit Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="e15f2-113">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="e15f2-114">Wenn Sie Ihre Benutzer zu Exchange 2013 oder Exchange 2016 migrieren, können Sie sowohl Exchange-Speicher als auch lync Server Speicher auf Interimsbasis verwenden, während Sie die Migration abschließen.</span><span class="sxs-lookup"><span data-stu-id="e15f2-114">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="e15f2-115">Die dauerhafte Verwendung von Exchange und lync Server Speicher wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e15f2-115">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="e15f2-116">Für die Integration von lync Server 2013 mit Exchange Server und SharePoint Server ist eine Server-zu-Server-Authentifizierung zwischen Servern erforderlich, auf denen lync Server 2013, Exchange Server und SharePoint Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="e15f2-116">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="e15f2-117">Lync Server 2013 unterstützt das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="e15f2-117">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="e15f2-118">Für die lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern ist kein Drittanbieter-Tokenserver erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e15f2-118">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="e15f2-119">Lync Server 2013, Exchange Server und SharePoint Server verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke miteinander verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e15f2-119">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="e15f2-120">Beispielsweise können lync Server 2013 ein Sicherheitstoken selbst ausgeben und Signieren und dieses Token bei der Kommunikation mit Exchange verwenden.</span><span class="sxs-lookup"><span data-stu-id="e15f2-120">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="e15f2-121">In diesem Fall muss kein Drittanbieter-Tokenserver verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e15f2-121">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="e15f2-122">Lync Server 2013 unterstützt die beiden Szenarien für die Server-zu-Server-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e15f2-122">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="e15f2-123">Diese beinhalten die Konfiguration der Server-zu-Server-Authentifizierung zwischen folgenden Instanzen:</span><span class="sxs-lookup"><span data-stu-id="e15f2-123">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="e15f2-124">Eine lokale Installation von lync Server 2013 und eine lokale Installation von Exchange Server 2013, Exchange Server 2016 und/oder SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="e15f2-124">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="e15f2-125">Ein paar von Office-Komponenten (beispielsweise zwischen Microsoft Exchange 365 und Microsoft lync Server 365 oder zwischen Microsoft lync Server 365 und Microsoft SharePoint 365).</span><span class="sxs-lookup"><span data-stu-id="e15f2-125">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e15f2-126">Die Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Microsoft 365-oder Office 365-Komponente wird in dieser lync Server 2013 Version nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e15f2-126">Server-to-server authentication between an on-premises server and a Microsoft 365 or Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="e15f2-127">Dies bedeutet unter anderem, dass Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von lync Server 2013 und Microsoft Exchange 365 nicht einrichten können.</span><span class="sxs-lookup"><span data-stu-id="e15f2-127">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="e15f2-128">Ausführliche Informationen zur Server-zu-Server-Authentifizierung finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e15f2-128">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>
