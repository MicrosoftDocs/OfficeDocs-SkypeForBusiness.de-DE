---
title: Konfigurieren von PIN-Regeln (Personal Identification Number) für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda9269bb53a463bf439aef8fda87cbae5bdf17b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="f099b-102">Konfigurieren von Einwahlkonferenz-Regeln (Personal Identification Number, PIN) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f099b-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f099b-103">_**Letztes Änderungsdatum des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="f099b-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="f099b-104">Lync Server 2013-Benutzer, die über die Active Directory-Domänendienste (AD DS)-Anmeldeinformationen in Ihrer Organisation verfügen, können mithilfe einer persönlichen Identifikationsnummer (PIN) an Einwahlkonferenzen als authentifizierte Benutzer teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="f099b-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="f099b-105">In einer PIN-Richtlinie werden die Regeln für die Funktionsweise der Einwahlkonferenz-PINs definiert.</span><span class="sxs-lookup"><span data-stu-id="f099b-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="f099b-106">Sie können eine neue PIN-Richtlinie erstellen, wenn für einen Standort oder eine bestimmte Benutzergruppe eine bestimmte Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="f099b-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="f099b-107">Wenn Sie dieselbe PIN-Richtlinie für Ihre gesamte Organisation einsetzen möchten, können Sie die globale PIN-Richtlinie verwenden und nach Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="f099b-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="f099b-108">Die PIN-Richtlinien gelten für Benutzer vom engsten bis hin zum weitesten Bereich.</span><span class="sxs-lookup"><span data-stu-id="f099b-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="f099b-109">Wenn Sie einem Benutzer eine PIN-Richtlinie auf Benutzerebene zuweisen, erhalten diese Einstellungen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="f099b-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="f099b-110">Wenn Sie keine Benutzerrichtlinie zuweisen, gilt die PIN-Richtlinie auf Standortebene, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f099b-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="f099b-111">Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale PIN-Richtlinie die Standardeinstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="f099b-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f099b-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f099b-112">In This Section</span></span>

  - [<span data-ttu-id="f099b-113">Ändern der Standard-PIN-Einstellungen für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f099b-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="f099b-114">Erstellen oder Ändern der PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f099b-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="f099b-115">Löschen von Einwahlkonferenz-PIN-Einstellungen für eine Website oder eine Benutzergruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f099b-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

