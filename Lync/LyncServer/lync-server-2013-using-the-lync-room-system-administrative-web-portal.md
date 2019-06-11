---
title: 'Lync Server 2013: Verwenden des Webportals zur Verwaltung des Lync-Raumsystems'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="11a61-102">Verwenden des Webportals zur Verwaltung des Lync-Raumsystems in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11a61-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11a61-103">_**Letztes Änderungsdatum des Themas:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="11a61-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="11a61-104">Nachdem Sie LRS auf dem Server bereitgestellt haben, können Sie den Status aller LRS-Räume überprüfen, indem Sie sich über einen Browser beim LRS Administrative Web Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="11a61-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="11a61-105">Anmelden</span><span class="sxs-lookup"><span data-stu-id="11a61-105">Sign in</span></span>

1.  <span data-ttu-id="11a61-106">Navigieren Sie zu der folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="11a61-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="11a61-107">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="11a61-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="11a61-108">Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der LRSSupportAdminGroup-Sicherheitsgruppe hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="11a61-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="11a61-109">![Anmeldebildschirm des lync Room System admin Portals] (images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm des lync Room System admin Portals")</span><span class="sxs-lookup"><span data-stu-id="11a61-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="11a61-110">Seite mit der Zusammenfassung des LRS Administrative Web Portals</span><span class="sxs-lookup"><span data-stu-id="11a61-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="11a61-111">Die Seite "Zusammenfassung" enthält die folgenden Informationen für alle LRS-Räume, die auf dem Server bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="11a61-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="11a61-112">**Markieren**   Sie den benutzerdefinierten Namen, den der Administrator dem Chatroom übergibt.</span><span class="sxs-lookup"><span data-stu-id="11a61-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="11a61-113">Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="11a61-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="11a61-114">**Integrität**   der Integritätsstatus des Raums, der vom Aggregat Status des Raums abgeleitet wird, der im Abschnitt "Gesundheit" auf der Seite "Raumeinstellungen" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="11a61-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="11a61-115">**Als nächstes treffen**   Sie das Datum und die Uhrzeit, an dem die nächste Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="11a61-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="11a61-116">**LRS-Version, Hersteller, Modell**   diese Werte sind in LRS voreingestellt.</span><span class="sxs-lookup"><span data-stu-id="11a61-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="11a61-117">Je nach Hersteller können diese Felder auch leer sein.</span><span class="sxs-lookup"><span data-stu-id="11a61-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="11a61-118">**Letzte Aktualisierung**   zeigt den Zeitpunkt an, zu dem die Webseite zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="11a61-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="11a61-119">![Lync Room-System Administrator-Portal – Zusammenfassungsansicht] (images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room-System Administrator-Portal – Zusammenfassungsansicht")</span><span class="sxs-lookup"><span data-stu-id="11a61-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="11a61-120">LRS-Rauminformationen</span><span class="sxs-lookup"><span data-stu-id="11a61-120">LRS Room Information</span></span>

<span data-ttu-id="11a61-121">Im Abschnitt Rauminformationen des Portals können Sie einzelne LRS-Räume anzeigen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="11a61-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="11a61-122">Es enthält vier Abschnitte: Einstellungen, Details, Problembehandlung und Zustand.</span><span class="sxs-lookup"><span data-stu-id="11a61-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="11a61-123">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="11a61-123">Settings</span></span>

<span data-ttu-id="11a61-124">Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen.</span><span class="sxs-lookup"><span data-stu-id="11a61-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="11a61-125">Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die LRS-Konsole neu gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="11a61-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="11a61-126">Es werden nur die Einstellungen für System Updates für lync Room-Systeme angezeigt, die Version 15,12 und höher sind.</span><span class="sxs-lookup"><span data-stu-id="11a61-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="11a61-127">![Einstellungen für das lync Room-System Administrator-Portal] (images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Einstellungen für das lync Room-System Administrator-Portal")</span><span class="sxs-lookup"><span data-stu-id="11a61-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="11a61-128">Details</span><span class="sxs-lookup"><span data-stu-id="11a61-128">Details</span></span>

<span data-ttu-id="11a61-129">Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des LRS-Raums, einschließlich: die Uhrzeit der letzten Aktualisierung. nächste Besprechung; Letzte Updates, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mikrofon und Klingelton Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.</span><span class="sxs-lookup"><span data-stu-id="11a61-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="11a61-130">![Lync Room-System Administrator-Portal-Detail Ansicht] (images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room-System Administrator-Portal-Detail Ansicht")</span><span class="sxs-lookup"><span data-stu-id="11a61-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="11a61-131">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="11a61-131">Troubleshooting</span></span>

