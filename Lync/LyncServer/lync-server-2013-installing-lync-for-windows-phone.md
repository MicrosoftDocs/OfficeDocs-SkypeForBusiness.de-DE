---
title: 'Lync Server 2013: Installieren von lync für Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="f8cc1-102">Installieren von lync für Windows phone in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8cc1-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8cc1-103">_**Letztes Änderungsdatum des Themas:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="f8cc1-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="f8cc1-104">Lync 2013 für Windows Phone ist eine vom Benutzer installierbare Anwendung, die auf dem Windows Phone Marketplace zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="f8cc1-105">Installieren von lync für Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="f8cc1-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="f8cc1-106">Sie können Ihre Benutzer anweisen, lync 2013 für Windows Phone auf Ihren Geräten zu installieren, indem Sie Sie an den Windows <http://go.microsoft.com/fwlink/p/?linkid=231901>Phone Marketplace unterrichten.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="f8cc1-107">Wenn Sie einen DNS-SRV-Eintrag zum Veröffentlichen von Exchange-Webdiensten verwenden</span><span class="sxs-lookup"><span data-stu-id="f8cc1-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="f8cc1-108">Um die Exchange-Integration für lync-Clients zu aktivieren, veröffentlichen einige Organisationen die Exchange-Webdienste-URL mithilfe eines DNS-SRV-Eintrags.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="f8cc1-109">Das Dokument "Understanding and Troubleshooting Exchange Integration", das im Microsoft Download Center [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)verfügbar ist, beschreibt Szenarien, in denen dies erforderlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="f8cc1-110">Die Exchange-Integration für Windows Phone-Benutzer funktioniert in diesem Szenario jedoch nicht, da die Windows Phone-Plattform keine SRV-Lookups unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="f8cc1-111">Sie müssen Windows Phone-Benutzer anweisen, die Exchange-Webdienste-URL anzugeben, anstatt dem Smartphone den automatischen Erkennen des Servers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="f8cc1-112">Weisen Sie die Benutzer an, die lync-Einstellungen auf Ihren Windows-Smartphones wie folgt zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f8cc1-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="f8cc1-113">Wählen Sie in Windows phone in den lync-Einstellungen den Bildschirm **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="f8cc1-114">Verschieben Sie den **Server automatisch erkennen** auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="f8cc1-115">Tippen Sie auf das leere Feld, und geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die URL für Exchange Web Services ein.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8cc1-116">Sie können entweder den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die vollständige URL Ihres Exchange-Webdienste-Servers angeben.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="f8cc1-117">Wenn Sie den FQDN angeben, werden das Protokoll (https://) und der Exchange-Webdienste Pfad (/EWS/Exchange.asmx) automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="f8cc1-118">Wenn ihr Pfad für Exchange-Webdienste anders ist, können Sie die vollständige URL angeben.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="f8cc1-119">Schließen Sie den Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="f8cc1-120">Überprüfen der Installation des mobilen Clients</span><span class="sxs-lookup"><span data-stu-id="f8cc1-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="f8cc1-121">Nachdem Sie den Client konfiguriert und sich erfolgreich angemeldet haben, verwenden Sie die folgenden Tests, um zu überprüfen, ob Ihre Installation von lync 2013 auf Ihrem mobilen Gerät ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="f8cc1-122">**Suchen nach einem Kontakt im Unternehmensverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="f8cc1-123">Tippen Sie in der Kontaktliste unten auf **Suchen** .</span><span class="sxs-lookup"><span data-stu-id="f8cc1-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="f8cc1-124">Suchen Sie einen Kontakt, der nur in der globalen Adressliste vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="f8cc1-125">Stellen Sie sicher, dass der Kontaktname in den Suchergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="f8cc1-126">**Testen der Chat- und Anwesenheitsfunktionen**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="f8cc1-127">Tippen Sie in der Kontaktliste auf einen Kontakt.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="f8cc1-128">Tippen Sie auf der Visitenkarte auf das Symbol **Chat** .</span><span class="sxs-lookup"><span data-stu-id="f8cc1-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="f8cc1-129">Stellen Sie sicher, dass ein Chatfenster zum Eingeben und Senden einer Sofortnachricht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="f8cc1-130">**Testen der Auswahlkonferenz**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="f8cc1-131">Planen Sie in Outlook eine lync-Besprechung.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="f8cc1-132">Öffnen Sie auf dem mobilen Gerät die Besprechungseinladung.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="f8cc1-133">Klicken Sie in der Besprechung auf den Link, um an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="f8cc1-134">Nehmen Sie den Anruf vom Konferenzdienst entgegen und stellen Sie sicher, dass Sie mit dem Besprechungsaudio verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="f8cc1-135">**Testen von Pushbenachrichtigungen**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="f8cc1-136">Registrieren Sie sich auf dem mobilen Gerät von Benutzer a bei lync mit dem Konto von Benutzer a.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="f8cc1-137">Öffnen Sie eine andere Anwendung auf dem mobilen Gerät.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="f8cc1-138">Bei einem anderen Client können Sie sich mit dem Konto von Benutzer B bei lync anmelden.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="f8cc1-139">Senden Sie eine Sofortnachricht von Benutzer B an Benutzer A.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="f8cc1-140">Stellen Sie sicher, dass die Sofortnachricht auf dem mobilen Gerät von Benutzer A erscheint.</span><span class="sxs-lookup"><span data-stu-id="f8cc1-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

