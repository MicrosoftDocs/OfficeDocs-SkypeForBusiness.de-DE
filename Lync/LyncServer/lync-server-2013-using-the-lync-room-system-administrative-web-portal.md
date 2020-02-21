---
title: 'Lync Server 2013: Verwenden des Administrator-Webportals von lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d950bd62b2db91f60dd5828f79977472a9c5d573
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="c5951-102">Verwenden des Administrator-Webportals von lync Room System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5951-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5951-103">_**Letztes Änderungsstand des Themas:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="c5951-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="c5951-104">Nachdem Sie LRS auf dem Server bereitgestellt haben, können Sie den Status aller LRS-Räume überprüfen, indem Sie sich über einen Browser beim administrativen Webportal für LRS anmelden.</span><span class="sxs-lookup"><span data-stu-id="c5951-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="c5951-105">Anmelden</span><span class="sxs-lookup"><span data-stu-id="c5951-105">Sign in</span></span>

1.  <span data-ttu-id="c5951-106">Wechseln Sie zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="c5951-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="c5951-107">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="c5951-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="c5951-108">Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5951-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="c5951-109">![Anmeldebildschirm des lync Room-System Administrator Portals](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm des lync Room-System Administrator Portals")</span><span class="sxs-lookup"><span data-stu-id="c5951-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="c5951-110">Seite "Übersicht über das LRS-Verwaltungsportal"</span><span class="sxs-lookup"><span data-stu-id="c5951-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="c5951-111">Die Zusammenfassungsseite enthält die folgenden Informationen zu allen auf dem Server bereitgestellten LRS-Räumen:</span><span class="sxs-lookup"><span data-stu-id="c5951-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="c5951-112">**Markieren**   Sie den benutzerdefinierten Namen, den der Administrator dem Chatroom übergibt.</span><span class="sxs-lookup"><span data-stu-id="c5951-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="c5951-113">Das-Tag kann im Portal festgelegt werden, indem auf den Raumnamen geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="c5951-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="c5951-114">**Integrität**   der Integritätsstatus des Raums, der vom aggregierten Integritätsstatus des Raums abgeleitet wird, der auf der Seite "Raumeinstellungen" im Abschnitt "Integrität" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c5951-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="c5951-115">**Nächste Besprechung**   das Datum und die Uhrzeit, zu denen die nächste Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="c5951-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="c5951-116">**LRS-Version, Hersteller, Modell**   diese Werte werden in LRS voreingestellt.</span><span class="sxs-lookup"><span data-stu-id="c5951-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="c5951-117">Je nach Hersteller können diese Felder leer bleiben.</span><span class="sxs-lookup"><span data-stu-id="c5951-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="c5951-118">**Bei der letzten Aktualisierung**   wird angezeigt, wann die Webseite zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c5951-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="c5951-119">![Zusammenfassung der lync Room System-Administrator Portal-Ansicht](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Zusammenfassung der lync Room System-Administrator Portal-Ansicht")</span><span class="sxs-lookup"><span data-stu-id="c5951-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="c5951-120">LRS-Rauminformationen</span><span class="sxs-lookup"><span data-stu-id="c5951-120">LRS Room Information</span></span>

<span data-ttu-id="c5951-121">Im Abschnitt "Rauminformationen" des Portals können Sie einzelne LRS-Räume anzeigen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c5951-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="c5951-122">Es enthält vier Abschnitte: Einstellungen, Details, Problembehandlung und Integrität.</span><span class="sxs-lookup"><span data-stu-id="c5951-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="c5951-123">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c5951-123">Settings</span></span>

<span data-ttu-id="c5951-124">Im Abschnitt "Einstellungen" können Sie das Kennwort, das Raum-Tag und die Standardlautstärke für den Raum festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5951-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="c5951-125">Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst nach dem Neustart der LRS-Konsole repliziert.</span><span class="sxs-lookup"><span data-stu-id="c5951-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="c5951-126">Es werden nur System Updateeinstellungen für lync-Raumsysteme angezeigt, die Version 15,12 und höher sind.</span><span class="sxs-lookup"><span data-stu-id="c5951-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="c5951-127">![Raum System-Administrator Portal-Einstellungen für lync Room-Systeme](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Raum System-Administrator Portal-Einstellungen für lync Room-Systeme")</span><span class="sxs-lookup"><span data-stu-id="c5951-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="c5951-128">Details</span><span class="sxs-lookup"><span data-stu-id="c5951-128">Details</span></span>

<span data-ttu-id="c5951-129">Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des LRS-Raums, einschließlich: der Zeitpunkt der letzten Aktualisierung; nächste Besprechung; Letzte Aktualisierungen, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mic und Rufton; Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.</span><span class="sxs-lookup"><span data-stu-id="c5951-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="c5951-130">![Detail Ansicht des lync Room-System Administrator Portals](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Detail Ansicht des lync Room-System Administrator Portals")</span><span class="sxs-lookup"><span data-stu-id="c5951-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="c5951-131">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c5951-131">Troubleshooting</span></span>

