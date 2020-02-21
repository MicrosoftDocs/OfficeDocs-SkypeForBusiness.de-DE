---
title: Konfigurieren von PIN-Regeln (persönliche Identifikationsnummer) für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16b56e1809f9ffefa37065a208340e1143e38487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="43538-102">Konfigurieren von PIN-Regeln (private Identification Number) für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43538-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43538-103">_**Letztes Änderungsstand des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="43538-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="43538-104">Lync Server 2013 Benutzer mit Active Directory-Domänendienste (AD DS) Anmeldeinformationen in Ihrer Organisation können Einwahlkonferenzen als authentifizierte Benutzer mithilfe einer persönlichen Identifikationsnummer (PIN) beitreten.</span><span class="sxs-lookup"><span data-stu-id="43538-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="43538-105">In einer PIN-Richtlinie werden die Regeln für die Funktionsweise der Einwahlkonferenz-PINs definiert.</span><span class="sxs-lookup"><span data-stu-id="43538-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="43538-p102">Sie können eine neue PIN-Richtlinie erstellen, wenn für einen Standort oder eine bestimmte Benutzergruppe eine bestimmte Richtlinie gelten soll. Wenn Sie dieselbe PIN-Richtlinie für Ihre gesamte Organisation einsetzen möchten, können Sie die globale PIN-Richtlinie verwenden und nach Bedarf anpassen. Die PIN-Richtlinien gelten für Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine PIN-Richtlinie auf Benutzerebene zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gilt die PIN-Richtlinie auf Standortebene, falls vorhanden. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale PIN-Richtlinie die Standardeinstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="43538-p102">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users. If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="43538-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="43538-112">In This Section</span></span>

  - [<span data-ttu-id="43538-113">Ändern der standardmäßigen PIN-Einstellungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43538-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="43538-114">Erstellen oder Ändern von PIN-Einstellungen für Einwahlkonferenzen in lync Server 2013 für einen Standort oder eine Benutzergruppe</span><span class="sxs-lookup"><span data-stu-id="43538-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="43538-115">Löschen von PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43538-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

