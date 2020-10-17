---
title: 'Lync Server 2013: Schritte zum Vorbereiten und Bereitstellen lync Server Hybridumgebung'
description: 'Lync Server 2013: Schritte zum Vorbereiten und Bereitstellen lync Server Hybridumgebung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffb791a8a45b2220d8987c8d688f346447747c00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546331"
---
# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="9dab8-103">Schritte zum Vorbereiten und Bereitstellen lync Server 2013 Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="9dab8-103">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dab8-104">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="9dab8-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="9dab8-105">In der folgenden Tabelle sind die erforderlichen Schritte zum Vorbereiten der Umgebung für eine hybridbereitstellung mit Skype for Business Online und Microsoft Office 365 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9dab8-105">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dab8-106">Abgeschlossen?</span><span class="sxs-lookup"><span data-stu-id="9dab8-106">Completed?</span></span></th>
<th><span data-ttu-id="9dab8-107">Schritt</span><span class="sxs-lookup"><span data-stu-id="9dab8-107">Step</span></span></th>
<th><span data-ttu-id="9dab8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dab8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9dab8-109">Erstellen eines Mandanten Kontos für Office 365 und Aktivieren von lync Online</span><span class="sxs-lookup"><span data-stu-id="9dab8-109">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="9dab8-110">Informationen zu Office 365 und lync Online finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-110">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="9dab8-111">Wenn Sie sicherstellen möchten, dass Ihre Umgebung für Office 365 bereit ist, lesen Sie die <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Anforderungen</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-111">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="9dab8-112">Ausführliche Informationen zum Einrichten von Office 365 finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Erste Schritte mit Office 365</a> und <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Einrichten von Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-112">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9dab8-113">Hinzufügen Ihrer Domäne und Überprüfen des Besitzes</span><span class="sxs-lookup"><span data-stu-id="9dab8-113">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="9dab8-114">Ihre Domäne wird manchmal auch als ihre Vanity- <em>Domäne</em>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9dab8-114">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="9dab8-115">Sie müssen Ihre Domäne Ihrer Office 365 Organisation hinzufügen und dann die Schritte ausführen, um die Domäne mit Office 365 zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9dab8-115">You must add your domain to your Office 365 organization, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="9dab8-116">Dadurch wird bestätigt, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="9dab8-116">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="9dab8-117">Führen Sie die unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Hinzufügen Ihrer Domäne zu Office 365</a>beschriebenen Schritte aus, um Ihre Domäne zu Ihrer Office 365 Organisation hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9dab8-117">To add your domain to your Office 365 organization, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="9dab8-118">Führen Sie alle Schritte in den einzelnen Abschnitten des Themas aus, einschließlich &quot; Bearbeiten von DNS-Einträgen für Ihre Office 365 Dienste.&quot;</span><span class="sxs-lookup"><span data-stu-id="9dab8-118">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9dab8-119">Überprüfen der Umgebungs Bereitschaft</span><span class="sxs-lookup"><span data-stu-id="9dab8-119">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="9dab8-120">Sie können den Office 365-Setup-Assistenten verwenden, um Sie bei der Bereitstellung von Office 365 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9dab8-120">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="9dab8-121">Weitere Informationen finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">use Setup Assistant to bestimmen Office 365 Readiness</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-121">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="9dab8-122">Ausführliche Informationen zur Verwendung des Tools und zum Bereitstellen von Office 365 finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 Deployment Guide</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-122">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9dab8-123">Vorbereiten der Active Directory Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="9dab8-123">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="9dab8-124">Durch Active Directory Synchronisierung wird Ihre lokale Active Directory kontinuierlich mit Office 365 synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="9dab8-124">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="9dab8-125">Auf diese Weise können Sie synchronisierte Versionen aller Benutzerkonten und Gruppen erstellen und außerdem die Synchronisierung der globalen Adressliste (GAL) zwischen der lokalen Exchange Server Umgebung und Microsoft Exchange Online aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9dab8-125">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="9dab8-126">Sie müssen die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online-lync-Bereitstellungen synchronisieren, auch wenn Benutzer nicht zu lync Online verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="9dab8-126">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="9dab8-127">Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Online Benutzern in Ihrer Organisation möglicherweise nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="9dab8-127">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="9dab8-128">Um Ihre Umgebung für Active Directory Synchronisierung vorzubereiten, befolgen Sie die unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Verzeichnis Synchronisierungs-Roadmap</a>beschriebenen Schritte, einschließlich der Einrichtung des einmaligen Anmeldens.</span><span class="sxs-lookup"><span data-stu-id="9dab8-128">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9dab8-129">Erstellen von Zertifikaten für Active Directory Verbunddienste (AD FS)</span><span class="sxs-lookup"><span data-stu-id="9dab8-129">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="9dab8-130">Sie müssen die Zertifikate erstellen, die für den Identitätsverbund mit Office 365 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9dab8-130">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="9dab8-131">Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" des Themas planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Prüfliste: Verwenden von AD FS zum Implementieren und Verwalten des einmaligen Anmeldens</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-131">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9dab8-132">Zuweisen von Zertifikaten für AD FS</span><span class="sxs-lookup"><span data-stu-id="9dab8-132">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="9dab8-133">Nachdem Sie die Zertifikate erstellt haben, die für den Identitätsverbund mit Office 365 verwendet werden, müssen Sie diese installieren und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9dab8-133">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9dab8-134">Migrieren von Pilotbenutzern zu Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9dab8-134">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="9dab8-135">Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren Ihrer Umgebung für Skype for Business Online abgeschlossen haben, können Sie mit dem Verschieben von Pilotbenutzern in lync Online beginnen.</span><span class="sxs-lookup"><span data-stu-id="9dab8-135">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="9dab8-136">Weitere Informationen finden Sie unter <a href="lync-server-2013-move-users-to-lync-online.md">Migrieren von Benutzern zu lync Online in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-136">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9dab8-137">Verwalten von Benutzern in einer hybridbereitstellung</span><span class="sxs-lookup"><span data-stu-id="9dab8-137">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="9dab8-138">Ausführliche Informationen zur Verwaltung von Benutzern in einer hybridbereitstellung finden Sie unter Verwalten von <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Benutzern in einer hybriden lync Server 2013-Bereitstellung</a>.</span><span class="sxs-lookup"><span data-stu-id="9dab8-138">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