<span data-ttu-id="c5951-132">Der Abschnitt Problembehandlung kann verwendet werden, um Protokolle Remote zu sammeln und Sie an einem angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c5951-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="c5951-133">Sie können auch die LRS-Konsole (LRS-Benutzeroberfläche) neu starten oder das gesamte System neu starten.</span><span class="sxs-lookup"><span data-stu-id="c5951-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="c5951-134">Geben Sie zum Sammeln von Protokollen einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen verfügt, die für das Konto des LRS-Computers erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="c5951-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="c5951-135">Wenn die Protokollgröße zu groß ist, kann es bis zu 5 Minuten dauern, bis das Sammeln von Protokollen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c5951-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="c5951-136">Wenn Sie die Seite aktualisieren, erhalten Sie den neuesten Status.</span><span class="sxs-lookup"><span data-stu-id="c5951-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="c5951-137">![Protokollierung des Chatroom-Administrator Portals für lync Raumsysteme](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Protokollierung des Chatroom-Administrator Portals für lync Raumsysteme")</span><span class="sxs-lookup"><span data-stu-id="c5951-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="c5951-138">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="c5951-138">Health</span></span>

<span data-ttu-id="c5951-139">Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf die Integrität der lync Server-Verbindung, des Audiogeräts, des Videogeräts, des Zustands der Ausfallsicherheit und des Bildschirmgeräts.</span><span class="sxs-lookup"><span data-stu-id="c5951-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="c5951-140">![Raum System-Administrator Portal für lync Room-Integrität](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Raum System-Administrator Portal für lync Room-Integrität")</span><span class="sxs-lookup"><span data-stu-id="c5951-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="c5951-141">Zusätzliche Hinweise zum administrativen Webportal</span><span class="sxs-lookup"><span data-stu-id="c5951-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="c5951-142">Einstellungsänderungen werden nur angewendet, nachdem das LRS-System neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="c5951-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="c5951-143">Wenn das Kennwort für das LRSApp-Konto abgelaufen ist, können Sie den Status der Räume nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c5951-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="c5951-144">Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es sich in der Nähe des Ablaufs befindet.</span><span class="sxs-lookup"><span data-stu-id="c5951-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="c5951-145">Das LRS-Verwaltungsportal wird nur für lokale Bereitstellungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c5951-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c5951-146">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="c5951-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="c5951-147">Warum kann ich mich nicht beim administrativen Webportal anmelden?</span><span class="sxs-lookup"><span data-stu-id="c5951-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="c5951-148">Wenn Sie öffnen https://localhost/lrs, werden Sie die Anmeldeseite sehen können, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="c5951-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="c5951-149">In diesem Fall müssen Sie sich öffnen https://FQDNofFEserver/lrs , um sich beim administrativen Webportal anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c5951-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="c5951-150">Wenn sich der Computer, auf dem Sie das administrative Webportal aufrufen, in einer Arbeitsgruppe befindet, funktioniert "http://" nicht.</span><span class="sxs-lookup"><span data-stu-id="c5951-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="c5951-151">Verwenden Sie stattdessen "https".</span><span class="sxs-lookup"><span data-stu-id="c5951-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="c5951-152">Warum wird LRS nicht im administrativen Webportal angezeigt?</span><span class="sxs-lookup"><span data-stu-id="c5951-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="c5951-153">Stellen Sie sicher, dass Sie über LRS-Konten in Ihrer Bereitstellung verfügen und dass Sie entsprechend den Bereitstellungsempfehlungen für das LRS-Verwaltungsportal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c5951-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="c5951-154">Stellen Sie sicher, dass die LRS-Konten mithilfe von enable-csmeetingroom ", not enable-CsUser, auf dem lync-Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c5951-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="c5951-155">Wenn Sie LRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des lync Server Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren LRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="c5951-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="c5951-156">Warum kann ich den Status von LRS nicht im administrativen Webportal anzeigen?</span><span class="sxs-lookup"><span data-stu-id="c5951-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="c5951-157">Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c5951-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="c5951-158">Wenn Sie weiterhin Probleme haben, sammeln Sie die **Trace. log** -Datei im LRS-System von D\\:\\Tracing\\LRSAdminLogs, und senden Sie Sie dann an Ihren LRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="c5951-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

