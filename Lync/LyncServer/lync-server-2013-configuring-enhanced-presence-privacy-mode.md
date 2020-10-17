---
title: 'Lync Server 2013: Konfigurieren des Datenschutzmodus für erweiterte Anwesenheit'
description: 'Lync Server 2013: Konfigurieren des Datenschutzmodus für erweiterte Anwesenheitsinformationen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548451"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="217e4-103">Konfigurieren des Datenschutzmodus für erweiterte Anwesenheitsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="217e4-103">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="217e4-104">_**Letztes Änderungsstand des Themas:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="217e4-104">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="217e4-105">Mit dem Datenschutzmodus für erweiterte Anwesenheit können Benutzer ihre Anwesenheitsinformationen so einschränken, dass Sie nur für die Kontakte sichtbar sind, die in ihrer lync 2013 Kontaktliste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="217e4-105">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="217e4-106">Die Cmdlets **New-CsPrivacyConfiguration**   und **Sets-CsPrivacyConfiguration** verfügen über einen EnablePrivacyMode-Parameter, der diese Option steuert.</span><span class="sxs-lookup"><span data-stu-id="217e4-106">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="217e4-107">Wenn EnablePrivacyMode auf "true" festgelegt ist, wird die Option zum Einschränken der Anwesenheitsinformationen auf Kontakte in den lync 2013 Status Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="217e4-107">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="217e4-108">Wenn EnablePrivacyMode auf "false" festgelegt ist, können Benutzer auswählen, dass jeder immer seine Anwesenheitsinformationen anzeigen oder sich an zukünftige Änderungen halten kann, die der Administrator im Datenschutzmodus durchführt.</span><span class="sxs-lookup"><span data-stu-id="217e4-108">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="217e4-109">Lync 2013-und lync 2010-Datenschutzeinstellungen werden durch frühere Versionen (Microsoft Office Communicator 2007 R2 oder Microsoft Office Communicator 2007) nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="217e4-109">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="217e4-110">Wenn sich frühere Versionen von Office Communicator anmelden können, kann der Status eines lync 2013 Benutzers, die Kontaktinformationen oder das Bild von einer Person angezeigt werden, die nicht berechtigt ist, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="217e4-110">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="217e4-111">Darüber hinaus werden die Datenschutzeinstellungen eines lync 2013 Benutzers zurückgesetzt, wenn er sich später mit einer früheren Version von Communicator anmeldet.</span><span class="sxs-lookup"><span data-stu-id="217e4-111">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="217e4-112">Aus diesen Gründen in einem Migrationsszenario, bevor Sie den erweiterten Datenschutzmodus für Anwesenheit aktivieren:</span><span class="sxs-lookup"><span data-stu-id="217e4-112">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="217e4-113">Stellen Sie sicher, dass alle Benutzer lync 2013 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="217e4-113">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="217e4-114">Definieren Sie eine clientversionsrichtlinien Regel, um zu verhindern, dass sich frühere Versionen von Communicator anmelden.</span><span class="sxs-lookup"><span data-stu-id="217e4-114">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="217e4-115">So aktivieren Sie den Datenschutzmodus für erweiterte Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="217e4-115">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="217e4-116">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="217e4-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="217e4-117">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="217e4-117">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="217e4-118">Mit diesem Befehl wird der Datenschutzmodus für alle derzeit in der Organisation verwendeten Datenschutz-Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="217e4-118">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="217e4-119">Weitere Informationen darüber, wie die Richtlinienkonfigurationen für den lync Server Enhanced Presence-Datenschutzmodus die Kontakt Anwesenheit für den lync 2013-Client verwaltet, finden Sie im Microsoft KB-Artikel [aktivieren lync Server erweiterten Anwesenheitsdaten Modus aktualisiert den Anwesenheitsstatus einiger lync-Kontakte auf "nicht verfügbar"](https://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="217e4-119">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](https://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="217e4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="217e4-120">See Also</span></span>


[<span data-ttu-id="217e4-121">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="217e4-121">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="217e4-122">New-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="217e4-122">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="217e4-123">Gruppe-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="217e4-123">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