<span data-ttu-id="11a61-132">Im Abschnitt zur Problembehandlung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern.</span><span class="sxs-lookup"><span data-stu-id="11a61-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="11a61-133">Sie können auch die LRS-Konsole (LRS-Benutzeroberfläche) neu starten oder das gesamte System neu starten.</span><span class="sxs-lookup"><span data-stu-id="11a61-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="11a61-134">Um Protokolle zu sammeln, geben Sie einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen verfügt, die dem LRS-Computerkonto zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="11a61-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="11a61-135">Bei einer sehr umfangreichen Protokollgröße kann es bis zu 5 Minuten dauern, bis der Vorgang zur Erfassung der Protokolle abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="11a61-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="11a61-136">Sie erhalten den aktuellen Status, wenn Sie die Seite aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="11a61-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="11a61-137">![Lync Room-System Administrator-Portal Raum Protokollierung] (images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room-System Administrator-Portal Raum Protokollierung")</span><span class="sxs-lookup"><span data-stu-id="11a61-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="11a61-138">Integrität</span><span class="sxs-lookup"><span data-stu-id="11a61-138">Health</span></span>

<span data-ttu-id="11a61-139">Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf den Zustand der lync-Server Verbindung, des Audiogeräts, des Videogeräts, des Stabilitäts Status und des Bildschirmgeräts.</span><span class="sxs-lookup"><span data-stu-id="11a61-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="11a61-140">![Lync Room System Admin Portal Raum Gesundheit] (images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Raum Gesundheit")</span><span class="sxs-lookup"><span data-stu-id="11a61-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="11a61-141">Weitere Hinweise zum Webportal für die Verwaltung</span><span class="sxs-lookup"><span data-stu-id="11a61-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="11a61-142">Einstellungsänderungen werden erst nach einem Neustart des LRS-Systems übernommen.</span><span class="sxs-lookup"><span data-stu-id="11a61-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="11a61-143">Wenn das Kennwort für das LRSApp-Konto abläuft, können Sie den Status der Räume nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="11a61-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="11a61-144">Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder achten Sie darauf, das Kennwort zu aktualisieren, wenn es in der Nähe des Ablaufs liegt.</span><span class="sxs-lookup"><span data-stu-id="11a61-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="11a61-145">Das administrative LRS-Webportal wird nur für lokale Bereitstellungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="11a61-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="11a61-146">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="11a61-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="11a61-147">Warum kann ich mich nicht beim Webportal für die Verwaltung anmelden?</span><span class="sxs-lookup"><span data-stu-id="11a61-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="11a61-148">Wenn Sie öffnen https://localhost/lrs, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="11a61-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="11a61-149">In diesem Fall müssen Sie die Anmeldung https://FQDNofFEserver/lrs beim Administrator-Webportal öffnen.</span><span class="sxs-lookup"><span data-stu-id="11a61-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="11a61-150">Wenn sich der Computer, von dem aus Sie auf das administrative Webportal zugreifen, in einer Arbeitsgruppe befindet, kann "http://" nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="11a61-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="11a61-151">Verwenden Sie stattdessen "https".</span><span class="sxs-lookup"><span data-stu-id="11a61-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="11a61-152">Warum wird LRS im Administrator-Webportal nicht angezeigt?</span><span class="sxs-lookup"><span data-stu-id="11a61-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="11a61-153">Stellen Sie sicher, dass Sie über LRS-Konten in Ihrer Bereitstellung verfügen, und dass diese entsprechend den Bereitstellungsempfehlungen des LRS-Administrator Webportals erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="11a61-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="11a61-154">Stellen Sie sicher, dass die LRS-Konten mithilfe von enable-CsMeetingRoom, nicht enable-CsUser, auf dem lync-Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="11a61-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="11a61-155">Wenn Sie LRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des lync Server-Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren LRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="11a61-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="11a61-156">Warum wird der Status von LRS im Administrator-Webportal nicht angezeigt?</span><span class="sxs-lookup"><span data-stu-id="11a61-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="11a61-157">Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11a61-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="11a61-158">Wenn weiterhin Probleme auftreten, sammeln Sie die Datei **Trace. log** im LRS-System von D:\\Tracing\\LRSAdminLogs\\, und senden Sie Sie an Ihren LRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="11a61-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

