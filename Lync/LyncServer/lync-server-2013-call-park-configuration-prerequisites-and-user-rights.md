---
title: 'Lync Server 2013: Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a2f322ffec1d2ffa7aa238b76686391fc76ed7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="f3a56-102">Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3a56-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3a56-103">_**Letztes Änderungsdatum des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="f3a56-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="f3a56-104">Anruf Parken ist eine anrufverwaltungsfunktion, die standardmäßig bei der Bereitstellung von Enterprise-VoIP installiert wird.</span><span class="sxs-lookup"><span data-stu-id="f3a56-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f3a56-105">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie den Anruf Park und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="f3a56-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f3a56-106">Angepasste Musik-in-situ-Dateien für die Anwendung "Parken" werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert, und die Dateien gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="f3a56-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="f3a56-107">Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.</span><span class="sxs-lookup"><span data-stu-id="f3a56-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="f3a56-108">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zum Parken von Anrufen gelesen haben (siehe [Planen von Anruf Verwaltungsfeatures in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="f3a56-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="f3a56-109">Voraussetzungen für die Konfiguration des Anruf Parks</span><span class="sxs-lookup"><span data-stu-id="f3a56-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="f3a56-110">Für den Parken von Anrufen sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f3a56-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="f3a56-111">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="f3a56-111">Application service</span></span>

  - <span data-ttu-id="f3a56-112">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="f3a56-112">Call Park application</span></span>

<span data-ttu-id="f3a56-113">Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f3a56-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="f3a56-114">Wenn Sie möchten, dass Anrufer Musik hören, während der Anruf abgestellt wird, ist auch eine Musik-auf-halten-Datei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3a56-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="f3a56-115">Wenn Sie Enterprise-VoIP bereitstellen, wird automatisch eine standardmäßige Music-on-halten-Datei installiert.</span><span class="sxs-lookup"><span data-stu-id="f3a56-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f3a56-116">Sie können die Standarddatei durch ihre eigene Musik-in-halten-Datei ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f3a56-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="f3a56-117">Call Park verwendet den Dateispeicher, um die Audiodatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f3a56-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="f3a56-118">Konfigurations Benutzerrechte des Anruf Parks</span><span class="sxs-lookup"><span data-stu-id="f3a56-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="f3a56-119">Sie können die folgenden Verwaltungstools zum Konfigurieren des Anruf Parks verwenden:</span><span class="sxs-lookup"><span data-stu-id="f3a56-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="f3a56-120">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f3a56-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="f3a56-121">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f3a56-121">Lync Server Management Shell</span></span>

<span data-ttu-id="f3a56-122">Sie verwenden diese Tools, um die Umlaufbahn Tabelle des Anruf Parks einzurichten und andere Einstellungen zu konfigurieren, die von Call Park verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3a56-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="f3a56-123">Die Konfiguration des Anruf Parks erfordert je nach Aufgabe eine der folgenden Administratorrollen:</span><span class="sxs-lookup"><span data-stu-id="f3a56-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="f3a56-124">**CsVoiceAdministrator:** Diese Administratorrolle kann alle sprachbezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="f3a56-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="f3a56-125">**CsUserAdministrator:** Mit dieser Administratorrolle kann der Anruf Park in der VoIP-Richtlinie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f3a56-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="f3a56-126">Diese Administratorrolle verfügt auch über die schreibgeschützte Ansicht Zugriff auf alle Sprachkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f3a56-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="f3a56-127">**CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="f3a56-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="f3a56-128">**CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="f3a56-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3a56-129">Details zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f3a56-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3a56-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3a56-130">See Also</span></span>


[<span data-ttu-id="f3a56-131">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3a56-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="f3a56-132">Planen der Anruf Verwaltungsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3a56-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

