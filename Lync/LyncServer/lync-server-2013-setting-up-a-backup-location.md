---
title: 'Lync Server 2013: Einrichten eines Sicherungsspeicherorts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 723bcbc2aeaae5264645d824a9b10a939b6770ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="364d1-102">Einrichten eines Sicherungsspeicherorts für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="364d1-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="364d1-103">_**Letztes Änderungsdatum des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="364d1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="364d1-104">Bevor Sie die erste Sicherung von lync Server durchführen, richten Sie die Hardware und Software ein, die Sie benötigen, um die Sicherungen zu speichern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="364d1-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="364d1-105">Sie müssen je nach Bedarf Zugriff auf die Medien und Inhalte erhalten und die Netzwerkkonnektivität zwischen den einzelnen zu sichernden Servern und den Sicherungsmedien bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="364d1-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="364d1-106">Die von Ihnen verwendeten Medien und Standorte sollten in ihrer Sicherungs-und Wiederherstellungsstrategie definiert werden.</span><span class="sxs-lookup"><span data-stu-id="364d1-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="364d1-107">Der Speicherort, den Sie für reguläre Sicherungen verwenden, kann lokal oder Remote sein, aber er muss sicher sein, und er muss für die Sicherung und Wiederherstellung zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="364d1-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="364d1-108">Wir empfehlen, einen Remotestandort zu verwenden, um vor einem katastrophalen Ereignis an Ihrem primären Standort zu schützen.</span><span class="sxs-lookup"><span data-stu-id="364d1-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="364d1-109">Nachdem Sie die einzelnen Komponenten eingerichtet und getestet haben, überprüfen Sie die Barrierefreiheit der Sicherungen auf den einzelnen Servern.</span><span class="sxs-lookup"><span data-stu-id="364d1-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

