---
title: 'Lync Server 2013: Anforderungen für lync für Android'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c584a20df5dc2516115b4b137c0543576d5fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="a05cf-102">Lync für Android-Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05cf-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a05cf-103">_**Letztes Änderungsdatum des Themas:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="a05cf-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="a05cf-104">Microsoft lync 2013 Microsoft lync 2013 für Android bietet Benutzern in Ihrer Organisation, die über ein Android-Gerät eine Verbindung herstellen, Sofortnachrichten (im), erweiterte Anwesenheitsfunktionen und lync-Besprechungs Verknüpfungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="a05cf-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="a05cf-105">In diesem Thema werden die Überlegungen zu lync 2013 für Android beschrieben, einschließlich Voraussetzungen, technischen Anforderungen und erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="a05cf-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="a05cf-106">Voraussetzungen für lync für Android</span><span class="sxs-lookup"><span data-stu-id="a05cf-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="a05cf-107">Zur Unterstützung von lync 2013 für Android muss das Android-Gerät die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a05cf-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="a05cf-108">Auf dem Android-Gerät muss Android 4,0 oder ein höheres Telefon-oder Tablet-basiertes Betriebssystem, einschließlich Tablets, ausgeführt werden, mit Ausnahme der Tegra2-Chips.</span><span class="sxs-lookup"><span data-stu-id="a05cf-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="a05cf-109">Das Gerät muss einen 1,2 GHz-Dual-Core-Prozessor oder eine höhere CPU aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a05cf-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="a05cf-110">Die Gerätekamera (Vorder-und Rückseite) sollte VGA oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="a05cf-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="a05cf-111">Andere Hardwareanforderungen sollten mit dem Android-Kompatibilitäts Definitions Dokument 4,0 ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="a05cf-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="a05cf-112">Weitere technische Überlegungen</span><span class="sxs-lookup"><span data-stu-id="a05cf-112">Other Technical Considerations</span></span>

<span data-ttu-id="a05cf-113">Auf der Android-Geräteplattform kann die lync-Anwendung im Hintergrund ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a05cf-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="a05cf-114">Im Gegensatz zu anderen Plattformen für mobile Geräte sind daher keine Push-Benachrichtigungen für Android-Geräte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a05cf-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="a05cf-115">Die einzige Möglichkeit, die lync-Anwendung auf einem Android-Gerät zu beenden, besteht darin, sich ausdrücklich von lync abzumelden.</span><span class="sxs-lookup"><span data-stu-id="a05cf-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="a05cf-116">Diese Version der lync-Anwendung wird auf Geräten mit Tegra 2-Chipsätze nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a05cf-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

