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
ms.openlocfilehash: 4fe9ddd835d569aca129d53de2a44e2a00b39794
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="f0f24-102">Einrichten eines Sicherungsspeicherorts für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0f24-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0f24-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f0f24-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f0f24-104">Bevor Sie die erste Sicherung von lync Server durchführen, richten Sie die Hardware und Software ein, die Sie benötigen, um die Sicherungen zu speichern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f0f24-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="f0f24-105">Verschaffen Sie sich Zugriff auf die erforderlichen Medien und Inhalte, und stellen Sie die Netzwerkkonnektivität zwischen den einzelnen zu sichernden Servern und den Sicherungsmedien her.</span><span class="sxs-lookup"><span data-stu-id="f0f24-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="f0f24-106">Die verwendeten Medien und Standorte sollten in der Sicherungs-und Wiederherstellungsstrategie definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0f24-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="f0f24-107">Der Speicherort, den Sie für reguläre Sicherungen verwenden, kann lokal oder Remote sein, er muss jedoch sicher sein, und er muss sowohl für die Sicherung als auch für die Wiederherstellung zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="f0f24-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="f0f24-108">Es wird empfohlen, einen Remotestandort zum Schutz vor einem katastrophalen Ereignis am primären Standort zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0f24-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="f0f24-109">Überprüfen Sie nach dem Einrichten und Testen der einzelnen Komponenten, ob von jedem Server auf die Sicherungen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0f24-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

