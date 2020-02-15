---
title: 'Lync Server 2013: Voraussetzungen und Benutzerrechte für die Konfiguration des Anruf Parks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19a677b7b1a76c0956b5edc663e8932716ce5fb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="60fd4-102">Voraussetzungen und Benutzerrechte für die Konfiguration des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60fd4-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60fd4-103">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="60fd4-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="60fd4-104">Das Parken von anrufen ist ein Anruf Verwaltungsfeature, das standardmäßig bei der Bereitstellung von Enterprise-VoIP installiert wird.</span><span class="sxs-lookup"><span data-stu-id="60fd4-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="60fd4-105">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie das Parken von Anrufen und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60fd4-106">Benutzerdefinierte Musikdateien für die Anwendung zum Parken von Anrufen werden im Rahmen des lync Server 2013 Notfall Wiederherstellungsvorgangs nicht gesichert, und die Dateien gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="60fd4-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="60fd4-107">Bewahren Sie immer eine separate Sicherungskopie der angepassten Musikdateien auf, die Sie für das Parken von Anrufen hochgeladen haben.</span><span class="sxs-lookup"><span data-stu-id="60fd4-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="60fd4-108">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation im Zusammenhang mit dem Parken von Anrufen gelesen haben (siehe [Planning for Call Management Features in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="60fd4-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="60fd4-109">Voraussetzungen für die Konfiguration des Anruf Parks</span><span class="sxs-lookup"><span data-stu-id="60fd4-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="60fd4-110">Das Parken von Anrufen erfordert die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="60fd4-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="60fd4-111">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="60fd4-111">Application service</span></span>

  - <span data-ttu-id="60fd4-112">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="60fd4-112">Call Park application</span></span>

<span data-ttu-id="60fd4-113">Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="60fd4-114">Wenn Sie möchten, dass Anrufer Wartemusik hören, solange der Anruf geparkt ist, wird zusätzlich eine Datei für die Wartemusik benötigt.</span><span class="sxs-lookup"><span data-stu-id="60fd4-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="60fd4-115">Eine standardmäßige Musikdatei wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="60fd4-116">Sie können die Standarddatei durch eine eigene Wartemusikdatei ersetzen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="60fd4-117">Der Anruf Park verwendet Dateispeicher, um die Audiodatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="60fd4-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="60fd4-118">Konfigurieren von Benutzerrechten für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="60fd4-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="60fd4-119">Sie können die folgenden Verwaltungstools verwenden, um das Parken von Anrufen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="60fd4-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="60fd4-120">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="60fd4-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="60fd4-121">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="60fd4-121">Lync Server Management Shell</span></span>

<span data-ttu-id="60fd4-122">Sie verwenden diese Tools zum Einrichten der Orbit-Tabelle für das Parken von Anrufen und zum Konfigurieren anderer Einstellungen, die von der Funktion zum Parken von Anrufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60fd4-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="60fd4-123">Für die Konfiguration des Parkens von Anrufen sind je nach Aufgabe die folgenden Administratorrollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="60fd4-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="60fd4-124">**CsVoiceAdministrator:** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="60fd4-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="60fd4-125">**CsUserAdministrator:** Diese Administratorrolle kann das Parken von Anrufen in der VoIP-Richtlinie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="60fd4-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="60fd4-126">Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="60fd4-127">**CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="60fd4-128">**CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="60fd4-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60fd4-129">Ausführliche Informationen zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="60fd4-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60fd4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60fd4-130">See Also</span></span>


[<span data-ttu-id="60fd4-131">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60fd4-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="60fd4-132">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60fd4-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

